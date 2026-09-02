---
title: "로블록스 스튜디오 스크립트: GetService"
categories: RobloxStudio
# excerpt: ""
---




# 📌 TweenService
{: .notice}

어떤 값이 일정 시간 동안 부드럽게 변하도록 만들어주는 서비스

```Lua
local TweenService = game:GetService("TweenService")

local Part = script.Parent

local PartTweenInfo = TweenInfo.new(
	3, -- time
	Enum.EasingStyle.Linear, -- easingStyle
	Enum.EasingDirection.InOut, -- easingDirection
	-1, -- repeatCount
	true, -- reverses
	2 -- delayTime
)

local TweenPropertyTable = {
	Color = Color3.fromRGB(255, 0, 0),
	Position = Vector3.new(Part.Position.X + 10, Part.Position.Y, Part.Position.Z),
	Size = Part.Size
}

local Tween = TweenService:Create(Part, PartTweenInfo, TweenPropertyTable)

Tween:Play()
```




# 📌 UserInputService
{: .notice}

```Lua
local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(Input, GameProcessedEvent)
	if Input.UserInputType == Enum.UserInputType.Keyboard then
		-- GameProcessedEvent를 조건에도 넣어 채팅중일 때 키가 눌리지 않도록 설정
		if Input.KeyCode == Enum.KeyCode.E and not GameProcessedEvent then 
			
		end
	end
end)

UserInputService:GetMouseLocation()
UserInputService:IsKeyDown()
UserInputService.MouseBehavior = Enum.MouseBehavior.LockCenter -- 마우스를 중앙에 잠금
```




# 📌 RemoteEvent: FireServer → OnServerEvent
{: .notice}

<pre>
ReplicatedStorage
└─ RemoteEvent

ServerScriptService
└─ Script -- Server

StarterGui
└─ ScreenGui
       ├─ LocalScript -- Client
       └─ TextButton
</pre>

LocalScript (Client)
```Lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local BuyPotion = ReplicatedStorage:WaitForChild("RemoteEvent")

script.Parent.TextButton.MouseButton1Click:Connect(function()
	BuyPotion:FireServer("Potion", 100) -- 서버에 필요한 기능을 요구
end)
```

Script (Server)
```ruby
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local BuyPotion = ReplicatedStorage:WaitForChild("RemoteEvent")

BuyPotion.OnServerEvent:Connect(function(Player, ItemName, Price) -- 서버에서만 처리해야할 기능을 클라이언트에서 받아 처리
	print(Player.Name)
	print(ItemName)
	print(Price)
end)
```



# 📌 RemoteEvent: FireClient → OnClientEvent
{: .notice}




# 📌 RemoteEvent: FireAllClients → OnClientEvent
{: .notice}




# 📌 RemoteFunction: InvokeServer ↔ OnServerInvoke
{: .notice}

<pre>
Workspace
└─ Part
       └─ ClickDetector

ReplicatedStorage
└─ RemoteFunction

ServerScriptService
└─ Script -- Server

StarterPlayer
└─ StarterPlayerScripts
       └─ LocalScript -- Client
</pre>

LocalScript (Client)
```luau
local RaplicatedStorage = game:GetService("ReplicatedStorage")
local RemoteFunction = RaplicatedStorage:WaitForChild("RemoteFunction")

local Part = game.Workspace:WaitForChild("Part")
local ClickDetector = Part.ClickDetector

ClickDetector.MouseClick:Connect(function(Player)
	local Result = RemoteFunction:InvokeServer(50)
	
	print(Result)
end)
```

Script (Server)
```luau
local RaplicatedStorage = game:GetService("ReplicatedStorage")
local RemoteFunction = RaplicatedStorage:WaitForChild("RemoteFunction")

RemoteFunction.OnServerInvoke = function(Player, Number)
	Number *= 2
	
	return Player.Name .. " - " .. tostring(Number)
end
```




# 📌 DataStoreService
{: .notice}

File → Experience Settings → Security → Enable Studio Access to API Services = On → Save

*Play Server & Clinets

<pre>
ServerScriptService
└─ Script
</pre>

```lua
local DataStoreService = game:GetService("DataStoreService")
local DataStore = DataStoreService:GetDataStore("DataStore") -- "데이터 저장소 이름 지정"

local function SaveData(Player)
	local Success, ErrorMessage = pcall(function() -- Protected Call, 오류 발생시 게임을 멈추지 않고 결과 반환(성공: true, nil 반환 / 실패: false, "오류 내용" 반환)
		DataStore:SetAsync(Player.UserId .. "-Cash", Player.leaderstats.Cash.Value) -- SetAsync(key, value) Setter
		
		DataStore:UpdateAsync(Player.UserId .. "-Cash", function(OldValue) -- 기존 value를 가져와야 할 때 UpdateAsync 사용
			return Player.leaderstats.Cash.Value -- 다음과 같이 사용: return Player.leaderstats.Cash.Value + OldValue
		end)
	end)

	if not Success then
		warn(ErrorMessage)
	end	
end

game.Players.PlayerAdded:Connect(function(Player) -- 플레이어가 게임에 들어왔을 때 실행되는 이벤트
	local Leaderstats = Instance.new("Folder")
	Leaderstats.Name = "leaderstats"
	Leaderstats.Parent = Player
	
	local Cash = Instance.new("IntValue")
	Cash.Name = "Cash"
	Cash.Parent = Leaderstats
	
	local CashData = nil
	
	local Success, ErrorMessage = pcall(function()
		CashData = DataStore:GetAsync(Player.UserId .. "-Cash") -- GetAsync(key) Getter, return value
	end)
	
	if Success then
		if CashData ~= nil then
			Cash.Value = CashData -- Player의 DataStore에 저장된 값이 있으면 로드
		end
	else
		warn(ErrorMessage)
	end
end)

game.Players.PlayerRemoving:Connect(function(Player) -- 플레이어가 게임에서 나갈 때 발생하는 이벤트
	SaveData(Player)
end)

game:BindToClose(function() -- 게임 서버가 종료될 때 발생하는 이벤트
	for i, Player in pairs(game.Players:GetChildren()) do
		SaveData(Player)
	end
end)
```
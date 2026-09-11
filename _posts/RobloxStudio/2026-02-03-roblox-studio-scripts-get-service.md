---
title: "로블록스 스튜디오 스크립트: GetService"
categories: RobloxStudio
# excerpt: ""
---




# 📌 TweenService
{: .notice}

어떤 값이 일정 시간 동안 부드럽게 변하도록 만들어주는 서비스

```lua
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

```lua
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

<span class="color-control">ReplicatedStorage</span> <br>
└─<span class="color-string">RemoteEvent</span> <br>
<br>
<span class="color-control">ServerScriptService</span> <br>
└─<span class="color-string">Script</span> -- Server <br>
<br>
<span class="color-control">StarterGui</span> <br>
└─<span class="color-string">ScreenGui</span> <br>
　 　├─<span class="color-function">LocalScript</span> -- Client <br>
　 　└─<span class="color-function">TextButton</span>

<br>

<span class="color-function">LocalScript</span> (Client)

```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local BuyPotion = ReplicatedStorage:WaitForChild("RemoteEvent")

script.Parent.TextButton.MouseButton1Click:Connect(function()
	BuyPotion:FireServer("Potion", 100) -- 서버에 필요한 기능을 요구
end)
```

<br>

<span class="color-string">Script</span> (Server)

```lua
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
```lua
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
```lua
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




# 📌 ContextActionService
{: .notice}

<pre>
StarterPlayer
└─ StarterPlayerScripts
       └─ LocalScript
</pre>

```lua
local ContextActionService = game:GetService("ContextActionService") -- 여러 플랫폼의 Input을 하나의 방식으로 쉽게 처리

local function OnEPressed()
	print("Pressed E")
end

ContextActionService:BindAction("Horn", OnEPressed, true, Enum.KeyCode.E) -- BindAction(액션 이름, 실행할 함수, 모바일 버튼 생성 여부, 입력)
--ContextActionService:SetPosition("Horn", UDim2.new(0.5, 0, 0.8, 0)) -- 모바일에서의 버튼 위치 설정, *작동이 안됨
Button = ContextActionService:GetButton("Horn") -- 대체 함수
if Button then -- PC에선 Button이 nil로 뜨기때문에 조건 넣기
	Button.Position = UDim2.new(0.2, 0, 0.5, 0)
end
ContextActionService:SetTitle("Horn", "E") -- 모바일에서의 버튼 글자 설정

task.wait(10)

ContextActionService:UnbindAction("Horn") -- 액션 해제(Input 버튼 제거)
```




# 📌 MarketplaceService (Pass)
{: .notice}

File → Experience Settings → Security → Allow Third Party Sales = On → Save

*Play Server & Clinets

<pre>
ServerScriptService
└─ Script

StarterGui
└─ ScreenGui
       └─ TextButton
           └─ Local Script
</pre>

Script
```lua
local MarketplaceService = game:GetService("MarketplaceService")

local GamepassID = 1965794766 -- create.roblox.com → Creations → 생성할 Experience 선택 → Monetization → Passes → Create pass (Item for sale = On) → Pass ID

MarketplaceService.PromptGamePassPurchaseFinished:Connect(function(Player, ID, WasPurchased) -- 구매 과정이 끝났을 때 발생하는 이벤트(플레이어, Pass ID, 구매 확인 bool 값)
	if WasPurchased and GamepassID == ID then
		print("Get Reward")
	end
end)
```

Local Script
```lua
local MarketplaceService = game:GetService("MarketplaceService")
local Player = game.Players.LocalPlayer

local GamepassID = 1965794766 -- create.roblox.com → Creations → 생성할 Experience 선택 → Monetization → Passes → Create pass (Item for sale = On) → Pass ID

local function PromptPurchase()
	local HasPass = false
	
	local Success, ErrorMessage = pcall(function()
		HasPass = MarketplaceService:UserOwnsGamePassAsync(Player.UserId, GamepassID) -- 플레이어가 게임패스를 소유하는지 확인 후 bool 값 반환
	end)
	
	if not HasPass then
		MarketplaceService:PromptGamePassPurchase(Player, GamepassID) -- 게임패스 구매창 띄우기
	end
end

script.Parent.MouseButton1Click:Connect(function()
	PromptPurchase()
end)
```




# 📌 MarketplaceService (Product)
{: .notice}

<pre>
ServerScriptService
└─ Script

StarterGui
└─ ScreenGui
       └─ TextButton
           └─ Local Script
</pre>

Script
```lua
local MarketplaceService = game:GetService("MarketplaceService")

--local ProductID = 012345678

local function ProcessReceipt(ReceiptInfo)
	
	local Player = game.Players:GetPlayerByUserId(ReceiptInfo.PlayerId) -- PlayerID로 해당 플레이어를 찾음
	
	if not Player then
		return Enum.ProductPurchaseDecision.NotProcessedYet -- Roblox에 구매 처리 미완료 알림
	else
		-- 보상 지급 코드 작성--
		
		return Enum.ProductPurchaseDecision.PurchaseGranted -- Roblox에 구매 처리가 완료됐다고 알림
	end
	
end

MarketplaceService.ProcessReceipt = ProcessReceipt -- MarketplaceService.ProcessReceipt에 만든 함수 연결
```

Local Script
```lua
local MarketplaceService = game:GetService("MarketplaceService")
local Player = game.Players.LocalPlayer

local ProductID = 012345678

script.Parent.MouseButton1Click:Connect(function()
	MarketplaceService:PromptProductPurchase(Player, ProductID) -- 구매창 띄우기
end)
```




# 📌 PathfindingService
{: .notice}

<span class="color-control">Workspace</span> <br>
└─<span class="color-string">Model</span> <br>
　 　└─<span class="color-function">Script</span>

```lua
local PathfindingService = game:GetService("PathfindingService")

local NPC = script.Parent
local Humanoid = NPC:WaitForChild("Humanoid")
NPC.HumanoidRootPart.Anchored = false
local StartPoint = NPC.HumanoidRootPart
local EndPoint = game.Workspace.EndPart

local Path = PathfindingService:CreatePath({
	AgentRadius = 2,		-- Agent의 Radius 설정
	AgentHeight = 5,		-- Agent의 Height 설정
	AgentCanJump = false,	-- Agent가 Jump할 수 있는지 설정
	AgentCanClimb = false	-- Agent가 Climb할 수 있는지 설정
})
Path:ComputeAsync(StartPoint.Position, EndPoint.Position) -- Path 계산을 비동기 방식으로 처리

local Waypoints = Path:GetWaypoints()

for i, v in pairs(Waypoints) do
	local Part = Instance.new("Part", game.Workspace) -- 경로를 시각적으로 보여줄 Part
	Part.Name = "Waypoint" .. i
	Part.Position = v.Position + Vector3.new(0, 2, 0)
	Part.Size = Vector3.new(0.3, 0.3, 0.3)
	Part.Color = Color3.new(0, 1, 0)
	Part.Material = Enum.Material.Neon
	Part.Shape = Enum.PartType.Ball
	Part.Anchored = true
	Part.CanCollide = false
	
	if v.Action == Enum.PathWaypointAction.Jump then -- 점프하는 상황의 조건문이지만, AgentCanJump == false 일 경우 조건에서 탈락
		Humanoid:ChangeState(Enum.HumanoidStateType.Jumping) -- 점프 상태로 변경
	end
	
	Humanoid:MoveTo(v.Position) -- 목표 지점으로 이동
	local Success = Humanoid.MoveToFinished:Wait() -- MoveTo가 끝날때 까지 기다리고 이동 결과를 반환
	
	print("이동 결과:", Success)
end
```




# 📌 TeleportService
{: .notice}

<span class="color-control">Workspace</span> <br>
└─<span class="color-string">Part</span> <br>
　 　├─<span class="color-function">ProximityPrompt</span> <br>
　 　└─<span class="color-function">Script</span>

*Place들을 Publish to Roblox 후 실제 게임 내에서 테스트 필요

```lua
local TeleportService = game:GetService("TeleportService")
local PlaceID = 127577925052251 -- Teleport할 Place의 ID, Asset MAnager → Places In Experience → Add New Place → 생성된 Place ID
local ProximityPrompt = script.Parent.ProximityPrompt -- 플레이어가 특정 객체에 가까이 다가갔을 때 상호작용할 수 있도록 화면에 안내 UI를 표시해주는 객체

ProximityPrompt.Triggered:Connect(function(Player)
	TeleportService:TeleportAsync(PlaceID, {Player}) -- Place 이동
end)
```
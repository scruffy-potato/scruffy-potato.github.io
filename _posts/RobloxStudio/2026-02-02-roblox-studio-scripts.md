---
title: "로블록스 스튜디오 스크립트: "
categories: RobloxStudio
# excerpt: ""
---




# 📌 PlayerAdded:Connect
{: .notice}

```Lua
local <Variable Name> = game.Workspace.<Instance Name>

game.Players.PlayerAdded:Connect(function(Player)
	<Variable Name>.Touched:Connect(function(Hit)
		if Hit.Parent:FindFirstChild("Humanoid") then
			Player.Team = game.Teams["<Team Name>"]
		end
	end)
end)
```




# 📌 Table
{: .notice}

```Lua
local <Table Name> = {
	game.Workspace.<Instance Name>,
	game.Workspace.<Instance Name>,
	game.Workspace.<Instance Name>
}

table.insert(<Table Name>, <Value>)
table.remove(<Table Name>, <Index>) -- Index 번째 Value를 지우고 뒤의 값들을 앞당김
<Table Name>[Index] = nil -- Index 번째 Value를 nil값(null)으로 둠
```




# 📌 Function
{: .notice}

```Lua
local function <Function Name>()
	-- Fucntion Body--
end
```




# 📌 Local, Global
{: .notice}

```Lua
local <Variable Name> = <Value> -- local
<Variable Name> = <Value> -- Global
```




# 📌 + String +
{: .notice}

```Lua
local <Variable Name_1> = <Value>
local <Variable Name_2> = <Value>
local <Variable Name_3> = game.StarterGui.<ScreenGui Instance Name>.<TextLabel Instance Name>

<Variable Name_3>.Text = <Variable Name_1> .. "<String Value>" .. <Variable Name_2>
```




# 📌 for
{: .notice}

```Lua
for i = <Start Value>, <End Value>, <Step Value> do
    --For Body--
end
```




# 📌 for i, in pairs
{: .notice}

```Lua
local <Table Name with an s> = {
	game.Workspace.<Instance Name>,
	game.Workspace.<Instance Name>,
	game.Workspace.<Instance Name>
}

for i, <Table Name> in pairs(<Table Name with an s>) do
	<Table Name>.Touched:Connect(function(Hit)
		if Hit.Parent:FindFirstChild("Humanoid") and then
			<Table Name> = <Value>
		end
	end)
end
```




# 📌 Repeat
{: .notice}

```Lua
repeat
	-- Repeat Code --
	task.wait(<Wait Time>)
until <Bool Value>
```




# 📌 IsA, GetChildren
{: .notice}

```Lua
local <Table Name with an s> = game.Workspace.<Folder Name>

for i, <Table Name> in pairs(<Table Name with an s>:GetChildren()) do
	if <Table Name>:IsA("<Class Name>") then -- Check Class Type
		<Table Name>.Touched:Connect(function(Hit)
			local Humanoid = Hit.Parent:FindFirstChild("Humanoid")
			if Humanoid then
				Humanoid.Health = 0 -- Take away Health
			end
		end)
	end
end
```




# 📌 Script, Local Script, Module Script
{: .notice}

<span class="color-keyword">Script</span> 서버에서만 처리해야 할 스크립트. NPC AI, 맵 오브젝트 제어, 플레이어 데이터 처리, 데미지/체력 처리, 게임 룰 등

<span class="color-keyword">Local Script</span> 클라이언트(플레이어) 개인에게서만 필요한 처리를 담당하는 스크립트. 키보드/마우스 Input, UI, 카메라, 플레이어의 화면 효과, 로컬 애니메이션 등

<span class="color-keyword">Module Script</span> 데이터 스크립트로 다른 Script, LocalScript가 가져다 쓰는 코드 모듈

```Lua
-- 다른 스크립트에서 이런식으로 사용
local <Variable Name> = require(game.Workspace.ModuleScript)
<Variable Name>.<Function Name>()
```





# 📌 Sound
{: .notice}

```Lua
local <Variable Name> = game.<Sound Instance Name>

<Variable Name>:Play()
<Variable Name>:Pause()
<Variable Name>:Stop()
```



# 📌 Tool Equipped, Unequipped, Activated
{: .notice}

```Lua
local <Variable Name> = game.StarterPack.<Tool Instance Name>

<Variable Name>.Equipped:Connect(function()
	-- Tool 장착 시
end)

<Variable Name>.Unequipped:Connect(function()
	-- Tool 장착 해제 시
end)

<Variable Name>.Activated:Connect(function()
	-- Tool 장착 상태로 화면 클릭(탭) 시
end)
```




# 📌 Script에서 Instance 접근
{: .notice}

```Lua
game. -- Explorer 접근
script. -- Explorer 내 해당 Script 기준으로 접근
```




# 📌 MouseButton1Click
{: .notice}

```Lua
local <Variable Name> = game.StarterGui.<ScreenGui Instance Name>.<TextButton Instance Name>

<Variable Name>.MouseButton1Click:Connect(function()
	-- 버튼이 클릭됐을 때
end)
```




# 📌 Leaderboard
{: .notice}

```Lua
game.Players.PlayerAdded:Connect(function(Player)
	local LeaderStats = Instance.new("Folder", Player)
	LeaderStats.Name = "leaderstats" -- leaderstats 대소문자에 주의
	
	-- Value Instance를 쓰면 다른 Script에서 쉽게 값에 접근이 가능
	local <Variable Name> = Instance.new("IntValue", LeaderStats)
	<Variable Name>.Name = "<Instance Name>"
	<Variable Name>.Value = <Value>
end)
```




# 📌 ClickDetector
{: .notice}

<pre>
Part
└─ ClickDetector
       └─ Script
</pre>

```Lua
local ClickDetector = script.Parent

ClickDetector.MouseClick:Connect(function(Player)
	-- 해당 Player가 Part를 클릭했을 때를 설정할 수 있음
end)
```




# 📌 MoveTo를 이용해 포탈 만들기
{: .notice}

<pre>
Portals
├─ Script
├─ Protal_1
└─ Protal_2
</pre>

```Lua
local Portals = script.Parent

local Portal_1 = Portals.Portal_1
local Portal_2 = Portals.Portal_2

local Debounce = false

game.Players.PlayerAdded:Connect(function(Player)
	local Character = Player.Character or Player.CharacterAdded:Wait()
	
	Portal_1.Touched:Connect(function(Hit)
		if Hit.Parent:FindFirstChild("Humanoid") and not Debounce then
			Debounce = true
			Character:MoveTo(Portal_2.Position)
			task.wait(2)
			Debounce = false
		end
	end)
end)
```




# 📌 투명해지면서 사라지는 발판 만들기
{: .notice}

```Lua
local Part = script.Parent

local Debounce = false

local function Touched(Duration, Interval) -- 닿으면 투명해지는 함수
	while Part.Transparency < 1 do
		Part.Transparency += (Interval / Duration)
		task.wait(Interval)
	end

	Part.Transparency = 1
end

Part.Touched:Connect(function(hit)
	if Debounce then return end
	
	local character = hit.Parent
	local humanoid = character:FindFirstChild("Humanoid")

	if humanoid then
		Debounce = true
		Touched(4, 0.2)
		Part.CanCollide = false
		task.wait(3)
		Part.CanCollide = true
		Part.Transparency = 0
		Debounce = false
	end
end)
```




# 📌 깜빡이는 발판 만들기
{: .notice}

```Lua
local Part = script.Parent

local Debounce = false

local function ChangeColor(Material_1, Material_2, WaitTime)
	repeat
		task.wait(WaitTime)
		if Debounce == false then
			if Part.Material == Material_1 then Part.Material = Material_2
			else Part.Material = Material_1
			end
		end
	until Part == true and Part ~= nil
end

task.spawn(ChangeColor, Enum.Material.Plastic, Enum.Material.Neon, 1)
```




# 📌 속성 값이 바뀌었을 때 사용하는 함수 Changed
{: .notice}

```Lua
local Part = script.Parent

Part.Changed:Connect(function(Property)
	if Property == "Transparency" then
		print("Transparency Changed")
	end
end)
```




# 📌 Attachment Instance
{: .notice}

Part안에 필요한 Transform을 따로 잡는 용도, Unity의 Empty GameObject와 비슷한 용도




# 📌 ProximityPormpt
{: .notice}

오브젝트에 가까이 갔을 때 상호작용할 수 있게 해주는 Instance

<span class="color-keyword">ActionText</span>

<span class="color-keyword">HoldDuration</span>





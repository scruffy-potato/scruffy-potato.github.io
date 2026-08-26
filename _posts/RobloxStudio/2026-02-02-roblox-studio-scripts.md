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




# 📌 IsA
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
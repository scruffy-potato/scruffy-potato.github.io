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




# 📌 
{: .notice}

```Lua

```
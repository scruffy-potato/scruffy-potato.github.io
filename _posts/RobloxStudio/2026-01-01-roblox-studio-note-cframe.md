---
title: "로블록스 스튜디오 노트: CFrame"
categories: RobloxStudio
# excerpt: ""
---




# 📌 CFrame
{: .notice}

```lua
-- CFrame: Position + Rotation을 하나로 표현하는 데이터
Part.CFrame = CFrame.new(10, 5, 20) * CFrame.Angles(0, math.rad(90), 0)
-- 회전 값 없이 CFrame.new(10, 5, 20)만 넣을 경우 회전 값은 전부 0이 됨
```
---
title: "Emote 만들기"
categories: RobloxStudio
# excerpt: ""
---




# 📌 Animation Asset 만들기
{: .notice}

<span class="color-keyword">Avatar → Clip Editor</span> Animation Editor 창 열기

<span class="color-keyword">Avatar → Character → Rig Type = R15 → Mesh Avatar (2016)</span> 월드에 아바타 생성

<span class="color-keyword">Explorer → Workspace → Rig 선택</span> 생성한 아바타로 Animation Editor 활성화

<span class="color-keyword">Animation Editor</span>

<span class="color-variable">→ Animation Clip 이름 지정</span>

<span class="color-variable">→ Animation track에 부위별 Keyframe을 추가해 애니메이션 생성</span>

<span class="color-variable">→ ... → Set Animation Priority 지정</span>

<span class="color-variable">→ Looping이 필요한 애니메이션의 경우 Toggle looping animation 활성화</span>

<span class="color-variable">→ ... → Save</span>

<span class="color-variable">→ ... → Publish to Roblox</span>

<span class="color-keyword">create.roblox.com → Creations → Development items → Animations → Asset ID를 Animation Istance에 사용</span>




# 📌 R15의 관절 구성
{: .notice}

<span class="color-control">LowerTorso</span>: 최상위 관절로 아바타 자체의 Position, Rotation을 담당 <br>
├─<span class="color-string">LeftUpperLeg</span> ─ LeftLowerLeg ─ LeftFoot <br>
├─<span class="color-string">RightUpperLeg</span> ─ RightLowerLeg ─ RightFoot <br>
└─<span class="color-string">UpperTorso</span> <br>
　 　├─<span class="color-function">Head</span> <br>
　 　├─<span class="color-function">LeftUpperArm</span> ─ LeftLowerArm ─ LeftHand <br>
　 　└─<span class="color-function">RightUpperArm</span> ─ RightLowerArm ─ RightHand <br>

<span class="color-control">Facial Animation</span>: 얼굴 애니메이션의 경우 모든 부위가 상위 관절이 없음




# 📌 Emote 스토어에 등록하기
{: .notice}

<span class="color-keyword">Animation Editor</span>

<span class="color-variable">→ ... → Set Animation Priority = Action</span>

<span class="color-variable">→ Animation Track을 Curve Editor로 전환</span>

<span class="color-variable">→ ... → Publish to Roblox → Create Animation Object In Workspace = Emote</span>

<span class="color-keyword">Workspace → Animation 우클릭(Animation Id가 잘 들어갔는지 확인) → Save / Export → Save to Roblox... → Content Type = Avatar Item, Asset Category = Emote → 게시</span> (80 로벅스)

<span class="color-keyword">create.roblox.com → Creations → Avatar items → Animations → 게시한 Emote Animation으로 들어가 Configure 탭에서 Publish Item</span> (1500 로벅스)
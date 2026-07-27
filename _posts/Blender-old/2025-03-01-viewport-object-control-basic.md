---
title: "뷰포트와 오브젝트 컨트롤 기초"
categories: Blender-old
excerpt: "뷰포트 카메라 컨트롤, 오브젝트 컨트롤"
---




<span style="color:gray">blender version 3.0.0</span>




# 뷰포트 컨트롤
{: .notice}

• <span class="color-keyword">화면 회전(Orbit)</span> : MMB + 마우스 이동

• <span class="color-keyword">화면 이동(Pan)</span> : Shift + MMB + 마우스 이동

• <span class="color-keyword">줌 인/아웃</span> : Ctrl + MMB + 마우스 이동

• <span class="color-keyword">3D 커서 위치 초기화, 모든 오브젝트들을 한 화면에 보이게 함</span> : Shift + C

• <span class="color-keyword">3D 커서 위치 이동</span> : Shift + RMB

• <span class="color-keyword">정면(-Y에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Front Orthographic)</span> : Numpad 1

• <span class="color-keyword">후면(Y에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Back Orthographic)</span> : Ctrl + Numpad 1

• <span class="color-keyword">오른쪽 측면(X에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Right Orthographic)</span> : Numpad 3

• <span class="color-keyword">왼쪽 측면(-X에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Left Orthographic)</span> : Ctrl + Numpad 3

• <span class="color-keyword">상단(Z에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Top Orthographic)</span> : Numpad 7

• <span class="color-keyword">하단(-Z에서 바라보기) 플랫하게 보기</span><span class="color-comment">(Bottom Orthographic)</span> : Ctrl + Numpad 7




# H-ide
{: .notice}

• <span class="color-keyword">오브젝트 뷰포트에서 숨기기</span> : 오브젝트 선택 -> H

• <span class="color-keyword">선택한 오브젝트만 보기</span><span class="color-comment">(다른 오브젝트들을 뷰포트에서 숨김)</span> : 오브젝트 선택 -> Shift + H

• <span class="color-keyword">숨겨진 오브젝트들을 다시 보이게 하기</span> : Alt + H




# G-rab
{: .notice}

<span class="color-comment">마우스 조절 시 Shift 키를 통해 미세 조절 가능</span>

• <span class="color-keyword">오브젝트 Location 수정</span> : 오브젝트 선택 -> G

• <span class="color-keyword">오브젝트 Location 특정 축 수정</span> : 오브젝트 선택 -> G -> X, Y, Z <span class="color-comment">(직접 값을 할당할 수도 있음, 같은 축을 한번 더 선택할 경우 Global 에서 Local 기준으로 전환)</span>

• <span class="color-keyword">오브젝트 Location 특정 축 제외 수정</span> : 오브젝트 선택 -> G -> Shift + X, Y, Z <span class="color-comment">(같은 축을 한번 더 선택할 경우 Global 에서 Local 기준으로 전환)</span>

• <span class="color-keyword">오브젝트 Location 초기화</span> : 오브젝트 선택 -> Alt + G




# R-otation
{: .notice}

<span class="color-comment">마우스 조절 시 Shift 키를 통해 미세 조절 가능</span>

• <span class="color-keyword">오브젝트 Rotation 수정</span> : 오브젝트 선택 -> R

• <span class="color-keyword">오브젝트 Rotation 특정 축 수정</span> : 오브젝트 선택 -> R -> X, Y, Z <span class="color-comment">(직접 값을 할당할 수도 있음, 같은 축을 한번 더 선택할 경우 Global 에서 Local 기준으로 전환)</span>

• <span class="color-keyword">오브젝트 Rotation 초기화</span> : 오브젝트 선택 -> Alt + R




# S-cale
{: .notice}

<span class="color-comment">마우스 조절 시 Shift 키를 통해 미세 조절 가능</span>

• <span class="color-keyword">오브젝트 Scale 수정</span> : 오브젝트 선택 -> S

• <span class="color-keyword">오브젝트 Scale 특정 축 수정</span> : 오브젝트 선택 -> S -> X, Y, Z <span class="color-comment">(직접 값을 배율로 할당할 수도 있음, 같은 축을 한번 더 선택할 경우 Global 에서 Local 기준으로 전환)</span>

• <span class="color-keyword">오브젝트 Scale 특정 축 제외 수정</span> : 오브젝트 선택 -> S -> Shift + X, Y, Z <span class="color-comment">(직접 값을 배율로 할당할 수도 있음, 같은 축을 한번 더 선택할 경우 Global 에서 Local 기준으로 전환)</span>

• <span class="color-keyword">오브젝트 Scale 초기화</span> : 오브젝트 선택 -> Alt + S




# Undo, Redo
{: .notice}

• <span class="color-keyword">Undo</span> : Ctrl + Z

• <span class="color-keyword">Redo</span> : Ctrl + Shift + Z




# Delete
{: .notice}

• <span class="color-keyword">오브젝트 제거</span> : 오브젝트 선택 -> X




# A-dd
{: .notice}

• <span class="color-keyword">Add 창 핫키</span><span class="color-comment">(개체는 3D 커서 위치에 생성)</span> : Shift + A




# D-uplicate
{: .notice}

• <span class="color-keyword">복제</span> : 오브젝트 선택 -> Shift + D




# J-oin
{: .notice}

• <span class="color-keyword">오브젝트들을 하나의 개체로 합치기</span><span class="color-comment">(마지막으로 선택한 오브젝트가 기준이 됨)</span> : Shift + 오브젝트들 선택 -> Ctrl + J

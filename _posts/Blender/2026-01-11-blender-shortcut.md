---
title: "블렌더 단축키"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 세이브 관리
{: .notice}

<span class="color-keyword">Ctrl + Alt + S</span> 세이브 한 경로로 넘버링을 붙이며 세이브




# 📌 오브젝트 관리
{: .notice}

<span class="color-keyword">오브젝트들 선택 → M → New Collection</span> 오브젝트들을 폴더처럼 정리

<span class="color-keyword">오브젝트들 선택 → Ctrl + P → Object</span> Active 오브젝트가 Parent, 그 외 오브젝트들은 Child

<span class="color-keyword">오브젝트들 선택 → Ctrl + P → Object (Keep Transform)</span> 위의 기능에 추가로, Child 오브젝트들이 World Transform이 유지되도록 Local Transform을 보정




# 📌 카메라 컨트롤
{: .notice}

<span class="color-keyword">화면 회전(Orbit)</span> MMB + 마우스 이동

<span class="color-keyword">화면 이동(Pan)</span> Shift + MMB + 마우스 이동

<span class="color-keyword">줌 인/아웃</span> Ctrl + MMB + 마우스 상하 이동

<span class="color-keyword">Right Orthographic(X에서 바라보기)</span> Numpad 3

<span class="color-keyword">Back Orthographic(Y에서 바라보기)</span> Ctrl + Numpad 1

<span class="color-keyword">Top Orthographic(Z에서 바라보기)</span> Numpad 7

<span class="color-keyword">Left Orthographic(-X에서 바라보기)</span> Ctrl + Numpad 3

<span class="color-keyword">Front Orthographic(-Y에서 바라보기)</span> Numpad 1

<span class="color-keyword">Bottom Orthographic(-Z에서 바라보기)</span> Ctrl + Numpad 7

<span class="color-keyword">`</span> Orthographic Viewpoint 를 선택할 수 있는 팝업 창을 커서 위치에 생성




# 📌 Viewport Shading 모드
{: .notice}

<span class="color-keyword">Z</span> 커서 위치에 셰이딩 모드 팝업 창 오픈

<span class="color-keyword">→ Solid</span> 기본 단색(흰색) 모드

<span class="color-keyword">→ Wireframe <span class="color-comment">(Shift + Z)</span></span> 격자 모드

<span class="color-keyword">→ Rendered</span> 렌더링된 모습

<span class="color-keyword">→ Material Preview</span> 재질 미리보기 모드(라이팅 적용)




# 📌 오브젝트 ↔ 에디트 모드 전환
{: .notice}

<span class="color-keyword">Tab</span>




# 📌 X-Ray 모드
{: .notice}


<span class="color-keyword">Alt + Z</span> 엑스레이 뷰 토글 <span class="color-comment">Orthographic viewpoint 일 때 드래그로 뒤쪽 Mesh도 선택할 수 있음</span>




# 📌 사이드 바
{: .notice}

<span class="color-keyword">N</span> 사이드 바 토글 <span class="color-comment">선택한 Vertex 의 Transform 을 볼 수 있음</span>




# 📌 Undo, Redo
{: .notice}

<span class="color-keyword">Ctrl + Z</span> Undo

<span class="color-keyword">Ctrl + Shift + Z</span> Redo




# 📌 마지막 작업 반복
{: .notice}

<span class="color-keyword">Shift + R</span> R-epeat Last




# 📌 추가 선택, 제외 선택
{: .notice}

<span class="color-keyword">Shift + 선택</span> Mesh 추가 선택 <span class="color-comment">Add</span>

<span class="color-keyword">Ctrl + 선택</span> Mesh 제외 선택 <span class="color-comment">Sub</span>




# 📌 3D 커서 컨트롤
{: .notice}

<span class="color-keyword">Shift + RMB</span> 3D 커서 위치 이동

<span class="color-keyword">Shift + C</span> 3D 커서 위치 초기화, 모든 오브젝트들을 한 화면에 보이게 함




# 📌 글로벌, 로컬, 노말
{: .notice}

<span class="color-keyword">,</span> 커서 위치에 Grab, Rotation, Scale을 사용할 때 기준이 되는 좌표축을 정하는 Transform Orientations 팝업 창 생성

<span class="color-variable">→ G 또는 4</span> 블렌더 월드의 Global 좌표를 사용

<span class="color-variable">→ L 또는 6</span> 오브젝트의 Local 좌표를 사용

<span class="color-variable">→ N 또는 2</span> Face Normal 기준으로 사용 <span class="color-comment">Grab 후 Z축을 선택할 경우 Face가 바라보는 Face Normal 방향이 됨</span>




# 📌 Pivot 변경
{: .notice}

<span class="color-keyword">.</span> 커서 위치에 Transform Pivot Point 팝업 창 생성 

<span class="color-variable">Bounding Box Center</span> 선택된 오브젝트의 외곽을 감싸는 최소한의 박스의 중심이 Pivot이 됨

<span class="color-variable">3D Cursor</span> 현재 3D Cursor가 Pivot이 됨

<span class="color-variable">Individual Origins</span> Origin이 Pivot이 됨, 여러 오브젝트를 선택할 때 각각의 오브젝트가 자기 자신의 Origin을 Pivot으로 가짐

<span class="color-variable">Median Point</span> 여러 오브젝트를 선택할 때 오브젝트들의 Origin의 중앙점이 Pivot이 됨

<span class="color-variable">Active Element</span> 여러 오브젝트를 선택할 때 Active 오브젝트의 Origin이 Pivot이 됨




# 📌 도구 단축키
{: .notice}

<span class="color-keyword">W</span> Select Tool <span class="color-variable">Tweak, Select Box, Select Circle, Select Lasso</span>




# 📌 Transform
{: .notice}

G-rab

<span class="color-keyword">Mesh 선택 → G</span> Mesh Location 수정

<span class="color-keyword">Mesh 선택 → G → X, Y, Z</span> Mesh Location 특정 축 수정 <span class="color-comment">같은 축을 한번 더 선택할 경우 Global → Local 전환, 직접 숫자를 입력해 값을 할당할 수 있음</span>

<span class="color-keyword">Mesh 선택 → G → Shift + X, Y, Z</span> Mesh Location 특정 축 제외 수정 <span class="color-comment">같은 축을 한번 더 선택할 경우 Global → Local 전환</span>

<br>

R-otation

<span class="color-keyword">Mesh 선택 → R</span> Mesh Rotation 수정

<span class="color-keyword">Mesh 선택 → R → X, Y, Z</span> Mesh Rotation 특정 축 수정 <span class="color-comment">같은 축을 한번 더 선택할 경우 Global → Local 전환, 직접 숫자를 입력해 값을 할당할 수 있음</span>

<br>

S-cale

<span class="color-keyword">Mesh 선택 → S</span> Mesh Scale 수정

<span class="color-keyword">Mesh 선택 → S → X, Y, Z</span> Mesh Scale 특정 축 수정 <span class="color-comment">같은 축을 한번 더 선택할 경우 Global → Local 전환, 직접 숫자를 입력해 값을 배율로 할당할 수도 있음</span>

<span class="color-keyword">Mesh 선택 → S → Shift + X, Y, Z</span> Mesh Scale 특정 축 제외 수정 <span class="color-comment">같은 축을 한번 더 선택할 경우 Global → Local 전환, 직접 숫자를 입력해 값을 배율로 할당할 수도 있음</span>




# 📌 D-uplicate
{: .notice}

<span class="color-keyword">오브젝트, Mesh 선택 → Shift + D</span> 오브젝트, Mesh 복제




# 📌 Mesh 숨기기/보이기
{: .notice}

<span class="color-keyword">Mesh 선택 → H</span> 선택한 Mesh 숨기기

<span class="color-keyword">Mesh 선택 → Shift + H</span> 선택한 Mesh 제외 숨기기

<span class="color-keyword">Alt + H</span> 모든 숨겨진 Mesh들을 다시 보이게 하기




# 📌 Local View 모드
{: .notice}

<span class="color-keyword">오브젝트 선택 → /</span> 선택한 오브젝트만 보기 <span class="color-comment">토글</span>
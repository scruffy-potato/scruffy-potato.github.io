---
title: "Modifier: Generate"
categories: Blender
excerpt: "Subdivision Surface, Bevel, Mirror, Boolean, Solidify, Array, Wireframe"
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 Subdivision Surface
{: .notice}

표면을 나누어 부드럽게 다듬는 기능

<span class="color-keyword">오브젝트 선택 → Ctrl + 1 ~ 5</span> 원하는 Levels Viewport를 지정해 Modifier를 바로 추가

<span class="color-variable">Levels Viewport</span> 값을 조절해 표면을 나눌 정도를 조절




# 📌 Bevel
{: .notice}

에디트 모드에서 직접 Bevel을 주는 것과 달리 Modifier이기 때문에 원본을 유지한 채로 작업할 수 있다는 장점이 있음

<span class="color-keyword">Angle</span> Face와 Face 사이의 Angle이 | 지정한 Angle보다 큰 Edge만 Bevel 적용

<span class="color-keyword">Weight</span> 에디트 모드에서 Edge마다 사이드 바(N)의 Item → Transform → Edge Data → Bevel Weight의 값을 조절해 원하는 Edge만 Bevel이 적용되게 할 수 있음 <span class="color-comment">Edges를 선택할 경우 Edges Data → Mean Bevel Weight로 표현됨</span>

<span class="color-keyword">Profile → Shape</span> Bevel로 만들어지는 모서리의 단면 형태를 얼마나 둥글게/각지게 만들지 결정 <span class="color-comment">값을 1로 둘 경우 Loop Cut 형태로 사용할 수 있음</span>




# 📌 Mirror
{: .notice}

특정 축 기준으로 대칭 복사

<span class="color-keyword">Clipping</span> 대칭되는 중심에서 Vertex가 겹쳐 붙어 중앙선이 찢어지는 걸 방지할 수 있음

<span class="color-keyword">Merge</span> 대칭 복사된 Vertex가 일정 거리(Merge Distance) 이내에 있을 경우 자동 병합됨




# 📌 Boolean
{: .notice}

Boolean Modifier가 적용된 오브젝트에 다른 오브젝트가 영향을 주어 겹치는 부분만 남기거나, 모델링을 합치거나, 절단하는 기능

<span class="color-keyword">Intersect</span> 영향을 주는 오브젝트와 겹치는 부분만 남김

<span class="color-keyword">Union</span> 영향을 주는 오브젝트와 겹치는 부분을 없애고 하나의 오브젝트로 만듦

<span class="color-keyword">Difference</span> 영향을 주는 오브젝트와 겹치는 부분을 잘라냄




# 📌 Solidify
{: .notice}

두께가 없는 평면적인 Mesh에 실제 두께를 만들어주는 기능




# 📌 Array
{: .notice}




# 📌 Wireframe
{: .notice}

<span class="color-keyword">Plane 생성 → Subdivide로 원하는 격자 형태 생성 → Wireframe Modifier 추가</span>


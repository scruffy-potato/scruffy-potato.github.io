---
title: "Modifier: Generate"
categories: Blender
excerpt: "Subdivision Surface, Mirror, Boolean"
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 Subdivision Surface
{: .notice}

표면을 나누어 부드럽게 다듬는 기능, 오브젝트 선택 → Ctrl + 1~5로 원하는 Levels Viewport를 지정해 Modifier를 바로 추가할 수 있음

• <span class="color-keyword">Levels Viewport</span> : 값을 조절해 표면을 나눌 정도를 조절




# 📌 Mirror
{: .notice}

특정 축 기준으로 대칭 복사

• <span class="color-keyword">Clipping</span> : 대칭되는 중심에서 Vertex가 겹쳐 붙어 중앙선이 찢어지는 걸 방지할 수 있음

• <span class="color-keyword">Merge</span> : 대칭 복사된 Vertex가 일정거리(Merge Distance) 이내에 있을 경우 자동 병합됨




# 📌 Boolean
{: .notice}

Boolean 모디파이어가 적용된 오브젝트에 다른 오브젝트가 영향을 주어 겹치는 부분만 남기거나, 모델링을 합치거나, 절단하는 기능

• <span class="color-keyword">Intersect</span> : 영향을 주는 오브젝트와 겹치는 부분만 남김

• <span class="color-keyword">Union</span> : 영향을 주는 오브젝트와 겹치는 부분을 없애고 하나의 오브젝트로 만듦

• <span class="color-keyword">Difference</span> : 영향을 주는 오브젝트와 겹치는 부분을 잘라냄




# 📌 Solidify
{: .notice}

두께가 없는 평면적인 Mesh에 실제 두께를 만들어주는 기능
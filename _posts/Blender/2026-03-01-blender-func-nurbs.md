---
title: "블렌더 기능: NURBS"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 NURBS *Non-Uniform Rational B-Spline
{: .notice}

Vertex를 직접 이어서 표면을 만드는 Mesh와 달리, 여러 개의 Control Point를 이용해 수학적으로 부드러운 곡선과 표면을 만드는 방식

<span class="color-keyword">1. 오브젝트 모드에서 Shift + A → Curve → Path 생성</span>

<span class="color-keyword">2. 에딧 모드로 들어와 Contrl Point(Vertex)를 G-rab으로 움직이고 E-xtrude로 생성해 원하는 Curve Path 형태를 만듦</span>

<span class="color-keyword">3. 프로퍼티 창 → Data 탭의</span>

<span class="color-variable">3-1. Bevel</span>

<span class="color-variable">3-1-1. Depth</span>

<span class="color-variable">3-1-1. Resolution : 2의 배수(4의 배수), 2일때 8각형이 나옴</span>

<span class="color-variable">3-2. Shape</span>

<span class="color-variable">3-2-1. Resolution Preview U</span>

<span class="color-keyword">4. 모든 작업 후 오브젝트 모드에서 RMB → Convert To → Mesh로 Mesh 타입으로 변경</span>

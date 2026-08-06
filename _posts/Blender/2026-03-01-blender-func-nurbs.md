---
title: "블렌더 기능: NURBS"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 NURBS?
{: .notice}

• <span class="color-keyword">Non-Uniform Rational B-Spline</span> : Vertex를 직접 이어서 표면을 만드는 Mesh와 달리, 여러 개의 Control Point를 이용해 수학적으로 부드러운 곡선과 표면을 만드는 방식

1. 오브젝트 모드에서 Shift + A → Curve → Path 생성

2. 에딧 모드로 들어와 Contrl Point(Vertex)를 G-rab으로 움직이고 E-xtrude로 생성해 원하는 Curve Path 형태를 만듦

3. 프로퍼티 창 → Data 탭의

- Bevel

  + Depth

  + Resolution : 2의 배수(4의 배수), 2일때 8각형이 나옴

- Shape

  + Resolution Preview U

4. 모든 작업 후 오브젝트 모드에서 RMB → Convert To → Mesh로 Mesh 타입으로 변경

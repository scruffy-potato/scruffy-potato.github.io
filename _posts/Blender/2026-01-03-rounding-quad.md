---
title: "R값과 Triangle, Quad, N-gon"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 R값?
{: .notice}

• <span class="color-keyword">R값</span> : 모서리 부분에 라운딩을 줌(곡면을 만듦)




# 📌 Quad(사각형)을 써야하는 이유
{: .notice}

• <span class="color-keyword">Triangle(삼각형), N-gon(오각형 이상)을 쓰지 않고 Quad(사각형)을 써야 하는 이유</span> :

Subdivision Surface(면을 잘게 나누면서 곡면을 만드는 기능)가 가장 깨끗하게 적용됨

그 외에,

Edge Loop가 끊기지 않음

리토폴로지(Retopology)가 쉬워짐

애니메이션에서 변형이 자연스러움

UV 언랩이 쉬워짐

• <span class="color-keyword">Quad(사각형)이 아니어도 되는 예외적인 부분</span> : 

평면일 때

애니메이션 미 적용 시

리깅 사용 안 할 시




# 📌 Quad Topology
{: .notice}

<img src="/img/Blender/topology.png"/>

추가로 마지막에 유독 긴 Quad도 Loop Cut을 이용해 잘라 전체적으로 일정한 Quad 간격을 만들어 주는것이 더 좋은 Topology 형태




# 📌 실린더 4 배수
{: .notice}

<img src="/img/Blender/4-multi-cylinder.png"/>
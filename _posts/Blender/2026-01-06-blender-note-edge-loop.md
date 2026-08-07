---
title: "블렌더 노트: Edge Loop를 넣는 경우와 이유"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 case: Joint
{: .notice}

리깅 후 구부러질 부분(관절)이라면 메시가 찌그러지거나 볼륨이 사라지는 걸 막기 위해 최소 3개 이상, 5개에서 8개까지의 에지 루프를 사용해 부드러운 휘어짐을 만들 수 있다 <span class="color-comment">10개 이상일 경우 매우 부드럽지만 폴리곤의 수가 증가</span>

<img src="/img/Blender/edge-loop-joint.png"/>




# 📌 case: Subdivision Surface
{: .notice}

에지 루프가 적은 곳은 Subdivision Surface를 사용하면 둥글게 퍼져 버린다

에지 루프가 많으면 Subdivision Surface를 사용해도 형태를 잡아주는 역할을 한다




# 📌 case: Shading
{: .notice}

셰이딩 시에 에지 루프가 하나뿐이면 노말 방향이 급격하게 바뀌어 검은 얼룩, 부자연스러운 하이라이트, 셰이딩 깨짐이 생길 수 있다

에지 루프가 여러 개면 노말이 조금씩 변해서 빛이 훨씬 자연스럽게 흐른다
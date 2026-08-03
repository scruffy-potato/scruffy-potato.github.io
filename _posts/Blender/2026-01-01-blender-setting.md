---
title: "Blender Set"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 뉴 파일 디폴트 잡기
{: .notice}

<img src="/img/Blender/new-file-set.png"/>




# 📌 텐키리스 축 뷰 단축키 수정
{: .notice}

<img src="/img/Blender/tenkeyless-axis.png"/>




# 📌 레퍼런스 이미지 사용
{: .notice}

<img src="/img/Blender/ref.png"/>




# 📌 Save Incremental
{: .notice}

• <span class="color-keyword">Ctrl + Alt + S</span> : 세이브 한 경로로 넘버링을 붙이며 세이브




# 📌 Collection
{: .notice}

• <span class="color-keyword">오브젝트들 선택 → M → New Collection</span> : 오브젝트들을 그룹처럼 정리, 오브젝트 파트들을 합치지않고 Collection으로 정리해 후에 수정이 용이하도록 함




# 📌 Set Parent Object
{: .notice}

• <span class="color-keyword">오브젝트들 선택 → Ctrl + P → Object</span> : 선택한 오브젝트들 중 Active 오브젝트가 Parent가 되고 그 외 오브젝트들은 Active 오브젝트의 Child가 됨

• <span class="color-keyword">오브젝트들 선택 → Ctrl + P → Object (Keep Transform)</span> : Child 오브젝트들이 Parent가 생겨도 자신의 World Transform이 유지되도록 Local Transform을 보정해 줌




# 📌 Mesh, Object, Topology, Geometry?
{: .notice}

• <span class="color-keyword">Mesh</span> : Vertex, Edge, Face으로 만들어진 물체

• <span class="color-keyword">Object</span> : Mesh를 포함해 Location, Rotation, Scale, Modifier 등의 정보를 가지는 개체

• <span class="color-keyword">Topology</span> : Mesh가 어떻게 연결되어 있는지에 대한 구조, Quad로 이루어진 형태가 좋은 Topology

• <span class="color-keyword">Geometry</span> : Mesh를 포함해 Curve, Surface, Volume 등 3D 모델이 가진 형태




# 📌 Non-Manifold?
{: .notice}

큐브로 예를 들었을 때, 면이 삭제되어 구멍이 뚫려있는 경우나 내부에 면이 들어가 있는 경우(이 경우들의 공통점은 하나의 Edge에 Face가 두 개가 아닌 한 개, 또는 세 개 이상의 경우)를 Non-Manifold라 지칭

Non-Manifold가 생기면 Subdivision, UV, Shading, 리깅, 애니메이션 중 문제가 생길 수 있음


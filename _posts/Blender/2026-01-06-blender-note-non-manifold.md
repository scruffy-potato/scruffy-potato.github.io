---
title: "블렌더 노트: Non-Manifold"
categories: Blender
# excerpt: ""
---




<span style="color:gray">blender version 5.2.0</span>




# 📌 Non-Manifold
{: .notice}

<span class="color-variable">큐브로 예를 들었을 때</span>

면이 삭제되어 구멍이 뚫려있는 경우, 내부에 면이 들어가 있는 경우를 Non-Manifold라 말한다

<span class="color-variable">이 경우들은 공통적으로</span>

하나의 Edge에 한 개 또는 세 개 이상의 Face가 있는 경우이다

<span class="color-comment">(하나의 Edge에는 두 개의 Face가 있어야 한다)</span>

<span class="color-variable">Non-Manifold가 생기면 발생하는 문제는</span>

Subdivision, UV, Shading, 리깅, 애니메이션 중 문제가 생길 수 있다
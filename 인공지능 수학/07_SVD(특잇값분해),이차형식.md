# 07 SVD(특잇값 분해), 이차형식



### 7-2 특잇값 분해(SVD)



정사각 대칭행렬은 대각화 가능하다. -> 일반적인 m * n 행렬의 대각화? -> 특잇값 분해



* 특잇값 분해 : 행렬 A가 m * n의 실수 행렬이면 다음과 같은 직교 행렬 U, V와 대각선행렬 Σ 존재



![image](https://user-images.githubusercontent.com/89879599/149705624-71201237-607f-41b9-8c45-686befdcec30.png)



Σ1은 주대각성분이 모두 **단조감소의 순서**로 배열된 양수이고, 가역인 대각선행렬 O는 영행렬이다. 



* n * n 크기의 행렬 A가 가역행렬이가 위한 필요충분조건 : 행렬의 특이값들이 모두 0이 아니다. 



* 행렬 A가 가역이기 위한 필요충분조건 : det(A A^T) = (det A)^2 != 0 이므로 A A^T 가역



* 특잇값 : Σ의 대각선 성분들



left singular vector : U의 열들 / right singular vector : V의 열들



### 7-3 일반화된 역행렬



![image](https://user-images.githubusercontent.com/89879599/149706852-2350051c-f88e-44c3-a00d-ab60012d38ac.png)



일반화된 역행렬 : 행렬 A가 크기가 m * n인 경우 크기 n * m인 행렬 A^+를 행렬 A의 **pseudo-inverse**라 한다. (U, V는 직교행렬)




* full column rank를 갖는 m * n 행렬의 pseudo-inverse : 행렬 A가 n개의 열이 모두 일차독립인 full column rank를 갖는 m * n 행렬이면 Ax = b의 양변에 A^T를 곱한 식을 **정규방정식**이라하고, 이는 언제나 **유일해** x = (A^T A)^-1 A^T b를 갖는다. 이때 A^+ = (A^T A)^-1 A^T를 A의 **pseudo-inverse**라 한다. 

```
(A.transpose()*A).inverse()*A.transpose()
```

* 최소제곱해 : A가 m * n 행렬이고 b는 R^n의 임의의 벡터이면, **x = A^+ b**는 Ax = b의 최소제곱해이다. least square line



### 7-4 이차형식



* R^2 상의 이차형식



![image](https://user-images.githubusercontent.com/89879599/149708508-888e037e-d29c-4669-a35d-c114939dc4d7.png)



* R^n 상의 이차형식 : A = [aij]가 n차의 대칭행렬이고, n개의 변수 x를 성분으로 갖는 R^n의 벡터 x에 대한 이차다항식



![image](https://user-images.githubusercontent.com/89879599/149708799-9e828ab7-a5f5-4cad-9b1d-a2849712c82d.png)



* 행렬 A는 대칭행렬 B와 반대칭 행렬 C의 합으로 표시된다. A = (A + A^T) / 2 + (A - A^T) / 2



q(x) = x^T Ax = x^T Bx이므로 (C 사라짐) 이차형식 값은 주어진 행렬의 대칭부분에만 의존하므로 일반성을 잃지 않고 정의에서부터 A를 대칭행렬으로 정의한다. 이차형식에 관한 연구의 많은 부분은 **대칭행렬 A는 언제나 직교대각화 가능하다**는 사실과 밀접한 연관이 있다. 



대칭행렬의 직교화를 이용하면 교차항(이차형식의 xy항)을 제거할 수 있다. 



* 행렬 A가 대칭행렬일 때 A의 이차형식 q(x) = x^T Ax는 다음을 만족한다. (극대값, 극소값 바로 판별 가능)

```
1. A의 고윳값들이 모두 양이라면 q(x)는 양의 정부호이다.
2. A의 고윳값들이 모두 음이라면 q(x)는 음의 정부호이다.
3. A가 양과 음의 고윳값을 모두 가지면 q(x)는 부정부호이다.
```



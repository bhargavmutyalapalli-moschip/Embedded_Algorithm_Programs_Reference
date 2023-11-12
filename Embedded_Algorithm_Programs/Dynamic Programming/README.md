# 동적 계획법 정리 내용

## 동적 계획법 개요
동적 계획법은 2차 세계대전 직후 개발된 알고리즘 설계 기법이다.
<br>
원래는 효율적 의사 결정을 위해 만들어진 기법이다.
<br>
<br>
하지만 장점이 많은 기법이다 보니 현재는 컴퓨터 과학, 경제, 생명공학, 항공우주 공학 등 다양한 분야에서 활용되고 있다.

<br>

## 동적 계획법 탄생 배경
2차 세계대전을 치르는 동안 미국은 전쟁에서 승리할 수 있는 모든 방법을 강구했고 그중 대표적인 것이 원자 폭탄 개발을 위한 맨해튼 프로젝트였다.
<br>
미국은 이런 '물리적' 무기 연구뿐 아니라 레이더 운용 문제, 함대 배치 문제, 대잠수함 작전 문제, 수송 문제 등 군사 작전 자체에 대한 연구에도 수학자를 비롯하여 많은 과학자를 투입하는 등 큰 투자를 했다.
<br>
<br>
이 연구들은 전쟁이 끝난 후 OR(Operation Research) 이라는 학문으로 발전했다.
<br>
<br>
이때 이루어진 연구 중 하나가 바로 다단계 의사 결정 문제(Multistage Decision Problem)이다.
<br>
1940년대 미공군에 의해 설립된 연구 조직인 RAND(Reasearch And Development)는 이 문제에 관심을 갖고 있었다.
<br>
마침 RAND에서 컨설팅을 진행하고 있던 스탠포드 대학의 리처드 벨만(Richared Bellman) 교수에게 연구를 의뢰했다.
<br>
<br>
벨만 교수는 다단계 의사 결정 문제를 본격적으로 연구하기 전에 이 연구를 위한 새로운 이름이 필요하다고 느꼈다.
<br>
그래서 새로운 이름을 위해 가장 처음 떠올린 낱말은 의사 결정 '계획법(Planning)' 이었다.
<br>
처음 생각했던 Planning 대신 Programming이라는 낱말을 사용하기로 했다.
<br>
<br>
벨만 교수는 이 단계적 의사 결정이 '동적(Dynamic)'으로 이루어진다는 사실을 알리고 싶었다.
<br>
다단계 의사 결정은 말 그대로 단계예 따라 동적으로 의사 결정을 하는 방법이었기 때문이다.
<br>
의미를 잘 전달할 뿐만 아니라 용법도 형용사이기 때문에 '계획법' 앞에 붙이면 딱 들어맞는 이름을 만들 수 있었다.
<br>
<br>
이렇게 해서 동적 계획법이라는 이름이 탄생했다.
<br>
그리고 벨만 교수는 동적 계획법을 연구하여 1952년에 발표하였다.

<br>

## 동적 계획법의 개념
동적 계획법이란 어떤 문제가 여러 단계의 반복되는 부분 문제로 이루어졌을 때, 각 단계에 있는 부분 문제의 답을 기반으로 전체 문제의 답을 구하는 방법을 말한다.
<br>
동적 계획법은 **한 번 푼 적 있는 부분 문제의 당블 다시 푸는 일이 없도록 테이블 등에 저장하는 부분**이 중요한 부분이다.
<br>
<br>
동적 계획법으로 알고리즘을 설계할 때 부분 문제의 답을 저장하는 테이블을 빼놓으면 안 된다.
<br>
이 테이블이 없으면 부분 문제들의 답을 수없이 반복해서 다시 구하는 일이 생길 수도 있기 때문이다.
<br>
<br>
동적 계획법으로 설계된 알고리즘의 동작 방식은 다음 세 단계로 정리된다.

1. 문제를 부분 문제로 나눔
2. 가장 작은 부분 문제부터 해를 구한 뒤 테이블에 저장
3. 테이블에 저장된 부분 문제의 해를 이용하여 점차적으로 상위 부분 문제의 최적해를 구함

동적 계획법으로 풀 수 있는 문제의 종류는 한정되어 있다.
<br>
동적 계획법을 이용하여 문제를 풀기 위해서는 그 **문제가 '최적 부분 구조(Optimal Substructure)'를 갖추어야 한다는 조건을 충족**해야 한다.
<br>
<br>
최적 부분 구조란 **전체 문제의 최적해가 부분 문제의 최적해로부터 만들어지느 구조**를 말한다.
<br>
<br>
예를 들어 5개의 작은 문제로 쪼갤 수 있는 어떤 문제가 쪼개진 문제의 해 5개를 모두 얻어야 이 문제의 해를 구할 수 있다면 이 문제는 최적 부분 구조를 갖추었다고 할 수 있다.

<br>

## 동적 계획법 기반 피보나치 수 구하기

피보나치 수는 선행되는 피보나치 수를 구해야 다음 피보나치 수를 구할 수 있으므로 최적 부분 구조를 갖추고 있다고 말할 수 있다.

<br>

### 동적 계획법으로 피보나치 수를 구하는 방법
피보나치 수는 다음의 점화식으로 정의할 수 있다.

<br>

![image](https://github.com/JeHeeYu/Book-Reviews/assets/87363461/6196e04e-9c62-4bee-ba1b-94108905e018)

<br>

이 점화식을 C언어 코드로 옮기면 다음과 같은 함수를 만들 수 있다.
<br>
물론 이 알고리즘의 수행 시간은 O(n^2)으로 사용하기 어려운 수준이다.

<br>


```
ULONG Fibonacci(int n)
{
    if(n == 0)
        return 0;
    
    if(n == 1 || n == 2)
        return 1;
        
    return Fibonacci(n - 1) + Fibonacci(n - 2);
}
```

<br>

이 알고리즘이 사용하기 어려운 이유는 부분 피보나치 수를 얻기 위한 중복 계산이 수없이 이루어지기 때문이다.
<br>
예를 들어 Fibonacci(n-4)는 4번, Fibonacci(n-3)은 3번이나 반복해서 계산이 수행되고 있다.

<br>

![image](https://github.com/JeHeeYu/Book-Reviews/assets/87363461/85e332e8-739d-481e-9115-619a57f5cf0e)


<br>

동적 계획법으로 문제를 풀기 위해서는 제일 먼저 이 문제가 최적 부분 구조로 이루어져 있는지 부터 확인해야 한다.
<br>
피보나치 수는 부분 문제의 답에서 전체 문제의 답을 얻을 수 있으므로 최적 부분 구조로 이루어져 있다고 할 수 있다.
<br>
<br>
동적 계획법을 사용할 수 있다는 사실을 확인했으니 다음과 같은 동적 계획법의 세 단계로 풀어나가면 된다.

1. 문제를 부분 문제로 나눔
2. 가장 작은 문제부터 해를 구한 뒤 테이블에 저장
3. 테이블에 저장된 부분 문제의 해를 이용하여 점차적으로 상위 부분 문제의 최적해를 구함

이 절차를 피보나치 수 구하기 문제에 적용해서 문제를 풀 수 있다.
<br>
Fibonacci(n) 함수는 Fibonacci(n-1)과 Fibonacci(n-2)의 합이다.
<br>
Fibonacci(n-1)은 Fibonacci(n-2)와 Fibonacci(n-3)의 합이기도 하다.
<br>
<br>
그리고 Fibonacci(2)는 Fibonacci(1)과 Fibonacci(0)의 합이다.
<br>
이러한 사실에서 Fibonacci(n)이라는 문제가 Fibonacci(n-1), Fibonacci(n-2), ... Fibonacci(2), Fibonacci(1), Fibonacci(0)의 부분 집합으로 나뉜다는 새로운 사실을 알 수 있다.
<br>
<br>
부분 문제로 나누는 일을 끝냈다면 가장 작은 문제부터 해를 구해 나간다.
<br>
물론 그 결과는 테이블에 저장된다.

<br>

![image](https://github.com/JeHeeYu/Book-Reviews/assets/87363461/13b02626-5b19-4a87-8fc1-bbc516b1c951)


<br>

Fibonacci(0)과 Fibonacci(1)은 따로 계산할 것 없이 이미 정의되어 있는 값을 테이블의 0번과 1번 인덱스에 넣어놓고, Fibonacci(2)부터 방금 테이블에 저장한 값을 이용하여 차그나근 테이블을 완성해나간다.
<br>
Fibonacci(2)는 테이블의 0번과 1번에 저장된 값을 더해서 그 결과를 2번 인덱스에, Fibonacci(3)은 테이블의 2번과 1번에 저장된 값을 이용해서 3번 인덱스에 저장한다.
<br>
<br>
이런 식으로 Fibonacci(n)을 구할 때까지 테이블에서 이전 피보나치 수를 참조하여 계산을 반복한다.
<br>
<br>
테이블을 모두 완성하면 n번째 요소의 값이 Fibonacci(n)의 결과가 된다.
<br>
이렇게 찾고자 하는 n번째 피보나치 수 계산이 끝난다.

<br>

## 동적 계획법 기반 피보나치 수 구하기 알고리즘 구현

다음 코드가 동적 계획법 버전 Fiboancci() 함수이다.

```
ULONG Fibonacci(int n)
{
    int i;
    
    ULONG result;
    ULONG* fibonacciTable;
    
    if(n == 0 || n == 1) {
        return n;
    }
    
    fibonacciTable = (ULONG*)malloc(sizeof(ULONG) * (n + 1));
    
    fibonacciTable[0] = 0;
    fibonacciTable[1] = 1;
    
    for(i = 2; i <= n; i++) {
        fibonacciTable[i] = fibonacciTable[i - 1] + fibonacciTable[i - 2];
    }
    
    result = fibonacciTable[n];
    
    free(fibonacciTable);
    
    return result;
}
```

### [동적 계획법을 이용한 피보나치 예제 코드](https://github.com/JeHeeYu/Algorithm/blob/main/Dynamic%20Programming/FibonacciDP.c)

### 실행 결과
```
46
Fibonacci(46) = 1836311903

10
Fibonacci(10) = 55

20
Fibonacci(20) = 6765
```
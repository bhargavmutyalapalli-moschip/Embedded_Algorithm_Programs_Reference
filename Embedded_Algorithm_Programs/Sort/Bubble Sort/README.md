# 버블 정렬(Bubble Sort)

## 요약
### 시간 복잡도 : O(n) = n^2
<li>인접한 두 요소의 대소 관계를 비교하여 반복 교환</li>
<li>시간 복잡도가 느리지만, 코드가 단순하여 구현이 쉬워 자주 사용</li>
<li>요소의 개수가 n개인 배열에서 n - 1회 비교, 교환을 하고 나면 가장 작은 요소가 맨 처음 또는 끝으로 이동</li>
<li>비교, 교환 과정을 패스라고 함</li>
</ul>

## 버블 정렬이란
인접한 두 요소의 대소 관계를 비교하여 교환을 반복하는 것을 말한다.
<br>
시간 복잡도가 상당히 느리지만, 코드가 단순하여 구현이 쉽기 때문에 자주 사용된다.
<br>
원소의 이동이 거품이 수면으로 올라오는 듯한 모습을 보이기 때문에 버블 이라는 이름이 붙었다.
<br>
<br>
버블 정렬은 정렬을 앞에서 시작할 수도 있고, 뒤부터 시작할 수도 있지만, 요소의 끝부터 확인하고 정렬해야 한다.
<br>
먼저 7개의 크기를 가진 배열이 있다고 가정하고, 오름차순인지, 내림차순인지 알아야 한다.
<br>
<br>
<img src="https://user-images.githubusercontent.com/87363461/201458701-e019bf77-fce6-4cad-b02f-7da60ac2c783.JPG" width="400" height="150">
<br>
<br>
차례대로 뒤의 원소부터 8과 9를 비교하여 큰 값을 오른 쪽으로 이동, 다시 8과 1을 비교하여 큰 값이 오른쪽으로 이동을 반복한다.
<br>
두 값중 큰 값이 오른쪽에 있을 경우 별다른 동작을 하지 않고 다음 동작을 이어간다.
<br>
<br>
즉, 요소의 개수가 n개인 배열에서 n - 1회 비교, 교환을 하고 나면 가장 작은 요소가 맨 처음으로 이동한다.
<br>
이러한 일련의 과정(비교, 교환)을 패스(Pass)라고 한다.
<br>
<br>
<img src="https://user-images.githubusercontent.com/87363461/201458787-67ce5eda-1118-45e4-b5b2-1dd851d00d3b.JPG" width="600" height="500">
<br>
<br>
제일 작은 값이 맨 처음 요소로 이동했으니, 이후 배열의 값을 비교하여 교환하여야 한다.
<br>
배열의 2번째 이후 요소에 대해 패스 작업을 수행한다.
<br>
<br>
<img src="https://user-images.githubusercontent.com/87363461/201458867-b57a994d-03df-45c8-a93f-ab7c8d9601dd.JPG" width="600" height="500">
<br>
<br>
패스를 수행하고 나면 3의 배열은 2번째 자리로 이동하고 그 결과 두 요소의 정렬이 끝난다ㅏ.
<br>
두 번째 패스의 비교 횟수는 첫 번째 횟수보다 적은 n - 2회이다. 그 이유는 패스를 수행할 때마다 정렬할 요소가 하나씩 줄어즐기 때문이다.
<br>
패스를 j회 수행하면 앞쪽의 요소 j개가 정렬되고, 모든 절열이 끝나려면 n - 1회의 패스가 수행되어야 한다.


## 문제 해결
버블 정렬 알고리즘 프로그램은 i 값을 0부터 n - 2까지 1씩 증가하며, n - 1회의 패스를 수행해야 한다.
<pre>
for(i = 0; i < n - 1; i++) {
    // 끝에서부터 앞쪽으로 스캔하면서 이웃하는 두 요소를 비교하고 교환함
}
</pre>
<img src="https://user-images.githubusercontent.com/87363461/201458955-23d2155c-bab5-4b02-b1f8-ca6d3239c817.JPG" width="500" height="300">
<br>
<br>
비교하는 두 요소 중에서 오른쪽 요소의 인덱스는 i + 1이 될 때까지 감소하고, 왼쪽 요소는 인덱스가 i가 될 때까지 감소한다.
<br>
이렇게 서로 이웃한 요소에 대해서만 교환하므로 버블 정렬 알고리즘은 안정적인 알고리즘이라고 할 수 있다.
<br>
<br>
버블 정렬의 비교 횟수 합계는 다음과 같다.
<pre>
(n - 1) + (n - 2) + ... + 1 = n(n - 1) / 2
</pre>

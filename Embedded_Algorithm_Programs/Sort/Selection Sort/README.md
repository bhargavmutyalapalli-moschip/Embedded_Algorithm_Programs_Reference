# 선택 정렬(Selection Sort)

## 요약

### 시간 복잡도 : O(n ^ 2)

<ol>
<li>가장 작은 요소부터 선택해 알맞은 위치로 옮겨서 순서대로 정렬하는 정렬 알고리즘</li>
<li>배열의 가장 작은 값을 찾아 맨 처음 요소와 위치를 변경하는 작업을 반복하여 정렬을 수행</li>
<li>같은 값이 있을 경우 상대적인 위치가 변경될 수 있어 안전하지 않음</li>
<li>배열의 크기를 알고 있기 때문에 이동 횟수를 미리 알 수 있다는 장점이 있음</li>
</ol>

## 단순 선택 정렬이란
단순 선택 정렬이란 가장 작은 요소부터 선택해 알맞은 위치로 옮겨서 순서대로 정렬하는 정렬 알고리즘이다.
<br>
어떤 배열이 있을 때, 배열의 가장 작은 값을 찾아 맨 처음 요소와 위치를 변경하는 작업을 반복하여 정렬을 수행한다.
<br>
<br>
<img src="https://user-images.githubusercontent.com/87363461/201461243-393ffed5-551f-4f72-9ec5-4a4e5f5a0916.JPG" width="600" height="300">
<br>
<ol>
<li>배열에서 가장 작은 값 1을 찾아 0번째 인덱스 6과 위치를 교환한다.</li>
<li>1번째 인덱스부터 가장 작은 값 3을 찾아 정렬되지 않은 2번째 인덱스 4와 위치를 교환한다.</li>
<li>2번째 인덱스부터 가장 작은 값 4을 찾아 정렬되지 않은 3번째 인덱스 8와 위치를 교환한다.</li>
<li>3번째 인덱스부터 가장 작은 값 6을 찾아 정렬되지 않은 4번째 인덱스 8와 위치를 교환한다.</li>
<li>4번째 인덱스부터 가장 작은 값 7을 찾아 정렬되지 않은 5번째 인덱스 8와 위치를 교환한다.</li>
<li>5번째 인덱스부터 가장 작은 값 8을 찾아 정렬되지 않은 6번째 인덱스 8와 위치를 교환한다.</li>
<li>마지막 인덱스 9가 가장 낮은 값이므로 정렬이 완성된다.</li>
</ol>


이렇게 단순 선택 정렬의 교환 과정은 2단계로 나뉜다.
<ol>
<li>배열에서 가장 작은 값을 선택</li>
<li>절열하지 않은 앞쪽의 요소와 교환</li>
</ol>
<br>
위 과정을 n - 1회 반복하면 선택 정렬이 완성된다.

## 단점
선택 정렬은 서로 떨어져 있는 요소를 교환하는 것이기 때문에 안정적이지 않다.
<br>
만약 중복되는 값이 있을 경우 요소의 위치가 뒤바뀌기 때문이다.
<br>
<br>
<img src="https://user-images.githubusercontent.com/87363461/201461769-9971565b-e5f4-4592-81bd-fd65a6f24a56.JPG" width="300" height="300">

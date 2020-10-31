## 📌 Algorithm
📖 Contents

- [Sorting-Algorithm](#Sorting-Algorithm)
- [Dijkstra](#Kruskal-MST-알고리즘)
- [Bellman-Ford](#Bellman-Ford-알고리즘)
- [Kruskal](#Kruskal-MST-알고리즘)

#

### Sorting-Algorithm
Sorting 알고리즘은 크게 Comparisons 방식과 Non-Comparisons 방식으로 나눌 수 있다. 

#### Comparisons Sorting Algorithm (비교 방식 알고리즘)
- `Bubble Sort`, `Selection Sort`, `Insertion Sort`, `Merge Sort`, `Heap Sort`, `Quick Sort`
<br>

#### Bubble Sort

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(1)       |     O(n^2)      |
<br>

#### Selection Sort

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(1)       |     O(n^2)      |
<br>

#### Insertion Sort

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(1)       |     O(n^2)      |
<br>

#### Merge Sort

기본적인 개념으로는 n 개의 원소를 가진 배열을 정렬할 때, 정렬하고자 하는 배열의 크기를 작은 단위로 나누어 정렬하고자 하는 배열의 크기를 줄이는 원리를 사용한다. `Divide and conquer`라는, "분할하여 정복한다"의 원리인 것이다. 말 그대로 복잡한 문제를 복잡하지 않은 문제로 분할하여 정복하는 방법이다. 단 분할(divide)해서 정복했으니 정복(conquer)한 후에는 **결합(combine)** 의 과정을 거쳐야 한다.

`Merge Sort`는 더이상 나누어지지 않을 때 까지 **반 씩(1/2)** 분할하다가 더 이상 나누어지지 않은 경우(원소가 하나인 배열일 때)에는 자기 자신, 즉 원소 하나를 반환한다. 원소가 하나인 경우에는 정렬할 필요가 없기 때문이다. 이 때 반환한 값끼리 **`combine`될 때, 비교가 이뤄지며,** 비교 결과를 기반으로 정렬되어 **임시 배열에 저장된다.** 그리고 이 임시 배열에 저장된 순서를 합쳐진 값으로 반환한다. 실제 정렬은 나눈 것을 병합하는 과정에서 이뤄지는 것이다.

결국 하나씩 남을 때까지 분할하는 것이면, 바로 하나씩 분할해버리면 되지 않을까? 재귀적으로 정렬하는 원리인 것이다. 재귀적 구현을 위하 1/2 씩 분할한다.

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(n)       |    O(nlogn)     |
<br>

#### Heap Sort 

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(1)       |    O(nlogn)     |
<br>

#### Quick Sort

Sorting 기법 중 가장 빠르다고 해서 quick 이라는 이름이 붙여졌다. **하지만 Worst Case 에서는 시간복잡도가 O(n^2)가 나올 수도 있다.** 하지만 `constant factor`가 작아서 속도가 빠르다.

`Quick Sort` 역시 `Divide and Conquer` 전략을 사용하여 Sorting 이 이루어진다. Divide 과정에서 `pivot`이라는 개념이 사용된다. 입력된 배열에 대해 오름차순으로 정렬한다고 하면 이 pivot 을 기준으로 좌측은 pivot 으로 설정된 값보다 작은 값이 위치하고, 우측은 큰 값이 위치하도록 `partition`된다. 이렇게 나뉜 좌, 우측 각각의 배열을 다시 재귀적으로 Quick Sort 를 시키면 또 partition 과정이 적용된다.이 때 한 가지 주의할 점은 partition 과정에서 pivot 으로 설정된 값은 다음 재귀과정에 포함시키지 않아야 한다. 이미 partition 과정에서 정렬된 자신의 위치를 찾았기 때문이다.

| Space Complexity | Time Complexity |
| :--------------: | :-------------: |
|       O(log(n))       |    O(nlogn)     |

<br>

#### non-Comparisons Sorting Algorithm 
- `Counting Sort`, `Radix Sort`

<br>

#### Sorting Algorithm's Complexity 정리

|   Algorithm    | Space Complexity | (average) Time Complexity | (worst) Time Complexity |
| :------------: | :--------------: | :-----------------------: | :---------------------: |
|  Bubble sort   |       O(1)       |          O(n^2)           |         O(n^2)          |
| Selection sort |       O(1)       |          O(n^2)           |         O(n^2)          |
| Insertion sort |       O(1)       |          O(n^2)           |         O(n^2)          |
|   Merge sort   |       O(n)       |         O(nlogn)          |        O(nlogn)         |
|   Heap sort    |       O(1)       |         O(nlogn)          |        O(nlogn)         |
|   Quick sort   |       O(1)       |         O(nlogn)          |         O(n^2)          |
|   Count sort   |       O(n)       |           O(n)            |          O(n)           |
|   Radix sort   |       O(n)       |           O(n)            |          O(n)           |

<br>

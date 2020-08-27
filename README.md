# tech-interview-for-developer
👶🏻 신입 개발자 전공 지식




### 📌 Algorithm
📖 Contents

- 다익스트라
- [Kruskal](#Kruskal-MST-알고리즘)

#

### Kruskal MST 알고리즘

#### Kruskal MST 알고리즘이란
탐욕적인 방법(greedy method) 을 이용하여 네트워크(가중치를 간선에 할당한 그래프)의 모든 정점을 최소 비용으로 연결하는 최적 해답을 구하는 것

- MST(최소 비용 신장 트리) 가 1) 최소 비용의 간선으로 구성됨 2) 사이클을 포함하지 않음 의 조건에 근거하여 각 단계에서 사이클을 이루지 않는 최소 비용 간선을 선택 한다.
- 간선 선택을 기반으로 하는 알고리즘이다.
- 이전 단계에서 만들어진 신장 트리와는 상관없이 무조건 최소 간선만을 선택하는 방법이다.


#### 과정
  - 그래프의 간선들을 가중치의 오름차순으로 정렬한다.
  - 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택한다.
      - 즉, 가장 낮은 가중치를 먼저 선택한다.
      - 사이클을 형성하는 간선을 제외한다.
  - 해당 간선을 현재의 MST(최소 비용 신장 트리)의 집합에 추가한다.

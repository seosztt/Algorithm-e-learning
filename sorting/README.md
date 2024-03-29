# 정렬

- 데이터를 특정한 기준에 따라 순서대로 나열하는 것
- 일반적으로 문제 상황에 따라서 적절한 정렬 알고리즘이 공식처럼 사용됩니다.

## 선택 정렬

- 처리되지 않은 데이터 중에서 가장 작은 데이터를 **선택**해 맨 앞에 있는 데이터와 바꾸는 것을 반복합니다.
- 시간 복잡도: O(N^2)



## 삽입 정렬

- 처리되지 않은 데이터를 하나씩 골라 적절한 위치에 **삽입**합니다.
- 선택 정렬에 비해 구현 난이도가 높은 편이지만, 일반적으로 더 효율적으로 동작합니다.
- 시간 복잡도: O(N^2)
- 삽입 정렬은 현재 리스트의 데이터가 거의 정렬되어 있는 상태라면 매우 빠르게 동작합니다.
  - 최선의 경우 O(N)의 시간 복잡도를 가집니다. (이미 정렬되어있는 성태)



## 퀵 정렬

- 기준 데이터를 설정하고 그 기준보다 큰 데이터와 작은 데이터의 위치를 바꾸는 방법입니다.
- 일반적인 상황에서 가장 많이사용되는 정렬 알고리즘 중 하나입니다.
- 병합 정렬과 더불어 대부분의 프로그밍 언어의 정렬 라이브러리의 근간이 되는 알고리즘입니다.
- 가장 기본적인 퀵 정렬은 첫 번째 데이터를 기준 데이터(Pivot)로 설정합니다.
- 평균 O(NlogN)의 시간 복잡도를 가집니다.
- 최악의 경우 O(N^2)의 시간 복잡도를 가집니다.
  - 첫 번째 원소를 피벗으로 삼을 때, 이미 정렬된 배열에 대해서 퀵정렬을 수행는 경우



## 계수 정렬

- 특정한 조건이 부합할 때만 사용할 수 있지만 **매우 빠르게 동작**하는 정렬 알고리즘입니다.
  - 계수 정렬은 데이터의 크기 범위가 제한되어 정수 형태로 표현할 수 있을 대 사용 가능합니다.
- 데이터의 개수가 N, 데이터(양수) 중 최댓값이 K일 때 최악의 경우에도 수행 시간 O(N+K)를 보장합니다.
- 시간복잡도와 공복잡도 모두 O(N+K)입니다.
- 계수 정렬은 때에 따라서 심각한 비효율성을 초래할 수 있습니다.
  - 데이터가 0과 999,999로 단 2개만 존재하는 경우를 생각해봅시다.
- 계수 정렬은 동일한 값을 가지는 데이터가 여러 개 등장할 때 효과적으로 사용할 수 있습니다.
  - 성적의 경우 100점을 맞은 학생이 여러 명일 수 있기 때문에 계수 정렬이 효과적입니다.



## 위상 정렬

- **사이클이 없는 방향 그래프**의 모든 노드를 **방향성에 거스르지 않도록 순서대로 나열**하는 것을 의미합니다.

### 진입차수와 진출차수

- **진입차수(Indegree)**: 특정한 노드로 들어오는 간선의 개수
- **진출차수(Outdegree)**: 특정한 노드에서 나가는 간선의 개수

### 위상 정렬 알고리즘

- **큐**를 이용하는 **위상 정렬 알고리즘의 동작 과정**은 다음과 같습니다.
  1. 진입차수가 0인 모든 노드를 큐에 넣는다.
  2. 큐가 빌 때까지 다음의 과정을 반복한다.
     1. 큐에서 원소를 꺼내 해당 노드에서 나가는 간선을 그래프에서 제거한다.
     2. 새롭게 진입차수가 0이 된 노드를 큐에 넣는다.
- 결과적으로 **각 노드가 큐에 들어온 순서가 위상 정렬을 수행한 결과**와 같습니다.

### 위상 정렬의 특징

- 위상 정렬은 DAG에 대해서만 수행할 수 있습니다.
  - **DAG (Direct Acyclic Graph)**: 순환하지 않는 방향 그래프
- 위상 정렬에서는 **여러 가지 답이 존재**할 수 있습니다.
  - 한 단계에서 큐에 새롭게 들어가는 원소가 2개 이상인 경우가 있다면 여러 가지 답이 존재합니다.
- **모든 원소를 방문하기 전에 큐가 빈다면 사이클이 존재**한다고 판단할 수 있습니다.
  - 사이클에 포함된 원소 중에서 어떠한 원소도 큐에 들어가지 못합니다.
- 스택을 활용한 DFS를 이용해 위상 정렬을 수행할 수도 있습니다.

### 위상 정렬 알고리즘 성능 분석

- 위상 정렬을 위해 차례대로 모든 노드를 확인하며 각 노드에서 나가는 간선을 차례대로 제거해야 합니다.
  - 위상 정렬 알고리즘의 시간 복잡도는 O(V+E)입니다.

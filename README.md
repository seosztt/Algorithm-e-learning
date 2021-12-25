# 자료구조

## 스택(stack)

- 선입후출
- 입구와 출구가 동일한 형태
- python에서는 list

## 큐(queue)

- 선입선출

- 입구와 출구가 모두 뚤려있는 터널과 같은 형태

- python에서는

  ```python
  from collectioins import deque
  queue = deque()
  ```

## 우선순위 큐(Priority Queue)

- 우선순위가 가장 높은 데이터를 가장 먼저 삭제하는 자료구조
- 우선순위에 따라 처리하고 싶을 때 사용

- 구현방법
  - list
  - heap
    - 완전 이진 트리 자료구조의 일종
    - 항상 루트 노드(root node)를 제거
    - 최소 힙
      - 루트 노드가 가장 작은 값을 가집니다
      - 따라서 값이 가장 작은 데이터가 우선적으로 제거
    - 최대 힙
      - 루트 노드가 가장 큰 값을 가집니다.
      - 따라서 값이 큰 데이터가 우선적으로 제거됩니다.

### 최소 힙 구성 함수: min-heapify()

- (상향식) 부모 노드로 거슬러 올라가며, 부모보다 자신의 값이 더 작은 경우에 위치를 교체합니다.
- 새로운 윈소가 삽입되었을 때 O(logN)의 시간 복잡도로 힙 성질을 유지하도록 할 수 있습니다.
- 힙에서 원소가 제거되었을 때 O(logN)의 시간 복잡도로 힙 성질을 유지하도록 할 수 있습니다.
  - 원소를 제거할 때는 가장 마지막 노드가 루트 노드의 위치에 오도록 합니다.
  - 이후에 루트 노드에서부터 하향식으로(더 작은 자식 노드로) Heapify()를 진행합니다.

## 트리(tree)

- 트리는 가계도와 같은 계층적인 구조를 표현할 때 사용할 수 있는 자료구조

### 이진 탐색 트리 (Binary Search Tree)

- 이진 탐색이 동자할 수 있도록 고안된 효율적인 탐색이 가능한 자료구조의 일종입니다.
- 이진 탐색 트리의 특징: 왼쪽 자식 노드 < 부모 노드 < 오른쪽 자식 노드
  - 부모 노드보다 왼쪽 자식 노드가 작습니다.
  - 부모 노드보다 오른쪽 자식 노드가 큽니다.

### 트리의 순회(Tree Traversal)

- 트리 자료구조에 포함된 노드를 특정한 방법으로 한 번씩 방문하는 방법을 의미합니다.
  - 트리의 정보를 시각적으로 확인할 수 있습니다.

- 대표적인 트리 순회 방법은 다음과 같습니다.
  - 전위 순회(pre-order traverse): 루트를 먼저 방문합니다
  - 중위 순회(in-order traverse): 왼쪽 자식을 방문한 뒤에 루트를 방문합니다.
  - 후위 순회(post-order traverse): 왼쪽 자식을 방문하고 오른쪽 자식을 방문한 뒤에 루트를 방문합니다.

### 바이너리 인덱스 트리 (Binary Indexed Tree)

- 2진법 인덱스 구조를 활용해 구간 합 문제를 효과적으로 해결해줄 수 있는 자료구조



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

# 탐색

## DFS(Depth_First Search)

- 깊이 우선 탐색. 그래프에서 **깊은 부분을 우선적으로 탐색하는 알고리즘**
- **스택 자료구조(혹은 재귀 함수)를 이용**하며, 구체적인 동작 과정은 다음과 같다.
  1. 탐색 시작 노드를 스택에 삽입하고 방문 처리를 합니다.
  2. 스택의 최상단 노드에 방문하지 않은 인접한 노드가 하나라도 있으면 그 노드를 스택에 넣고 방문처리합니다. 방문하지 않은 인접 노드가 없으면 스택에서 최상단 노드를 꺼냅니다.
  3. 더 이상 2번의 과정을 수행할 수 없을 때가지 반복합니다.

## BFS (Breadth-First Search)

- 너비 우선 탐색. 그래프에서 **가까운 노드부터 우선적으로 탐색하는 알고리즘**입니다.
- BFS는 **큐 자료구조**를 이용하며, 구체적인 동작 과정은 다음과 같습니다.
  1. 탐색 시작 노드를 큐에 삽입하고 방문 처리를 합니다.
  2. 큐에서 노드를 꺼낸 뒤에 해당 노드의 인접 노드 중에서 방문하지 않은 노드를 모두 큐에 삽입하고 방문 처리합니다.
  3. 더 이상 2번의 과정을 수행할 수 없을 때까지 반복합니다.




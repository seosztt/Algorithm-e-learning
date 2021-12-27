# 재귀 함수

- 재귀 함수(Recursive Function)란 **자기 자신을 다시 호출하는 함수**를 의미합니다.

- 재귀 함수를 문제 풀이에서 사용할 때는 재귀 함수의 종료 조건을 반드시 명시해야 합니다.
- 종료 조건을 제대로 명시하지 않으면 함수가 무한히 호출될 수 있습니다.

## 재귀 함수 사용의 유의 사항

- 재귀 함수를 잘 활용하면 복잡한 알고리즘을 간결하게 작성할 수 있습니다.
  - 단, 오히려 다른 사람이 이해하기 어려운 형태의 코드가 될 수도 있으므로 신중하게 사용해야 합니다.
- 모든 <u>재귀 함수는 반복문을 이용하여 동일한 기능을 구현</u>할 수 있습니다.
- 재귀 함수가 반복문보다 유리한 경우도 있고 불리한 경우도 있습니다.
- 컴퓨터가 함수를 연속적으로 호출하면 컴퓨터 메모리 내부의 스택 프레임에 쌓입니다.
  - 그래서 스택을 사용해야 할 때 구현상 **스택 라이브러리 대신에 재귀 함수를 이용**하는 경우가 많습니다.



# 실전에서 유용한 Python Standard Library

- 내장 함수: 기본 입출력 함수부터 정렬 함수까지 기본적인 함수들을 제공합니다.
  - 파이썬 프로그램을 작성할 때 없어서는 안 되는 필수적인 기능을 포함하고 있습니다.
- itertools: 파이썬에서 반복되는 형태의 데이터를 처리하기 위한 유용한 기능들을 제공합니다.
  - 특히 순열과 조합 라이브러리는 코딩 테스트에서 자주 사용됩니다.
- heapq: 힙(Heap) 자료구조를 제공합니다.
  - 일반적으로 우선순위 큐 기능을 구현하기 위해 사용됩니다.

- bisect: 이진 탐색(Binary Search) 기능을 제공합니다.
- collectioins: 덱(deque), 카운터(Counter) 등의 유용한 자료구조를 포함합니다.
- math: 필수적인 수학적 기능을 제공합니다.
  - 팩토리얼, 제곱근, 최대공약수(GCD), 삼각함수 관련 함수부터 파이(pi)와 같은 상수를 포함합니다.



# 소수 판정 알고리즘

- 어떠한 자연수가 소수인지 아닌지 판별해야 하는 문제가 자주 출제됩니다.

## 기본적인 알고리즘 성능 분석

- 2부터 X-1까지의 모든 자연수에 대하여 연산을 수행해야 합니다.
  - 모든 수를 하나씩 확인한다는 점에서 시간 복잡도는 O(X)입니다.

## 약수의 성질

- **모든 약수가 가운데 약수를 기준으로 곱셈 연산에 대해 대칭**을 이루는 것을 알 수 있습니다.
- 따라서 우리는 특정한 자연수의 모든 약수를 찾을 때 가운데 약수(제곱근)까지만 확인하면 됩니다.

## 개선된 알고리즘 성능 분석

- 2부터 X의 제곱근(소수점 이하 무시)까지의 모든 자연수에 대하여 연산을 수행해야 합니다.
  - 시간 복잡도는 O(N^1/2)입니다.

## 다수의 소수 판별

- <u>특정한 수의 범위 안에 존재하는 모든 소수</u>를 찾으려면 **에라토스테네스의 체 알고리즘**을 사용할 수 있습니다.

## 에라토스테네스의 체 알고리즘

- <u>다수의 자연수에 대하여 소수 여부를 판별</u>할 때 사용하는 대표적인 알고리즘입니다.
- 에라토스테네스의 체는 N보다 작거나 같은 모든 소수를 찾을 때 사용할 수 있습니다.
- 에라토스테네스의 체 알고리즘의 **구체적인 동작 과정**은 다음과 같습니다.
  1. 2부터 N까지의 모든 자연수를 나열한다.
  2. 남은 수 중에서 아직 처리하지 않은 가장 작은 수 i를 찾는다.
  3. 남은 수 중에서 i의 배수를 모두 제거한다. (i는 제거하지 않는다).
  4. 더 이상 반복할 수 없을 때까지 2번과 3번의 과정을 반복한다.

## 에라토스테네스의 체 알고리즘 성능 분석

- 에라토스테네스의 체 알고리즘의 시간 복잡도는 사실상 선형 시간에 가가울 정도로 매우 빠릅니다.
  - 시간 복잡도는 O(NloglogN)입니다.
- 에라토스테네스의 체 알고리즘은 다수의 소수를 찾아야 하는 문제에서 효과적으로 사용될 수 있습니다.
  - 하지만 각 자연수에 대한 소수 여부를 저장해야 하므로 **메모리가 많이 필요**합니다.
  - **10억**이 소수인지 아닌지 판별해야 할 때 에라토스테네스의 체를 사용하면 메모리 매우 비효율적으로 사용하게 된다.


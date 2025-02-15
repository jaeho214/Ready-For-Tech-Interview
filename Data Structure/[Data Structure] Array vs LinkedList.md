## Array vs LinkedList

Array와 LinkedList의 비교이다.



- Array
  - 배열이며, 논리적 저장순서와 물리적 저장순서가 일치한다.
  - 특정 자료형들이 메모리 공간 상에서 연속적으로 이루어져 있다.
  - immutable하다.
  - 인덱스로 해당 원소에 접근할 수 있으며, 인덱스를 알고 있다면 O(1)의 시간 복잡도로 원소에 접근이 가능하다. 즉, `Random Access`가 가능하다.
  - 삭제 또는 삽입 과정에서는 해당 원소에 접근하여 작업을 완료한 뒤, shift해줘야 하므로 비용이 발생한다. O(n)
  - 메모리 공간 활용에 제약이 있다.



- LinkedList
  - 데이터 검색 시 처음 노드부터 순회해야 한다. 이유는 논리적 저장 순서와 물리적 저장 순서가 다르기 때문이다. O(n)
  - 메모리 공간 상에서 각 노드들이 연속적으로 이루어져 있지 않고 흩어져 있으며, 각각의 노드가 자신의 다음 노드의 위치를 알고 있는 형태이다. 
  - 각 노드들이 메모리 공간 상의 어디에 위치하는지는 각각의 노드들만 알고 있고, 사용자는 제일 첫 번째 노드의 위치만 알고 있는 상태이다.
  - 어떤 원소를 삽입, 삭제 시 그 원소를 찾기 위해 O(n)의 시간이 발생하고 추가적으로 작업을 완료하는 시간까지 O(n)의 시간이 걸린다.
  - 결국, LinkedList는 검색과 삽입, 삭제 과정 모두 O(n)의 시간 복잡도를 갖는다.



### 데이터 접근 속도
- Array
  - 인덱스를 사용하여 빠르게 접근하므로 시간 복잡도는 O(1)이다. 
  - Random Access가 가능하다.
- LinkedList
  - 특정 원소에 접근하기 위해서는 처음부터 순차적으로 검색하기 때문에 시간 복잡도는 O(N)이다.



### 데이터 삽입 속도

- Array
  - 데이터를 중간이나 맨 앞에 삽입할 경우, 이후의 데이터를 Shift해야 하므로 추가 과정과 시간이 소요된다. 
  - 따라서 데이터가 많은 경우, 비효율적이다.
  - O(N)의 시간이 걸린다.
- LinkedList
  - 중간 삽입 없이 맨 앞과 맨 뒤에만 삽입한다면 O(1)의 시간 복잡도를 갖는다.
  - 그렇지 않다면 삽입할 위치를 찾고(O(N))과 삽입 연산을 진행하기 때문에 O(N)의 시간 복잡도를 갖는다.
  - 그럼에보 불구하고 Array보다 빠른 성능을 갖는다.

Array의 경우, 데이터를 삽입하여 모든 공간이 꽉 차게 되면 새로운 메모리 공간을 할당받아 옮겨야 하지만, LinkedList를 그럴 필요가 없다. 추가할 때마다 동적으로 메모리 공간을 할당받는다.



### 데이터 삭제 속도

- Array
  - 데이터 삭제의 경우, 그 위치의 데이터를 삭제한 후 전체적으로 Shift해줘야 하기 때문에 O(N)의 시간 복잡도를 갖는다.
- LinkedList
  - 삭제할 원소를 찾기 위해 O(N)의 시간 복잡도를 갖고 삭제한다. 하지만, Array보다 빠르게 삭제 연산을 수행한다.



### 메모리 할당

- Array 
  - 메모리에는 Array가 선언되자 마자 Compile time에 할당되어 진다.
  - 정적 메모리 할당이라고 한다.
- LinkedList
  - 메모리는 새로운 Node가 추가될 때 runtime에 할당되어 진다.
  - 동적 메모리 할당이라고 한다. 



### 결론

- 삽입과 삭제가 빈번하게 일어난다면 LinkedList를 사용하는 것이 좋다.
- 데이터에 접근하는 것이 빈번하게 일어난다면 Array를 사용하는 것이 좋다.
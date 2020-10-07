# 연결 리스트

## 개요
- 선형 자료구조의 하나로 Node가 연결된 형태로 구성되어 있다.
![연결 리스트 구조 예시](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/1920px-Singly-linked-list.svg.png)
(출처: Wikipedia - <https://en.wikipedia.org/wiki/Linked_list>)
- Node는 데이터 값과 다음 데이터 값을 가지고 있는 포인터의 쌍으로 구성되어 있다.
![Node 구성 예시](../assets/Linked-list-Node.png)
- 데이터를 추가할 때 필요한 메모리를 새로 할당 사용한다.
- 일반적으로 head라고 부르는 Node 혹은 포인터로 시작 Node를 관리하며 마지막 Node의 포인터에는 NULL값이 저장되어 마지막 노드라는 것을 표시한다.  
(head로 생성한 연결 리스트를 관리하며 head의 정보를 잃어버리면 생성한 연결 리스트를 사용할 수 없다.)
- 필요할 때 메모리를 할당받아 Node를 연결하여 구성하므로 메모리상에서 연속적이지 않다.  
![메모리 할당 예시](https://w.namu.la/s/ef210f7b01f17258cc7060ba5b02e5b4b337bfb282cea34ac6a68c00ca740eea089b57d84f3f618e103bf8e54b2c698e1290d7bb489498073458f06da004e664984fc50b3eb6c93e683fc7652c12b4b19d6bf6da16590b610e777023c87b44f3dd60bc47905350a35f639c704dbd5aca)  
(출처: 파이썬 알고리즘 인터뷰. 책만. p199 - <https://www.onlybook.co.kr/entry/algorithm-interview>)

### 장점
1. 메모리를 낭비하지 않음
    - 필요할 때 메모리를 할당받아 사용한다.
    - 배열처럼 미리 전체 메모리를 할당받아 사용하지 않기 때문에 낭비되는 메모리가 없다.
2. 데이터의 삽입이 간단
    - 데이터의 추가나 삽입 위치에 관계없이 Node의 포인터 값만 변경하면 된다.
    - 데이터를 미는 등의 추가 연산이 필요없다.
    ![Node 삽입 예시](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/CPT-LinkedLists-addingnode.svg/474px-CPT-LinkedLists-addingnode.svg.png)  
    (출처: Wikipedia - https://en.wikipedia.org/wiki/Linked_list)
3. 데어터의 삭제가 간단
    - 데이터의 삭제 위치와 관계없이 포인터의 주소값을 삭제할 Node의 다음 Node로 변경하면 된다.
    - 삭제 이후 데이터르 당겨오는 등의 추가 연산이 필요 없다.
    ![Node 삭제 예시](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d4/CPT-LinkedLists-deletingnode.svg/380px-CPT-LinkedLists-deletingnode.svg.png)  
    (출처: Wikipedia - https://en.wikipedia.org/wiki/Linked_list)

### 단점
1. 특정 데이터에 바로 접근 불가
    - 메모리상에 연속적으로 할당되어 있지 않기 때문에 head로 시작 위치를 알고 있어도 원하는 데이터에 직접 접근이 불가능 하다.
    - head부터 시작해서 원하는 데이터까지 검색이 필요하다.
2. 데이터를 관리하기 위한 추가 공간이 필요
    - 데이터 값 외에 다음 Node의 주소값을 저장하기 위한 메모리가 필요하다.

### 구현
```Java
class MyList {
  Node head;
  int size;

  public MyList() {
    head = null;
    size = 0;
  }

  private class Node {
    private Node next;
    private int data;

    Node(int data) {
      this.data = data;
      next = null;
    }
  }

  public void add(int data) {
    Node newNode = new Node(data);
    if(head == null) {
      head = newNode;
    } else {
      Node temp = head;
      while(temp.next != null) {
        temp = temp.next;
      }
      temp.next = newNode;
    }
    size++;
  }

  public void delete() {
      //TODO
  }

  public void show() {
    Node node = head;
    while(node.next != null) {
      System.out.println(node.data);
      node = node.next;
    }
    System.out.println(node.data);
  }
}
```

## 정리
- 데이터의 추가/삽입이나 삭제가 많이 필요한 상황에 적절한 자료구조.
- 특정 데이터로 바로 접근이 필요하거나 검색이 많을 경우에는 효율적이지 않음.
- 대부분의 언어에서 라이브러리로 지원하므로 사용하기 쉬움.

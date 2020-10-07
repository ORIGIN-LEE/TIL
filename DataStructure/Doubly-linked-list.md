# 이중 연결 리스트

## 개요
- 연결 리스트의 변형된 형태로 Node가 다음 Node의 주소값과 이전 Node의 주소값을 다 가지고 있는 자료구조  
![이중 연결 리스트 예시](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/1920px-Singly-linked-list.svg.png)  
(출처: Wikipedia - <https://en.wikipedia.org/wiki/Linked_list#Doubly_linked_list>)
- 마지막 Node의 정보를 가지고 있는 tail이 존재한다.
- 새로운 Node를 추가할 때 양방향 연결성을 잃지 않기 위해 prev와 next의 적절한 조절이 필요하다.   
![이중 연결 리스트 삽입 예시](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL_add_middle1.png)    
(출처: GeeksforGeeks - <https://www.geeksforgeeks.org/doubly-linked-list/>)  
![이중 연결 리스트 삭제 예시](https://media.geeksforgeeks.org/wp-content/uploads/20200318150826/ezgif.com-gif-maker1.gif)    
(출처: GeeksforGeeks - <https://www.geeksforgeeks.org/delete-a-node-in-a-doubly-linked-list/>)

### 장점
1. 양방향 탐색
    - head와 tail로 연결 리스트의 양 끝 어디에서나 탐색을 시작할 수 있다.

### 단점
1. 추가 메모리 필요
    - 다음 Node의 정보를 가지고 있는 head에 더해 이전 Node의 정보를 가지고 있는 prev를 위한 추가 메모리가 필요하다.

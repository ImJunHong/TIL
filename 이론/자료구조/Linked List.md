# 연결 리스트(Linked List)
* 각 노드가 데이터와 포인터를 가지고 한 줄로 연결되어 있는 방식으로 데이터를 저장하는 자료구조
* 시간복잡도
  * 탐색 : O(n)
  * 삽입/삭제 : O(1)
* 장점
  * 리스트의 길이를 동적으로 조절 가능
  * 크기가 고정되어 있지 않아 데이터의 삽입과 삭제가 용이함
* 단점
  * 임의 접근(random access)이 불가능함
  * 모든 노드를 처음부터 순차적으로 탐색하기 때문에 탐색 시간이 긺
  (리스트를 뒤에서부터 순회하거나 정렬할 시 최악의 경우 시간복잡도가 O(n<sup>2</sup>))

## 단일 연결 리스트(Singly Linked List)
각 노드에 자료 공간과 한 개의 포인터 공간이 있고, 각 노드의 포인터는 다음 노드를 가리키는 연결 리스트

### Python
```python
class Node(object):
    def __init__(self, data):
        self.data = data
        self.pointer = None

class SinglyLinkedList(object):
    def __init__(self):
        self.head = None
        self.length = 0

    def add(self, node):
        self.length += 1
        if self.head == None: # 첫 번째 노드 삽입
            self.head = node
        else:
            curr = self.head
            while curr.pointer != None:
                curr = curr.pointer
            curr.pointer = node
    
    def get_index(self, data):
        curr = self.head
        index = 0
        while curr:
            if curr.data == data:
                return index
            curr = curr.pointer
            index += 1
        return -1

    def get_data(self, index):
        curr = self.head
        curr_index = 0
        while curr_index < index:
            if curr.pointer:
                curr = curr.pointer
                curr_index += 1
            else:
                break
        if curr_index == index:
            return curr.data
        else:
            return -1
            
    def insert_node(self, index, node):
        curr = self.head
        prev = None
        curr_index = 0

        if index == 0: # 리스트의 맨 앞에 노드 삽입
            if self.head: # 리스트가 비어 있지 않을 때
                nxt = self.head
                self.head = node
                self.head.pointer = nxt
            else: # 리스트가 비어 있을 때
                self.head = node
        else: # 리스트의 중간 또는 맨 마지막에 노드 삽입
            while curr_index < index:
                if curr:
                    prev = curr
                    curr = curr.pointer
                else:
                    break
                curr_index += 1
            if curr_index == index:
                node.pointer = curr
                prev.pointer = node
            else:
                print(f"인덱스 {index}에 노드를 삽입할 수 없습니다.")

    def delete_node_by_index(self, index):
        curr_index = 0
        curr = self.head
        prev = None
        nxt = self.head.pointer
        if index == 0: # 첫 번째 노드 삭제
            self.head = nxt
        else: # 중간 또는 마지막 노드 삭제
            while curr_index < index:
                if curr.pointer:
                    prev = curr
                    curr = nxt
                    nxt = nxt.pointer
                else:
                    break
                curr_index += 1
            if curr_index == index:
                prev.pointer = nxt
            else:
                print(f"인덱스 {index}에 해당하는 노드가 없습니다.")

    def delete_node_by_data(self, data):
        index = self.get_index(data)
        if index == -1:
            print(f"{data}을(를) 데이터로 가진 노드가 없습니다.")
        else:
            self.delete_node_by_index(index)

    def clear(self):
        self.head = None

    def print_list(self):
        curr = self.head
        while curr:
            print(curr.data, end=" ")
            curr = curr.pointer
        print()

ll = SinglyLinkedList()
ll.add(Node(1))
ll.add(Node(2))
ll.add(Node(3))
ll.add(Node(4))
ll.add(Node(6))
ll.print_list() # 1 2 3 4 6
print(ll.get_data(4)) # 6
print(ll.get_index(6)) # 4
ll.insert_node(4, Node(5))
ll.print_list() # 1 2 3 4 5 6
ll.delete_node_by_index(5)
ll.print_list() # 1 2 3 4 5
ll.delete_node_by_index(8) # 인덱스 8에 해당하는 노드가 없습니다.
ll.print_list() # 1 2 3 4 5
ll.delete_node_by_data(1)
ll.print_list() # 2 3 4 5
ll.delete_node_by_data(8) # 8을(를) 데이터로 가진 노드가 없습니다.
ll.print_list() # 2 3 4 5
```

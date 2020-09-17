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
'''python
class Node(object):
    def __init__(self, data):
        self.data = data
        self.pointer = None

class SinglyLinkedList(object):
    def __init__(self):
        self.head = None
        self.length = 0

    def add(self, node):
        if self.head == None: # 첫 번째 노드 삽입
            self.head = node
        else:
            current_node = self.head
            while current_node.pointer != None: # 중간에 삽입하는 경우
                current_node = current_node.pointer
            current_node.pointer = node
    
    def get_index(self, data):
        current_node = self.head
        index = 0
        while current_node:
            if current_node.data == data:
                return index
            current_node = current_node.pointer
            index += 1
        return -1

    def insert_node_index(self, index, node):
        current_node = self.head
        previous_node = None
        current_index = 0

        if index == 0: # 리스트의 맨 앞에 노드 삽입
            if self.head: # 리스트가 비어 있지 않을 때
                next_node = self.head
                self.head = node
                self.head.pointer = next_node
            else: # 리스트가 비어 있을 때
                self.head = node
        else: # 리스트의 중간 또는 맨 마지막에 노드 삽입
            while current_index < index:
                if current_node:
                    previous_node = current_node
                    current_node = current_node.pointer
                else:
                    break
                current_index += 1
            if current_index == index:
                node.pointer = current_node
                previous_node.point = node
            else:
                return -1
        
    def insert_node_data(self, data, node):
        index = self.get_index(data)
        if index >= 0:
            self.insert_node_index(index, node)
        else:
            return -1

    def delete_node(self, index):
        current_index = 0
        current_node = self.head
        previous_node = None
        next_node = self.head.pointer
        if index == 0:
            self.head = next_node
        else:
            while current_index < index:
                if current_node.pointer:
                    previous_node = current_node
                    current_node = next_node
                    next_node = next_node.pointer
                else:
                    break
                current_index += 1
            if current_index == index:
                previous_node.pointer = next_node
            else:
                return -1
    
    def clear(self):
        self.head = None

    def print_list(self):
        current_node = self.head
        string = ""
        while current_node:
            string += str(current_node.data)
            if current_node.pointer:
                string += " "
            current_node = current_node.pointer
        print(string)
```

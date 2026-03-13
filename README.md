class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


class Queue:
    def __init__(self):
        self.front = None
        self.rear = None

    def enqueue(self, data):
        new_node = Node(data)

        if self.rear is None:
            self.front = self.rear = new_node
            return

        self.rear.next = new_node
        self.rear = new_node

    def dequeue(self):
        if self.front is None:
            print("Queue is empty")
            return

        temp = self.front
        self.front = temp.next

        if self.front is None:
            self.rear = None

        print("Deleted element:", temp.data)

    def display(self):
        temp = self.front
        if temp is None:
            print("Queue is empty")
            return

        print("Queue elements are:")
        while temp:
            print(temp.data, end=" ")
            temp = temp.next
        print()


q = Queue()

q.enqueue(10)
q.enqueue(20)
q.enqueue(30)

q.display()

q.dequeue()

q.display()# Linked-list-queue-ADT
Practical program 

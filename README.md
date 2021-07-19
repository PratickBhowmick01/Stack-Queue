# Stack-Queue
Using Array and Linked LIst


#Stack Implementation//- Array
class Stack:
    stack = []
    pointer = -1
    
    def push(self, element):
        self.stack.append(element)
        self.pointer += 1
    
    def peek(self):
        return (self.stack[self.pointer])

    def pop(self):
        value = self.stack[self.pointer]
        self.stack = self.stack[:-1]    #discarding the last item
        self.pointer -= 1
        return value  

#Stack Implementation//- Array
class Node:
    def __init__(self,v):
        self.val = v
        self.ref = None 
        
class Stack:
    head = None 
    
    def push(self, data):
        if(self.head == None):
            self.head = Node(data) 
        else:
            n = Node(data) 
            n.ref = self.head
            self.head = n 
    
    def peek(self):
        #check for empty list
        return self.head.val 
    
    def pop(self):
        #check for empty list 
        temp = self.head 
        self.head = self.head.ref 
        value = temp.val  
        temp.val = None 
        temp.ref = None 
        return value
        
        
#Queue Implementation: Array

class Queue:   
    q = []
    front = 0 
    rear = -1
     
    def enqueue(self, val):
        self.q.append(val)
        self.rear += 1
    
    def dequeue(self):
        temp = self.q[self.front]
        self.q = self.q[self.front+1:self.rear]     #excluding first value(0 index)
        self.rear -= 0 
        return temp 
    
    def peek(self):
        return self.q[self.front]
    
queue = Queue()
queue.enqueue(1)
print("Top:", queue.peek())
queue.enqueue(2)
queue.enqueue(2)
print(queue.dequeue())
print(queue.peek()) 


#Queue implementation: Linked List

class Node:
    def __init__(self,val):
        self.val = val 
        self.next = None 
        
class Queue:
    head = None 
    tail = None 

    def enqueue(self, data):
        n = Node(data)
        if(self.head == None):
            self.head = n
            self.tail = n
        else:
            self.tail.next = n
            self.tail = n
            
    def dequeue(self):
        if(self.head == None):
            print("Empty List")
        else:
            temp = self.head 
            self.head = self.head.next 
            print("Removed:", temp.val)
            temp.val = None 
            temp.next = None 
    
    def peek(self):
        return (self.head.val)
        
q = Queue()
q.enqueue(1)
q.enqueue(2)
print(q.peek()) 
q.dequeue()
print(q.peek())  
        
        
        
        
        
        
        
        
        
        

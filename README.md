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
        
        

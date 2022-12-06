Multiplication without using * operator 	

def multiply(x, y):
    if y < 0:
        return -multiply(x, -y)
    elif y == 0:
        return 0
    elif y == 1:
        return x
    else:
        return x + multiply(x, y - 1)
print(multiply(3, 5));

Output: 15


 Towers of Hanoi	
def tower_of_hanoi(disks, source, auxiliary, target):  
    if(disks == 1):  
        print('Move disk 1 from rod {} to rod {}.'.format(source, target))  
        return  
    tower_of_hanoi(disks - 1, source, target, auxiliary)  
    print('Move disk {} from rod {} to rod {}.'.format(disks, source, target))  
    tower_of_hanoi(disks - 1, auxiliary, source, target)  
disks = int(input('Enter the number of disks: '))  
tower_of_hanoi(disks, 'A', 'B', 'C')  

Output: 
Enter number of disks: 2  
Move disk 1 from rod A to rod B.  
Move disk 2 from rod A to rod C.  
Move disk 1 from rod B to rod C. 


 Acckermann function 
def Ackermann(m, n):
    cache = [[0 for i in range(n + 1)] for j in range(m + 1)]
    for rows in range(m + 1):

        for cols in range(n + 1):

            if rows == 0:

                cache[rows][cols] = cols + 1
            elif cols == 0:

                cache[rows][cols] = cache[rows-1][1]

            else:
                r = rows - 1

                c = cache[rows][cols-1]
                if r == 0:

                    ans = c + 1

                elif c <= n:

                    ans = cache[rows-1][cache[rows][cols-1]]

                else:
                    ans = (c-n)*(r) + cache[r][n]
 

                cache[rows][cols] = ans
 

    return cache[m][n]

m = 2

n = 2
m1 = 5

n1 = 7
print("Ackermann value for m = ", m,

      " and n = ", n, "is -> ",

      Ackermann(m, n))
print("Ackermann value for m = ", m1,

      " and n = ", n1, "is -> ",

      Ackermann(m1, n1)) 

Output:
Ackermann value for m = 2 and n = 2 is -> 7
Ackermann value for m = 5 and n = 7 is -> 6141004759





 Convert from decimal to binary 
def DecimalToBinary(num):
    if num >= 1:

        DecimalToBinary(num // 2)

    print(num % 2, end = '')
if _name_ == '_main_':
    dec_val = 24
    DecimalToBinary(dec_val)

Output:
011000

 Convert binary to decimal 	

def decimalToBinary(n): 
    if(n > 1): 
        decimalToBinary(n//2) 
    print(n%2, end=' ')
if _name_ == '_main_': 
    decimalToBinary(8) 
    print("\n")
    decimalToBinary(18) 
    print("\n")
    decimalToBinary(7) 

Output:
1 0 0 0 
1 0 0 1 0 
1 1 1

Euclid's algorithm 

def hcf(a, b): 
    if(b == 0): 
        return a 
    else: 
        return hcf(b, a % b) 
a = 60
b = 48
print("The gcd of 60 and 48 is : ", end="") 
print(hcf(60, 48)) 

Output:
The gcd of 60 and 48 is : 12

 Number is prime or not 

num = 11
if num > 1:
    for i in range(2, int(num/2)+1):
        if (num % i) == 0:
            print(num, "is not a prime number")
            break
    else:
        print(num, "is a prime number")
else:
    print(num, "is not a prime number")

Output: 11 is a prime number


 Prime factors of a given number 

import math
def primeFactors(n):
    while n % 2 == 0:
        print 2,
        n = n / 2
    for i in range(3,int(math.sqrt(n))+1,2):
        while n % i== 0:
            print i,
            n = n / i
    if n > 2:
        print n
n = 315
primeFactors(n)

Output: 3 5 7

 Binomial coefficient 

def binomialCoeff(n, k):
    if k > n:
        return 0
    if k == 0 or k == n:
        return 1
    return binomialCoeff(n-1, k-1) + binomialCoeff(n-1, k)
n = 5
k = 2
print ("Value of C(%d,%d) is (%d)" % (n, k,binomialCoeff(n, k)))

Output: Value of C(5, 2) is 10


 Number pattern 

rows = 6
for i in range(rows):
    for j in range(i):
        print(i, end=' ')
    print('')

Output: 
1  
2 2  
3 3 3  
4 4 4 4  
5 5 5 5 5
6 6 6 6 6 6


 Mirrored alphabets 

n = 5
k = 2*n-1
for i in range(0,n):
for j in range(0,k):
print(end=' ')
k = k - 1
val = ""
for r in range(1, i+1):
val = val + str(r)
print(val[:-1]+val[::-1])

Output: 
A
ABA
ABCBA
ABCDCBA
ABCDEDCBA


 Solid star
rows=5
def solidSquare(rows):
    for i in range(1, rows):
        for j in range(1, rows + 1):
            print("*", end = "")
        print()
solid square(rows)

Output:
*****
*****
*****
*****
*****


 Hollow Pattern 
rows =5
def hollowSquare(rows):
    for i in range(1, rows + 1):
        if (i == 1 or i == rows):
            for j in range(1, rows + 1):
                print("*", end = "")
        else:
            for j in range(1, rows + 1):
                if (j == 1 or j == rows):
                    print("*", end = "")
                else:
                    print(end = " ")
        print()
 
Output:
*****
*      *
*      *
*      *
*****


Implment two stacks in One Array 

class twoStacks:

	def init(self, n):	 # constructor
		self.size = n
		self.arr = [None] * n
		self.top1 = math.floor(n/2) + 1
		self.top2 = math.floor(n/2)
	def push1(self, x):
		if self.top1 > 0:
			self.top1 = self.top1 - 1
			self.arr[self.top1] = x
		else:
			print("Stack Overflow by element : ", x)
	def push2(self, x):
		if self.top2 < self.size - 1:
			self.top2 = self.top2 + 1
			self.arr[self.top2] = x
		else:
			print("Stack Overflow by element : ", x)

	

	def pop1(self):
		if self.top1 <= self.size/2:
			x = self.arr[self.top1]
			self.top1 = self.top1 + 1
			return x
		else:
			print("Stack Underflow")
			exit(1)

	
	def pop2(self):
		if self.top2 >= math.floor(self.size/2) + 1:
			x = self.arr[self.top2]
			self.top2 = self.top2 - 1
			return x
		else:
			print("Stack Underflow")
			exit(1)
if name == 'main':
	ts = twoStacks(5)
	ts.push1(5)
	ts.push2(10)
	ts.push2(15)
	ts.push1(11)
	ts.push2(7)
	print("Popped element from stack1 is : " + str(ts.pop1()))
	ts.push2(40)
	print("Popped element from stack2 is : " + str(ts.pop2()))

Output:
Stack Overflow By element : 7
Popped element from stack1 is : 11
Stack Overflow By element : 40
Popped element from stack2 is : 15


 
Infix to postfix conversion 

class Conversion:
	def init(self, capacity):
		self.top = -1
		self.capacity = capacity
		self.array = []
		self.output = []
		self.precedence = {'+': 1, '-': 1, '*': 2, '/': 2, '^': 3}
	def isEmpty(self):
		return True if self.top == -1 else False
	def peek(self):
		return self.array[-1]
	def pop(self):
		if not self.isEmpty():
			self.top -= 1
			return self.array.pop()
		else:
			return "$"
	def push(self, op):
		self.top += 1
		self.array.append(op)
	def isOperand(self, ch):
		return ch.isalpha()
	def notGreater(self, i):
		try:
			a = self.precedence[i]
			b = self.precedence[self.peek()]
			return True if a <= b else False
		except KeyError:
			return False
	def infixToPostfix(self, exp):
		for i in exp:
			if self.isOperand(i):
				self.output.append(i)
			elif i == '(':
				self.push(i)
			elif i == ')':
				while((not self.isEmpty()) and
					self.peek() != '('):
					a = self.pop()
					self.output.append(a)
				if (not self.isEmpty() and self.peek() != '('):
					return -1
				else:
					self.pop()
			else:
				while(not self.isEmpty() and self.notGreater(i)):
					self.output.append(self.pop())
				self.push(i)
		while not self.isEmpty():
			self.output.append(self.pop())

		print "".join(self.output)
if name == 'main':
	exp = "a+b*(c^d-e)^(f+g*h)-i"
	obj = Conversion(len(exp)
	obj.infixToPostfix(exp)

Output:
abcd^e-fgh*+^*+i-


 Infix to prefix conversion 

def isOperator(c):
	return (not (c >= 'a' and c <= 'z') and not(c >= '0' and c <= '9') and not(c >= 'A' and c <= 'Z'))
def getPriority(C):
	if (C == '-' or C == '+'):
		return 1
	elif (C == '*' or C == '/'):
		return 2
	elif (C == '^'):
		return 3
	return 0
def infixToPrefix(infix):

	operators = []
	operands = []

	for i in range(len(infix)):
		if (infix[i] == '('):
			operators.append(infix[i])
		elif (infix[i] == ')'):
			while (len(operators)!=0 and operators[-1] != '('):
				op1 = operands[-1]
				operands.pop()
				op2 = operands[-1]
				operands.pop()
				op = operators[-1]
				operators.pop()
				tmp = op + op2 + op1
				operands.append(tmp)
			operators.pop()
		elif (not isOperator(infix[i])):
			operands.append(infix[i] + "")
		else:
			while (len(operators)!=0 and getPriority(infix[i]) <= getPriority(operators[-1])):
				op1 = operands[-1]
				operands.pop()

				op2 = operands[-1]
				operands.pop()

				op = operators[-1]
				operators.pop()

				tmp = op + op2 + op1
				operands.append(tmp)
			operators.append(infix[i])
	while (len(operators)!=0):
		op1 = operands[-1]
		operands.pop()

		op2 = operands[-1]
		operands.pop()

		op = operators[-1]
		operators.pop()

		tmp = op + op2 + op1
		operands.append(tmp)
	return operands[-1]

s = "(A-B/C)*(A/K-L)"
print( infixToPrefix(s))

Output:
*-A/BC-/AKL


 Implement Queue Operations using two stacks 


class Queue:
	def init(self):
		self.s1 = []
		self.s2 = []
	def enQueue(self, x):
		while len(self.s1) != 0:
			self.s2.append(self.s1[-1])
			self.s1.pop()
		self.s1.append(x)
		while len(self.s2) != 0:
			self.s1.append(self.s2[-1])
			self.s2.pop()
	def deQueue(self):
		
			# if first stack is empty
		if len(self.s1) == 0:
			print("Q is Empty")

		x = self.s1[-1]
		self.s1.pop()
		return x
if name == 'main':
	q = Queue()
	q.enQueue(1)
	q.enQueue(2)
	q.enQueue(3)
	print(q.deQueue())
	print(q.deQueue())
	print(q.deQueue())

Output:
1
2
3

 Generate Binary Numbers between 1 to N using Queues 

from collections import deque
def generate():
      q = deque()
      q = append(1)
      for i in range():
           front = str(q.popleft())
           print(front)
           q.append(front+'0')
           q.append(front+'1')
n = int(input("Enter n: "))
generate(n)

Output:
Enter n: 5
1
10
11
100
101



Implementation of reverse of a singly linked list 


class Node:
	def _init_(self, data):
		self.data = data
		self.next = None
class LinkedList:
	def _init_(self):
		self.head = None
	def reverse(self):
		prev = None
		current = self.head
		while(current is not None):
			next = current.next
			current.next = prev
			prev = current
			current = next
		self.head = prev
	def push(self, new_data):
		new_node = Node(new_data)
		new_node.next = self.head
		self.head = new_node
	def printList(self):
		temp = self.head
		while(temp):
			print (temp.data,end=" ")
			temp = temp.next

llist = LinkedList()
llist.push(20)
llist.push(4)
llist.push(15)
llist.push(85)
print ("Given Linked List")
llist.printList()
llist.reverse()
print ("\nReversed Linked List")
llist.printList()

Output:
Given Linked List
85 15 4 20 
Reversed Linked List
20 4 15 85


 Swapping of two nodes in a singly linked list without swapping data 


class LinkedList(object):
	def _init_(self):
		self.head = None
	class Node(object):
		def _init_(self, d):
			self.data = d
			self.next = None
	def swapNodes(self, x, y):
		if x == y:
			return
		prevX = None
		currX = self.head
		while currX != None and currX.data != x:
			prevX = currX
			currX = currX.next
		prevY = None
		currY = self.head
		while currY != None and currY.data != y:
			prevY = currY
			currY = currY.next
		if currX == None or currY == None:
			return
		if prevX != None:
			prevX.next = currY
		else:
			self.head = currY
		if prevY != None:
			prevY.next = currX
		else: 
			self.head = currX
		temp = currX.next
		currX.next = currY.next
		currY.next = temp
	def push(self, new_data):
		new_Node = self.Node(new_data)
		new_Node.next = self.head
		self.head = new_Node
	def printList(self):
		tNode = self.head
		while tNode != None:
			print tNode.data,
			tNode = tNode.next
llist = LinkedList()
llist.push(7)
llist.push(6)
llist.push(5)
llist.push(4)
llist.push(3)
llist.push(2)
llist.push(1)
print "Linked list before calling swapNodes() "
llist.printList()
llist.swapNodes(4, 3)
print "\nLinked list after calling swapNodes() "
llist.printList()

Output:
Linked list before calling swapNodes() 1 2 3 4 5 6 7 
Linked list after calling swapNodes() 1 2 4 3 5 6 7


 Concatenate two circular linked lists 


import math
class Node:
	def _init_(self, data):
		self.data = data
		self.next = None
		self.prev = None
def insert(head_ref, data):
	new_node = Node(data)
	new_node.data = data
	if (head_ref == None):
		new_node.next = new_node
		new_node.prev = new_node
	
	else :
		last = head_ref.prev
		new_node.next = head_ref
		new_node.prev = last
		last.next = new_node
		head_ref.prev = new_node
	head_ref = new_node
	return head_ref
def merge(first, second):
	if (first == None):
		return second
	if (second == None):
		return first
	if (first.data < second.data) :
		first.next = merge(first.next,second)
		first.next.prev = first
		first.prev = None
		return first
	
	else :
		second.next = merge(first,second.next)
		second.next.prev = second
		second.prev = None
		return second
def mergeUtil(head1, head2):
	if (head1 == None):
		return head2
	if (head2 == None):
		return head1
	if (head1.prev.data < head2.prev.data):
		last_node = head2.prev
	else:
		last_node = head1.prev
	head1.prev.next = None
	head2.prev.next = None
	finalHead = merge(head1, head2)
	finalHead.prev = last_node
	last_node.next = finalHead

	return finalHead
def printList(head):
	temp = head

	while (temp.next != head):
		print(temp.data, end = " ")
		temp = temp.next
	
	print(temp.data, end = " ")
if _name=='__main_':
	head1 = None
	head2 = None
	head1 = insert(head1, 8)
	head1 = insert(head1, 5)
	head1 = insert(head1, 3)
	head1 = insert(head1, 1)
	head2 = insert(head2, 11)
	head2 = insert(head2, 9)
	head2 = insert(head2, 7)
	head2 = insert(head2, 2)
	newHead = mergeUtil(head1, head2)
	print("Final Sorted List: ", end = "")
	printList(newHead)

Output:
Final Sorted List: 1 2 3 5 7 8 9 11 


 Maximum and Minimum Value of a Circular linked list 

class Node:    
    def _init_(self,data):    
        self.data = data;    
        self.next = None;    
     
class CreateList:      
    def _init_(self):    
        self.head = Node(None);    
        self.tail = Node(None);    
        self.head.next = self.tail;    
        self.tail.next = self.head;      
    def add(self,data):    
        newNode = Node(data);      
        if self.head.data is None:    
            self.head = newNode;    
            self.tail = newNode;    
            newNode.next = self.head;    
        else:    
            self.tail.next = newNode;    
            self.tail = newNode;    
            self.tail.next = self.head;    
    def minNode(self):    
        current = self.head;    
        minimum = self.head.data;    
        if(self.head == None):    
            print("List is empty");    
        else:    
            while(True):    
                if(minimum > current.data):    
                    minimum = current.data;    
                current= current.next;    
                if(current == self.head):    
                    break;    
        print("Minimum value node in the list: "+ str(minimum));    
    def maxNode(self):    
        current = self.head;    
        maximum = self.head.data;    
        if(self.head == None):    
            print("List is empty");    
        else:    
            while(True):    
                if(maximum < current.data):    
                    maximum = current.data;    
                current= current.next;    
                if(current == self.head):    
                    break;    
        print("Maximum value node in the list: "+ str(maximum));    
     
class CircularLinkedList:    
    cl = CreateList();    
    cl.add(5);    
    cl.add(20);    
    cl.add(10);    
    cl.add(1);     
    cl.minNode();    
    cl.maxNode(); 

Output:
Minimum value node in the list: 1
Maximum value node in the list: 20



Python program to print connected components in an undirected graph 

class Graph:
	def init(self, V):
		self.V = V
		self.adj = [[] for i in range(V)]

	def DFSUtil(self, temp, v, visited):
		visited[v] = True
		temp.append(v)

		for i in self.adj[v]:
			if visited[i] == False:
				temp = self.DFSUtil(temp, i, visited)
		return temp
	def addEdge(self, v, w):
		self.adj[v].append(w)
		self.adj[w].append(v)
	def connectedComponents(self):
		visited = []
		cc = []
		for i in range(self.V):
			visited.append(False)
		for v in range(self.V):
			if visited[v] == False:
				temp = []
				cc.append(self.DFSUtil(temp, v, visited))
		return cc
if name == "main":
	g = Graph(5)
	g.addEdge(1, 0)
	g.addEdge(2, 1)
	g.addEdge(3, 4)
	cc = g.connectedComponents()
	print("Following are connected components")
	print(cc)

Output:
Following are connected components 
0 1 2 
3 4

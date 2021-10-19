# Stacks and Queues

![queu](https://www.101computing.net/wp/wp-content/uploads/queue-diagram.png)

## What is a Stack
A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.
### Common terminology for a stack is:
1. Push - Nodes or items that are put into the stack are pushed
 2. Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.
 ![dcsd](https://s3.amazonaws.com/stackabuse/media/stacks-and-queues-in-python-2.jpg)

3. Top - This is the top of the stack.
![sda](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.tutorialandexample.com%2Fpython-stack%2F&psig=AOvVaw3F9M195aVQSm9WjK6SbnlF&ust=1634765670617000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCJiSyey21_MCFQAAAAAdAAAAABAJ)

4. Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

5. IsEmpty - returns true when stack is empty otherwise returns false.

## Stacks follow these concepts:
* FILO
First In Last Out

This means that the first item added in the stack will be the last item popped out of the stack.
![eew](https://miro.medium.com/max/1838/1*4Pn00ch_p4DTCb4r3naCDQ.png)

* LIFO
Last In First Out

This means that the last item added to the stack will be the first item popped out of the stack.
![sds](http://bluegalaxy.info/codewalk/wp-content/uploads/2018/08/stack.jpg)

## Stack Visualization

the topmost item is denoted as the top. When you push something to the stack:
* it becomes the new top. 
* When you pop something from the stack, you pop the current top and set the next top as top.next.

![scc](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/stack1.PNG)

## Effictionce Push O(1)
### Push O(1)
Pushing a Node onto a stack will always be an O(1) operation. This is because it takes the same amount of time no matter how many Nodes (n) you have in the stack.such as following:
1. First, you should have the Node that you want to add.

![sdsd](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/pushStack1.PNG)

2. Next, you need to assign the next property of Node 5 to reference the same Node that top is referencing: Node 4
![dc](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/pushStack2.PNG)

3. there is no indication that it is the first Node in the stack. To make this happen, you have to re-assign our reference top to the newly added Node, Node 5
![dcs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/pushStack3.PNG)

4. Now you completed a successful push of Node 5 onto the stack.
```
ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node
```

## Pop O(1)
Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.

Try and pop off Node 5 from the stack.
!(lmlk)[https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack1.PNG]

1. The first step of removing Node 5 from the stack is to create a reference named temp that points to the same Node that top points to.
 !(dsa)[https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack2.PNG]


2. Once you have created the new reference type, you now need to re-assign top to the value that the next property is referencing. 
!(sefd)[https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack3.PNG]

3. We can now remove Node 5 safely without it affecting the rest of the stack.
!(jhjh)[https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/popStack4.PNG]

4. Finally, we return the value of the temp Node that was just popped off.

## Peek O(1)

>pov: When conducting a peek, you will only be inspecting the top Node of the stack.

Typically, you would check isEmpty before conducting a peek. This will ensure that an exception is not raised. Alternately, you can wrap the call in a try/catch block.

## IsEmpty O(1)
Here is the pseudocode for isEmpty

```
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return top = NULL
```

## What is a Queue
Common terminology for a queue is

1. Enqueue - Nodes or items that are added to the queue.
2. Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.
3. Front - This is the front/first Node of the queue.
4. Rear - This is the rear/last Node of the queue.
5. Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.
6. IsEmpty - returns true when queue is empty otherwise returns false.

# Queues

### FIFO
First In First Out

This means that the first item in the queue will be the first item out of the queue.

### LILO
Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

![dsfds](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Queue.PNG)

### Enqueue O(1)
 because it does not matter how many other items live in the queue (n); it takes the same amount of time to perform the operation.

 ![sdd](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Enqueue1.PNG)

 ###  Adding a Node to a queue:

 1. First, we should change the next property of Node 4 to point to the Node we are adding 5.
![dxcz](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Enqueue2.PNG)

2. re-assign the rear reference to point to Node 5. 
![dsada](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Enqueue3.PNG)

🎉🎉Congratulations! You have just successfully added a Node to a queue.🎉🎉

### Dequeue O(1)
When you remove an item from a queue, you use the dequeue action. This is done with an O(1) operation in time because it doesn’t matter how many other items are in the queue

##### removing a Node from a queue.

1.  create a temporary reference type named temp and point to the same Node that front is pointing too. 
![sdf](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Dequeue1.PNG)
2. Next, you want to re-assign front to the next value that the Node front is referencing. In our visual, this would be Node 2.
![sdf](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Dequeue2.PNG)

3. re-assign the next property on the temp Node to null. We do this because we want to make sure that all the proper Nodes clear 
![sdfds](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/images/Dequeue3.PNG)

4. Finally, we return the value of the temp Node that was just removed.

5. Congratulations! You dequeue action on a queue!


### Peek O(1)
When conducting a peek, you will only be inspecting the front Node of the queue
<!-- ![,dcsd]()
![]()
![]()
![]()
![]() -->
# Data Structures & Algorithm - Lab Notes 1

## Stack

## PUSH & POP operations

#### PUSHING elements to the stack
```
#include <stdio.h>
#define MAX 5


	int stack[MAX],top = -1;
	
	void push(int value){
		if(top == MAX-1){
			printf("Stack Overflow! cannot push %d\n", value);
			return;
		}
	top = top+1;
	stack[top]=value;
	printf("%d pushed into the stack\n", value);
	}
	
	
	int main(){
		push(10);
		push(20);
		push(30);
		push(40);
		return 0;
	}

```

#### POPPING elements from stack
```
#include <stdio.h>
#define MAX 5


	int stack[MAX],top = -1;
	
	int pop(){
		if(top == -1){
			printf("stack Underflow! cannot pop\n");
			return -1;
		}
		int currentValue = stack[top];
		top = top + 1;
		return currentValue;
	}

	}
	int main(){
		int poppedItem = pop();
		printf("Popped: %d\n", poppedItem);
		return 0;
	}
```

#### Displaying stack data

```
void display(){
		if (top == -1){
			printf("Stack if empty\n");
			return;
		}
		printf("stack elements\n");
		    for(int i = top; i>= 0; i--){
		        printf("%d ", stack[i]);
		    }
		    printf("\n");
		
	}
```

## QUEUE

#### ENQUEUEING ELEMENTS TO THE QUEUE

```
#include <stdio.h>
#define MAX 5

int queue[MAX], fromt=0, rear= -1;
//function to enqueue(insert) an element

void enqueue(int value){
    if( rear == MAX -1){
        printf("Queue Overflow! cannot enqueue %d\n", value);
        return ;
    }
    rear+=1;
    queue[rear]=value;
    printf("%d enqueued to queue\n", value);
}

int main(){
    enqueue(69);
    enqueue(420);
    enqueue(34);
    enqueue(35);
    enqueue(42);
    enqueue(0);
}


```

#### DEQUEUEING ELEMENTS TO THE QUEUE

```
int dequeue(){
    if(front > rear){
        printf("Queue Underflow! Cannot dequeue\n");
        return -1;
    }
    int removed = queue[front];
    front+=1;
    if (front > rear){
        front =0;
        rear = -1;
    }
    return removed;
}



int main(){
    int removed = dequeue();
    printf("dequeud element %d\n", removed);
}
```

#### main code w displaying
```
#include <stdio.h>
#define MAX 5

int queue[MAX], front=0, rear= -1;
//function to enqueue(insert) an element

void enqueue(int value){
    if( rear == MAX -1){
        printf("Queue Overflow! cannot enqueue %d\n", value);
        return ;
    }
    rear+=1;
    queue[rear]=value;
    printf("%d enqueued to queue\n", value);
}

int dequeue(){
    if(front > rear){
        printf("Queue Underflow! Cannot dequeue\n");
        return -1;
    }
    int removed = queue[front];
    front+=1;
    if (front > rear){
        front =0;
        rear = -1;
    }
    return removed;
}

void display(){
    if(front > rear){
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for(int i = front; i<= rear; i++){
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main(){
    enqueue(69);
    enqueue(420);
    enqueue(34);
    enqueue(35);
    enqueue(42);
    enqueue(0);
    display();
    int removed = dequeue();
    printf("dequeud element %d\n", removed);
    display();
    
}


```


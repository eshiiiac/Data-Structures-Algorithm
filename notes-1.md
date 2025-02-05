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
	top = top-1;
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


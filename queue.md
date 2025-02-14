```
#include<stdio.h>
#include<stdlib.h>
int queue[4],n=4,front=-1,rear=-1;

void enqueue();
int dequeue();
void display();

void main(){
    int choice;
    printf("1: Insert an element into queue \n");
    printf("2: remove an element from queue \n");
    printf("3: Display the queue element \n");
    printf("4: exit");
    
  while(1){
      printf("\n Enter your choice:");
      scanf("%d",&choice);
      
      switch(choice){
          case 1:
          enqueue();
          break;
          
          case 2:
           dequeue();
         break;
          case 3:
          display();
         break;
          case 4:
           exit(0);
         break;
         
         default:
         printf("\n Invalid choice");
         break;
     }
  }
}

void enqueue(){
    int element;
    printf("\n Enter the element:");
    scanf("%d",&element);
    
    if((rear+1) %n == front){
        printf("The Queue is full");
    } else if(front == -1 && rear == -1){
        front=0;
        rear=0;
        queue[rear]=element;
    } else{
        rear =(rear + 1)%n;
        queue[rear]=element;
    }
}

int dequeue(){
    if(front == -1){
        printf("\n The queue is empty cannot dequeue");
    } else if(front == rear){
        printf("\n The dequeued element is:%d\n",queue[front]);
        front ==-1;
        rear =-1;
    } else{
        printf("\n The dequed element is %d \n",queue[front+1]);
        front =(front +1)%n;
    }
}

void display(){
    if(front == -1){
        printf("\n The Queue is empty");
        return;
    }
    printf("\n Elements in circular queue are:");
    
    if(rear >= front){
        for(int i=front;i<=rear;i++){
            printf("%d ",queue[i]);
        }
    } else{
        for(int i=front;i<=rear;i++){
            printf("%d ",queue[i]);
        }
    }
}
```

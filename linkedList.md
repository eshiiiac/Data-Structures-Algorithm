```
    // Online C compiler to run C program online
    #include <stdio.h>
    
    #define MAX 100
    int data[MAX];
    int next[MAX];
    int head = -1;
    int freeIndex = 0;
    
    void insertEnd(int value) {
        if (freeIndex >= MAX){
            printf("list is full");
            return;
        }
        
        int newNode = freeIndex++;
        data[newNode]=value;
        next[newNode] = -1;
        
        if (head==-1){
            head = newNode;
            return;
        }
        int tem = head;
        while(next[temp] !=-1){
            
        }
        
    }
    
    void displayList(){
        if(head==-1){
            printf("list is empty");
            return;
        }
        int temp = head;
        printf("%d", data[temp]);
        while(temp != -1){
            printf("%d -> ", data[temp]);
            temp = next[temp];
        }
        printf("NULL\n");
    }
    
    void deleteNode(int value){
        if (head == -1) return;
        int temp = head, prev = -1;
        while(temp != -1 && data[temp] != value) {
            prev = temp;
            temp = next[temp];
        }
        if(temp==-1) return;
        
        if (prev == -1){
            head = next[temp];
        }else {
            next[prev] = next[temp];
        }
    }
    int main(){
        insertEnd(10);
        insertEnd(20);
        insertEnd(30);
        
        displayList();
        
        deleteNode(20);
        printf("After deleting 20: ");
        displayList();
    }
```

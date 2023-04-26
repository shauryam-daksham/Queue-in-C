# DSC_Exp-6
## Queue

### Code:-
```
#include <stdio.h>
#define MAX 10

int queue[MAX];
int front = -1;
int rear = -1;

void enqueue(void);
int dequeue(void);
void display(void);

int main()
{
    int option, val;
    do
    {
        printf("MENU\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display\n");
        printf("4. EXIT\n");
        printf("Choose option: ");
        scanf("%d", &option);
        switch(option)
        {
            case 1:
                enqueue();
                break;
            case 2:
                val = dequeue();
                if(val != -1)
                {
                    printf("The number deleted is: %d\n", val);
                }
                break;
            case 3:
                display();
                break;
        }
    } while (option != 4);
    return 0;
}

void enqueue()
{
    int num;
    printf("Enter number to be inserted: ");
    scanf("%d", &num);
    if(rear == MAX - 1)
    {
        printf("Overflow\n");
    }
    else if(front == -1 && rear == -1)
    {
        front = rear = 0;
    }
    else 
    {
        rear++;
    }
    queue[rear] = num;
}

int dequeue()
{
    int val;
    if(front == -1 || front > rear)
    {
        printf("Underflow\n");
        return -1;  
    }
    else
    {
        val = queue[front];
        front++;
    }
    if(front > rear)
    {
        front = rear = -1;
        return val;
    }
}

void display()
{
    int i;
    if(front == -1 || front > rear)
    {
        printf("Queue is empty\n");
    }
    else 
    {
        printf("Queue elements are: ");
        for(i = front; i <= rear; i++)
        {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}
```
### Output:-
![image](https://user-images.githubusercontent.com/124967782/230789080-dbb764c8-24ee-4851-bd70-ef2ecfdd9c9a.png)

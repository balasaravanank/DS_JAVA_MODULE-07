# Ex6 Right Rotation LinkedList
## DATE: 23.11.2025
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm
1. Traverse the list to find its length and last node.
2. Connect the last node to the head to form a circular list.
3. Reduce k by doing k = k % length.
4. Move (length − k) steps from the last node to locate the new tail.
5. Break the circle by setting newtail.next = null and return the new head.
## Program:
```java
/*
Program to  Right Rotation LinkedList
Developed by: BALA SARAVANAN K
RegisterNumber:  212224230031
*/
import java.util.Scanner;
public class RotateLinkedList {
    public static Node rotate(Node head, int k) {
        if(head==null) return head;
        Node temp=head;
        int length=1;
        while(temp.next!=null){
            temp=temp.next;
            length++;
        }
        temp.next=head;
        
        k=k%length;
        int pos=length-k;
        
        Node newtail=temp;
        for(int i=0;i<pos;i++){
            newtail=newtail.next;
        }
        Node newhead=newtail.next;
        newtail.next=null;

       return newhead;
    }
    public static void display(Node head) {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Node head = null, tail = null;
        int n = scanner.nextInt();
        for (int i = 0; i < n; i++) {
            Node newNode = new Node(scanner.nextInt());
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }
        int k = scanner.nextInt();
        head = rotate(head, k);
        display(head);
        scanner.close();
    }
}
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

```

## Output:
<img width="925" height="242" alt="image" src="https://github.com/user-attachments/assets/606fdf01-fc36-46f5-810e-b2ddc6f74154" />



## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.

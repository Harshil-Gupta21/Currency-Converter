# LinkedList

### Singly Linked List

### **1. Insertion at Beginning**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int x) {
        Node temp = new Node();
        temp.data = x;
        temp.next = head;
        head = temp;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class InsertionAtBeginning {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();
    }
}
```

### Output

```java
44->33->22->11->
```

#

### **2. Insertion at Last**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int x) {
        Node temp = new Node();
        temp.data = x;
        temp.next = null;

        if (head == null) {
            head = temp;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = temp;
        }
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class InsertionAtLast {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
```

#

### **3. Insertion after any Node**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.next = null;

        if (head == null) {
            head = new_node;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = new_node;
        }
    }

    public void insertAfter(Node prev_node, int new_data) {
        if (prev_node == null) {
            System.out.println("The given previous node cannot be null");
            return;
        }

        Node new_node = new Node();
        new_node.data = new_data;
        new_node.next = prev_node.next;
        prev_node.next = new_node;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class InsertionAfterNode {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.insertAfter(obj.head.next, 55);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
11->22->55->33->44->
```

#

### **4. Deletion at Beginning**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int x) {
        Node temp = new Node();
        temp.data = x;
        temp.next = head;
        head = temp;
    }

    public void delete() {
        head = head.next;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class DeletionAtBeginning {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.delete();

        obj.display();
    }
}
```

### Output

```java
44->33->22->11->
33->22->11->
```

#

### **5. Deletion at Last**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int x) {
        Node temp = new Node();
        temp.data = x;
        temp.next = null;

        if (head == null) {
            head = temp;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = temp;
        }
    }

    public void delete() {
        Node temp = head;
        Node last = null;

        while (temp.next != null) {
            last = temp;
            temp = temp.next;
        }

        last.next = null;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class DeletionAtLast {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.delete();

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
11->22->33->
```

#

### **6. Deletion after any Node**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.next = null;

        if (head == null) {
            head = new_node;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = new_node;
        }
    }

    public void deleteAfter(Node prev_node) {
        if (prev_node == null) {
            System.out.println("The given previous node cannot be null");
            return;
        }

        prev_node.next = prev_node.next.next;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class DeletionAfterNode {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.deleteAfter(obj.head.next);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
11->22->44->
```

#

### Doubly Linked List

### **7. Insertion**

```java
class Node {
    int data;
    Node prev;
    Node next;
}

class DoublyLinkedList {
    Node head;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.prev = null;
        new_node.next = null;

        if (head == null) {
            head = new_node;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = new_node;
            new_node.prev = last;
        }
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class Insertion {
    public static void main(String[] args) {
        DoublyLinkedList obj = new DoublyLinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
```

#

### **8. Deletion**

```java
class Node {
    int data;
    Node prev;
    Node next;
}

class DoublyLinkedList {
    Node head;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.prev = null;
        new_node.next = null;

        if (head == null) {
            head = new_node;
        } else {
            Node last = head;
            while (last.next != null) {
                last = last.next;
            }
            last.next = new_node;
            new_node.prev = last;
        }
    }

    public void delete() {
        Node temp = head;
        Node last = null;

        while (temp.next != null) {
            last = temp;
            temp = temp.next;
        }

        last.next = null;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class Deletion {
    public static void main(String[] args) {
        DoublyLinkedList obj = new DoublyLinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.delete();

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
11->22->33->
```

#

### Circular Linked List

### **9. Insertion**

```java
class Node {
    int data;
    Node next;
}

class CircularLinkedList {
    Node last;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.next = null;

        if (last == null) {
            last = new_node;
            last.next = new_node;
        } else {
            new_node.next = last.next;
            last.next = new_node;
            last = new_node;
        }
    }

    public void display() {
        Node temp = last.next;
        do {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        } while (temp != last.next);
    }
}

public class Insertion {
    public static void main(String[] args) {
        CircularLinkedList obj = new CircularLinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
```

#

### **10. Deletion**

```java
class Node {
    int data;
    Node next;
}

class CircularLinkedList {
    Node last;

    public void insert(int data) {
        Node new_node = new Node();
        new_node.data = data;
        new_node.next = null;

        if (last == null) {
            last = new_node;
            last.next = new_node;
        } else {
            new_node.next = last.next;
            last.next = new_node;
            last = new_node;
        }
    }

    public void delete() {
        Node temp = last.next;
        Node prev = last;
        do {
            prev = temp;
            temp = temp.next;
        } while (temp != last.next);

        prev.next = temp.next;
        last = prev;
    }

    public void display() {
        Node temp = last.next;
        do {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        } while (temp != last.next);
    }
}

public class Deletion {
    public static void main(String[] args) {
        CircularLinkedList obj = new CircularLinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.delete();

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
11->22->33->
```

#

### **11. Reverse a Linked List**

```java
class Node {
    int data;
    Node next;
}

class LinkedList {
    Node head;

    public void insert(int x) {
        Node temp = new Node();
        temp.data = x;
        temp.next = head;
        head = temp;
    }

    public void reverse() {
        Node current = head;
        Node prev = null;
        Node next = null;

        while (current != null) {
            next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }
        head = prev;
    }

    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class Reverse {
    public static void main(String[] args) {
        LinkedList obj = new LinkedList();
        obj.insert(11);
        obj.insert(22);
        obj.insert(33);
        obj.insert(44);

        obj.display();

        obj.reverse();

        obj.display();
    }
}
```

### Output

```java
44->33->22->11->
11->22->33->44->
```

#

# Stack

### **1. Push Operation**

```java
class Node {
    int data;
    Node next;
}

class Stack {
    private Node top;

    public void push(int x) {
        Node temp = new Node();

        temp.data = x;
        temp.next = top;
        top = temp;
    }

    public boolean isEmpty() {
        return top == null;
    }

    public int peek() {
        if (!isEmpty()) {
            return top.data;
        } else {
            System.out.println("Stack is empty");
            return -1;
        }
    }

    public void display() {
        if (top == null) {
            System.out.printf("\nStack Underflow");
            System.exit(1);
        } else {
            Node temp = top;
            while (temp != null) {
                System.out.printf("%d->", temp.data);
                temp = temp.next;
            }
        }
    }
}

public class Push {
    public static void main(String[] args) {
        Stack obj = new Stack();
        obj.push(11);
        obj.push(22);
        obj.push(33);
        obj.push(44);

        obj.display();

        System.out.printf("\nTop element is %d\n", obj.peek());

        obj.display();

        System.out.printf("\nTop element is %d\n", obj.peek());
    }
}
```

### Output

```java
44->33->22->11->
Top element is 44
105->95->44->33->22->11->
Top element is 105
```

#

### **2. Pop Operation**

```java
class Node {
    int data;
    Node next;
}

class Stack {
    private Node top;

    public void push(int x) {
        Node temp = new Node();

        temp.data = x;
        temp.next = top;
        top = temp;
    }

    public boolean isEmpty() {
        return top == null;
    }

    public int peek() {
        if (!isEmpty()) {
            return top.data;
        } else {
            System.out.println("Stack is empty");
            return -1;
        }
    }

    public void pop() {
        if (top == null) {
            System.out.print("\nStack Underflow");
            return;
        }
        top = top.next;
    }

    public void display() {
        if (top == null) {
            System.out.printf("\nStack Underflow");
            System.exit(1);
        } else {
            Node temp = top;
            while (temp != null) {
                System.out.printf("%d->", temp.data);
                temp = temp.next;
            }
        }
    }
}

public class Pop {
    public static void main(String[] args) {
        Stack obj = new Stack();
        obj.push(11);
        obj.push(22);
        obj.push(33);
        obj.push(44);

        obj.display();

        System.out.printf("\nTop element is %d\n", obj.peek());

        obj.pop();
        obj.pop();

        obj.display();

        System.out.printf("\nTop element is %d\n", obj.peek());
    }
}
```

### Output

```java
44->33->22->11->
Top element is 44
22->11->
Top element is 22
```

#

### **3. Infix to Postfix**

```java
class Node {
    char data;
    Node next;
}

class Stack {
    private Node top;

    public void push(char x) {
        Node temp = new Node();

        temp.data = x;
        temp.next = top;
        top = temp;
    }

    public boolean isEmpty() {
        return top == null;
    }

    public char peek() {
        if (!isEmpty()) {
            return top.data;
        } else {
            System.out.println("Stack is empty");
            return 0;
        }
    }

    public char pop() {
        if (top == null) {
            System.out.print("\nStack Underflow");
            return 0;
        }
        char x = top.data;
        top = top.next;
        return x;
    }

    public void display() {
        if (top == null) {
            System.out.printf("\nStack Underflow");
            System.exit(1);
        } else {
            Node temp = top;
            while (temp != null) {
                System.out.printf("%c->", temp.data);
                temp = temp.next;
            }
        }
    }
}

public class Conversion {
    public static int precedence(char ch) {
        switch (ch) {
            case '+':
            case '-':
                return 1;

            case '*':
            case '/':
                return 2;

            case '^':
                return 3;
        }
        return -1;
    }

    public static String infixToPostfix(String exp) {
        String result = new String("");
        Stack stack = new Stack();

        for (int i = 0; i < exp.length(); ++i) {
            char c = exp.charAt(i);

            if (Character.isLetterOrDigit(c)) {
                result += c;
            } else if (c == '(') {
                stack.push(c);
            } else if (c == ')') {
                while (!stack.isEmpty() && stack.peek() != '(') {
                    result += stack.pop();
                }
                if (!stack.isEmpty() && stack.peek() != '(') {
                    return "Invalid Expression";
                } else {
                    stack.pop();
                }
            } else {
                while (!stack.isEmpty() && precedence(c) <= precedence(stack.peek())) {
                    result += stack.pop();
                }
                stack.push(c);
            }
        }

        while (!stack.isEmpty()) {
            result += stack.pop();
        }

        return result;
    }

    public static void main(String[] args) {
        String exp = "a+b*(c^d-e)^(f+g*h)-i";
        System.out.println(infixToPostfix(exp));
    }
}
```

### Output

```java
abcd^e-fgh*+^*+i-
```

#

# Queue

### **1.Enqueue Operation**

```java
class Node {
    int data;
    Node next;
}

class Queue {
    private Node front;
    private Node rear;

    public void enqueue(int x) {
        Node temp = new Node();

        temp.data = x;
        temp.next = null;

        if (front == null && rear == null) {
            front = rear = temp;
            return;
        }

        rear.next = temp;
        rear = temp;
    }

    public void display() {
        Node temp = front;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class Enqueue {
    public static void main(String[] args) {
        Queue obj = new Queue();
        obj.enqueue(11);
        obj.enqueue(22);
        obj.enqueue(33);
        obj.enqueue(44);

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
```

#

### **2. Dequeue Operation**

```java
class Node {
    int data;
    Node next;
}

class Queue {
    private Node front;
    private Node rear;

    public void enqueue(int x) {
        Node temp = new Node();

        temp.data = x;
        temp.next = null;

        if (front == null && rear == null) {
            front = rear = temp;
            return;
        }

        rear.next = temp;
        rear = temp;
    }

    public void dequeue() {
        if (front == null) {
            System.out.println("\nQueue is empty");
            return;
        }

        if (front == rear) {
            front = rear = null;
        } else {
            front = front.next;
        }
    }

    public void display() {
        Node temp = front;
        while (temp != null) {
            System.out.printf("%d->", temp.data);
            temp = temp.next;
        }
    }
}

public class Dequeue {
    public static void main(String[] args) {
        Queue obj = new Queue();
        obj.enqueue(11);
        obj.enqueue(22);
        obj.enqueue(33);
        obj.enqueue(44);

        obj.display();

        obj.dequeue();
        obj.dequeue();

        obj.display();
    }
}
```

### Output

```java
11->22->33->44->
33->44->
```

#

# Trees

### **1. Inorder Traversal**

```java
class Node {
    int data;
    Node left;
    Node right;

    Node(int data) {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}

public class Inorder {
    Node root;

    public Inorder() {
        root = null;
    }

    public void inorder(Node temp) {
        if (temp == null) {
            return;
        }

        inorder(temp.left);
        System.out.printf("%d->", temp.data);
        inorder(temp.right);
    }

    public static void main(String[] args) {
        Inorder obj = new Inorder();
        obj.root = new Node(1);
        obj.root.left = new Node(2);
        obj.root.right = new Node(3);
        obj.root.left.left = new Node(4);
        obj.root.left.right = new Node(5);

        obj.inorder(obj.root);
    }
}
```

### Output

```java
4->2->5->1->3->
```

#

### **2. Preorder Traversal**

```java
class Node {
    int data;
    Node left;
    Node right;

    Node(int data) {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}

public class Preorder {
    Node root;

    public Preorder() {
        root = null;
    }

    public void preorder(Node temp) {
        if (temp == null) {
            return;
        }

        System.out.printf("%d->", temp.data);
        preorder(temp.left);
        preorder(temp.right);
    }

    public static void main(String[] args) {
        Preorder obj = new Preorder();
        obj.root = new Node(1);
        obj.root.left = new Node(2);
        obj.root.right = new Node(3);
        obj.root.left.left = new Node(4);
        obj.root.left.right = new Node(5);

        obj.preorder(obj.root);
    }
}
```

### Output

```java
1->2->4->5->3->
```

#

### **3. Postorder Traversal**

```java
class Node {
    int data;
    Node left;
    Node right;

    Node(int data) {
        this.data = data;
        this.left = null;
        this.right = null;
    }
}

public class Postorder {
    Node root;

    public Postorder() {
        root = null;
    }

    public void postorder(Node temp) {
        if (temp == null) {
            return;
        }

        postorder(temp.left);
        postorder(temp.right);
        System.out.printf("%d->", temp.data);
    }

    public static void main(String[] args) {
        Postorder obj = new Postorder();
        obj.root = new Node(1);
        obj.root.left = new Node(2);
        obj.root.right = new Node(3);
        obj.root.left.left = new Node(4);
        obj.root.left.right = new Node(5);

        obj.postorder(obj.root);
    }
}
```

### Output

```java
4->5->2->3->1->
```

#

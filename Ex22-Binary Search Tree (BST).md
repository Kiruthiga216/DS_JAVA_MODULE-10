# Ex22 Searching for a Book ID in a Binary Search Tree (BST)

## AIM:
To design and implement java program that constructs a Binary Search Tree (BST) using given Book IDs and checks whether a specific Book ID exists in the BST.

## Algorithm

Start the program.

Read integer.

Initialize root equals to null.

Repeat n times.

Insert(root, key).

Searching Book ID.

Search(root, key).

Stop the program.   

## Program:
```
/*
Program to constructs a Binary Search Tree (BST) using given Book IDs 
Developed by: KIRUTHIGA.B
RegisterNumber:  212224040160
*/

import java.util.*;

public class BookIDSearch {
    static class Node {
        int data;
        Node left, right;
        Node(int data) {
            this.data = data;
        }
    }

    public static Node insert(Node root, int key) {
        if (root == null) return new Node(key);
        if (key < root.data) root.left = insert(root.left, key);
        else root.right = insert(root.right, key);
        return root;
    }

    public static boolean search(Node root, int key) {
        if (root == null) return false;
        if (root.data == key) return true;
        if (key < root.data) return search(root.left, key);
        else return search(root.right, key);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Node root = null;
        for (int i = 0; i < n; i++) {
            root = insert(root, sc.nextInt());
        }
        int q = sc.nextInt();
        while (q-- > 0) {
            int key = sc.nextInt();
            System.out.println(search(root, key) ? "Found" : "Not Found");
        }
    }
}

```

## Output:

<img width="516" height="255" alt="image" src="https://github.com/user-attachments/assets/4a1d08eb-0089-4247-932f-9e16c2ece730" />



## Result:
The program has been successfully implemented and executed.
It constructs a Binary Search Tree from the given Book IDs and accurately determines whether a queried Book ID exists in the library system.

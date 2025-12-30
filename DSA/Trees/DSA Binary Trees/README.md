```c
#include <stdio.h>
#include <stdlib.h>

// Structure of a Binary Tree Node
struct Node {
    int data;
    struct Node *left, *right;
};

// Create new node
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}

// Print all nodes
void printNodes(struct Node* root) {
    if (root == NULL) return;

    printf("%d ", root->data);
    printNodes(root->left);
    printNodes(root->right);
}

// Print leaf nodes
void printLeafNodes(struct Node* root) {
    if (root == NULL) return;

    if (root->left == NULL && root->right == NULL)
        printf("%d ", root->data);

    printLeafNodes(root->left);
    printLeafNodes(root->right);
}

// Print parent nodes
void printParentNodes(struct Node* root) {
    if (root == NULL) return;

    if (root->left != NULL || root->right != NULL)
        printf("%d ", root->data);

    printParentNodes(root->left);
    printParentNodes(root->right);
}

// Print edges
void printEdges(struct Node* root) {
    if (root == NULL) return;

    if (root->left != NULL)
        printf("(%d -> %d) ", root->data, root->left->data);

    if (root->right != NULL)
        printf("(%d -> %d) ", root->data, root->right->data);

    printEdges(root->left);
    printEdges(root->right);
}

// Tree height
int treeHeight(struct Node* root) {
    if (root == NULL)
        return 0;

    int leftHeight = treeHeight(root->left);
    int rightHeight = treeHeight(root->right);

    return (leftHeight > rightHeight ? leftHeight : rightHeight) + 1;
}

// Tree size
int treeSize(struct Node* root) {
    if (root == NULL)
        return 0;

    return treeSize(root->left) + treeSize(root->right) + 1;
}

int main() {
    // Creating Binary Tree
    struct Node* root = createNode(10);

    root->left = createNode(8);
    root->left->left = createNode(6);
    root->left->right = createNode(7);

    root->right = createNode(20);
    root->right->left = createNode(15);
    root->right->right = createNode(22);

    // Root node
    printf("Root Node: %d\n", root->data);

    // All nodes
    printf("All Nodes: ");
    printNodes(root);

    // Leaf nodes
    printf("\nLeaf Nodes: ");
    printLeafNodes(root);

    // Parent nodes
    printf("\nParent Nodes: ");
    printParentNodes(root);

    // Edges
    printf("\nEdges: ");
    printEdges(root);

    // Height & Size
    printf("\nTree Height: %d", treeHeight(root));
    printf("\nTree Size: %d", treeSize(root));

    return 0;
}
```

```
Root Node: 10
All Nodes: 10 8 6 7 20 15 22
Leaf Nodes: 6 7 15 22
Parent Nodes: 10 8 20
Edges: (10 -> 8) (10 -> 20) (8 -> 6) (8 -> 7) (20 -> 15) (20 -> 22)
Tree Height: 3
Tree Size: 7
```
}

// Вспомогательная функция для вставки узла (для тестирования)
Node* insertNode(Node* root, int key) {
    if (root == nullptr) {
        return new Node(key);
    }
    if (key < root->value) {
        root->left = insertNode(root->left, key);
    } else {
        root->right = insertNode(root->right, key);
    }
    return root;
}

// Обход дерева (in-order) для проверки результата
void inorderTraversal(Node* root) {
    if (root != nullptr) {
        inorderTraversal(root->left);
        cout << root->value << " ";
        inorderTraversal(root->right);
    }
}

int main() {
    Node* root = nullptr;
    root = insertNode(root, 50);
    root = insertNode(root, 30);
    root = insertNode(root, 70);
    root = insertNode(root, 20);
    root = insertNode(root, 40);
    root = insertNode(root, 60);
    root = insertNode(root, 80);

    cout << "Tree before deletion: ";
    inorderTraversal(root);
    cout << endl;

    root = deleteNode(root, 50);

    cout << "Tree after deletion: ";
    inorderTraversal(root);
    cout << endl;

    return 0;
}

# pre-post-inorder-in-binary-tree.
package Trees;

public class PreInPost {
    public static void pip(int n) {
        if (n == 0) return;
        System.out.println("Pre" + n);
        pip(n - 1);
        System.out.println("In" + n);
        pip(n - 1);
        System.out.println("Post" + n);
    }

    public static class Node {
        int val;
        Node left;
        Node right;

        public Node(int val) {
            this.val = val;
        }
    }

    public static void preorder(Node root) {
        // Preorder: root, left, right
        if (root == null) return;
        System.out.println(root.val);
        preorder(root.left);
        preorder(root.right);
    }

    public static void inorder(Node root) {
        // Inorder: left, root, right
        if (root == null) return;
        inorder(root.left);
        System.out.println(root.val);
        inorder(root.right);
    }

    public static void postorder(Node root) {
        // Postorder: left, right, root
        if (root == null) return;
        postorder(root.left);
        postorder(root.right);
        System.out.println(root.val);
    }

    public static void main(String[] args) {
        Node root = new Node(1);
        Node a = new Node(2);
        Node b = new Node(3);
        root.left = a;
        root.right = b;

        Node c = new Node(4);
        Node d = new Node(5);
        a.left = c;
        a.right = d;

        Node e = new Node(6);
        Node f = new Node(7);
        b.left = e;
        b.right = f;

        System.out.println("Preorder:");
        preorder(root);

        System.out.println("Inorder:");
        inorder(root);

        System.out.println("Postorder:");
        postorder(root);
    }
}

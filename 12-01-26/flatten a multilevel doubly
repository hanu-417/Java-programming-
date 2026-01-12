class Solution {
    public Node flatten(Node head) {
        if (head == null) 
            return null;

        Stack<Node> stack = new Stack<>();
        Node curr = head;

        while (curr != null) {

            // If child exists
            if (curr.child != null) {
                if (curr.next != null) {
                    stack.push(curr.next); // store next node for later
                }

                curr.next = curr.child;
                curr.child.prev = curr;
                curr.child = null; // important: remove child link
            }

            // If end of list and stack has nodes to process
            if (curr.next == null && !stack.isEmpty()) {
                Node next = stack.pop();
                curr.next = next;
                next.prev = curr;
            }

            curr = curr.next;
        }

        return head;
    }
}

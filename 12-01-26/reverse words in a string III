class Solution {

    // Reverses characters in the array from index i to j (in-place)
    void reverse(char ch[], int i, int j) {
        while (i < j) {
            char temp = ch[i];
            ch[i] = ch[j];
            ch[j] = temp;
            i++;
            j--;
        }
    }

    // Reverses each word in the string while keeping word order intact
    public String reverseWords(String s) {

        // Convert string to character array for in-place modification
        char ch[] = s.toCharArray();

        int i = 0; // pointer to traverse characters
        int j = 0; // marks the start index of a word

        // Traverse the entire character array
        while (i < ch.length) {

            // When space is found, reverse the word before it
            if (ch[i] == ' ') {
                reverse(ch, j, i - 1);
                i++;        // move past the space
                j = i;      // next word starts after space
            } else {
                i++;        // continue traversing current word
            }
        }

        // Reverse the last word (as it won't be followed by a space)
        reverse(ch, j, ch.length - 1);

        // Convert character array back to string
        return new String(ch);
    }
}

class Solution {
    public double calculateTax(int[][] brackets, int income) {
        return IntStream.range(0, brackets.length)
            .mapToDouble(i -> Math.max(0, (Math.min(income, brackets[i][0]) - (i == 0 ? 0 : brackets[i - 1][0]))) * brackets[i][1] / 100.0)
            .sum();
    }
}

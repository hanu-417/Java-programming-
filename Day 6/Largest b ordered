class Solution {
    public int largest1BorderedSquare(int[][] grid) {
        int m = grid.length, n = grid[0].length;
        int max = 0;

        // Try all possible square sizes, starting from the largest
        for (int size = Math.min(m, n); size > 0; size--) {
            for (int r = 0; r + size <= m; r++) {
                for (int c = 0; c + size <= n; c++) {
                    if (isValid(grid, r, c, size)) {
                        return size * size; // Return the largest area immediately
                    }
                }
            }
        }

        return 0;
    }

    private boolean isValid(int[][] g, int r, int c, int size) {
        // top border
        for (int j = c; j < c + size; j++) {
            if (g[r][j] == 0) return false;
        }

        // bottom border
        for (int j = c; j < c + size; j++) {
            if (g[r + size - 1][j] == 0) return false;
        }

        // left border
        for (int i = r; i < r + size; i++) {
            if (g[i][c] == 0) return false;
        }

        // right border
        for (int i = r; i < r + size; i++) {
            if (g[i][c + size - 1] == 0) return false;
        }

        return true;
    }
}

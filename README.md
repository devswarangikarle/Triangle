# Triangle

Given a triangle array, return the minimum path sum from top to bottom.
For each step, you may move to an adjacent number of the row below. More formally, if you are on index i on the current row, you may move to either index i or index i + 1 on the next row.

class Solution(object):

    def minimumTotal(self, triangle):
        n = len(triangle)
        # Start from the second last row and move upwards
        for i in range(n - 2, -1, -1):
            for j in range(len(triangle[i])):
                min_sum = min(triangle[i + 1][j], triangle[i + 1][j + 1])
                current_val = triangle[i][j]
                triangle[i][j] = current_val + min_sum
        return triangle[0][0]

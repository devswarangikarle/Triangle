# Triangle

Given a triangle array, return the minimum path sum from top to bottom.
For each step, you may move to an adjacent number of the row below. More formally, if you are on index i on the current row, you may move to either index i or index i + 1 on the next row.

def recursion(l,x,y,ans=0):
    if x>=len(l):
        return ans
    ans += l[x][y]
    mx = min(recursion(l,x+1,y,ans),recursion(l,x+1,y+1,ans))
    return mx
class Solution:
    def minimumTotal(self, triangle: List[List[int]]) -> int:
        return recursion(triangle,0,0,0)

# 17-05-22-ass-1
class Solution:
    def pivotIndex(self, arr: List[int]) -> int:
        n=len(arr)
        a=[0]*n
        a[0]=arr[0]
        for i in range(1,n):
            a[i]=a[i-1]+arr[i]
        for i in range(n):
            if i==0:
                left=0
            else:
                left=a[i-1]
            right=a[n-1]-a[i]
            if left==right:
                return i
        return -1
        

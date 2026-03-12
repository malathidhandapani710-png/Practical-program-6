class Solution:
    def binarysearch(self, arr, k):
        low = 0
        high = len(arr) - 1
        result = -1
        
        while low <= high:
            mid = low + (high - low) // 2
            
            if arr[mid] == k:
                # Potential answer found
                result = mid
                # Continue searching left for the smallest index
                high = mid - 1
            elif arr[mid] < k:
                low = mid + 1
            else:
                high = mid - 1
                
        return result

# Find-the-odd-one-out
You're given an integer array, in which each element is present thrice except for one.  Find the number that is present only once. .  Constraints 1 &lt;= n &lt;= 105 1 &lt;= arr[i] &lt;= 105

def find_single_occurrence(arr):
    result = 0
    for i in range(32):
        count = 0
        for num in arr:
            count += (num >> i) & 1

        if count % 3 != 0:
            result |= (1 << i)

    return result

n = int(input())
arr = list(map(int, input().split()))

print(find_single_occurrence(arr))

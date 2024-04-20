testArray1 = [54, 9, 2, 8, 1, 90, 5]  # Odd
#For some reason when swaping the 9 with 7 in the odd array it dosent work correctly
testArray2 = [45, 6, 2, 7, 1, 87, 8, 19]  # Even


def swap(A, i, j):
    A[i], A[j] = A[j], A[i]

def sort(A):
    first = 0
    last = len(A) - 1

    while first < last:
        if len(A) % 2 == 0:
            min_val = min(A[first:last+1])
            max_val = max(A[first:last+1])
            min_index = A.index(min_val)
            max_index = A.index(max_val)
            swap(A, first, min_index)
            swap(A, last, max_index)
        else:
            A.append(10000000)
            min_val = min(A[first:last])
            max_val = max(A[first:last])
            min_index = A.index(min_val)
            max_index = A.index(max_val)
            swap(A, first, min_index)
            swap(A, last, max_index)
            A.pop()
        first += 1
        last -= 1

sort(testArray1)
print(testArray1)

sort(testArray2)
print(testArray2)


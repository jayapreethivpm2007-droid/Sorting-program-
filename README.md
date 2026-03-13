Implement Bubble Sort, Selection Sort, Insertion Sort and Radix Sort

def bubble_sort(arr):
    a = arr[:]
    n = len(a)
    for i in range(n):
        for j in range(0,n-i-1):
            if a[j] > a[j+1]:
                a[j],a[j+1] = a[j+1],a[j]
    print("Bubble Sort:",a)

def selection_sort(arr):
    a = arr[:]
    n = len(a)
    for i in range(n):
        min = i
        for j in range(i+1,n):
            if a[j] < a[min]:
                min = j
        a[i],a[min] = a[min],a[i]
    print("Selection Sort:",a)

def insertion_sort(arr):
    a = arr[:]
    for i in range(1,len(a)):
        key = a[i]
        j = i-1
        while j>=0 and key<a[j]:
            a[j+1]=a[j]
            j=j-1
        a[j+1]=key
    print("Insertion Sort:",a)

def counting_sort(arr,exp):
    n=len(arr)
    output=[0]*n
    count=[0]*10

    for i in range(n):
        index=arr[i]/exp
        count[(index)%10]+=1

    for i in range(1,10):
        count[i]+=count[i-1]

    i=n-1
    while i>=0:
        index=arr[i]/exp
        output[count[(index)%10]-1]=arr[i]
        count[(index)%10]-=1
        i-=1

    for i in range(n):
        arr[i]=output[i]

def radix_sort(arr):
    a = arr[:]
    max1=max(a)
    exp=1
    while max1/exp>0:
        counting_sort(a,exp)
        exp*=10
    print("Radix Sort:",a)

arr = [64,34,25,12,22]

print("Original Array:",arr)

bubble_sort(arr)
selection_sort(arr)
insertion_sort(arr)
radix_sort(arr)

Output:
Original Array: [64, 34, 25, 12, 22]

Bubble Sort: [12, 22, 25, 34, 64]

Selection Sort: [12, 22, 25, 34, 64]

Insertion Sort: [12, 22, 25, 34, 64]

Radix Sort: [12, 22, 25, 34, 64]# Sorting-program-
Data structure practical 

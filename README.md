from numpy import *

# one way to create array
arr = array([1,2,3,4,5])
print(arr.dtype)    # int32
print(arr)  # output = [1,2,3,4,5]

arr = array([1,2,3,4,5.0])
print(arr.dtype)    # float64
print(arr)  # output = [1.,2.,3.,4.,5.]

arr = array([1,2,3,4,5],float)
print(arr.dtype)    # float64
print(arr)  # output = [1.,2.,3.,4.,5.]

arr = array([1,2,3,4,5],int)
print(arr.dtype)    # int32
print(arr)  # output = [1,2,3,4,5]

# Another way to create array
# linspace() end include check
arr=linspace(0,16)  #linspace(start,end,parts)
# why output in float because you breaks into parts i,e 16 parts
print(arr)  # output = [0. 1. 2. 3. 4. 5. 6. 7. 8. 9. 10. 11. 12. 13. 14. 15.]

arr=linspace(0,16,20)  #linspace(start,end,parts)
# break into 20 parts
print(arr)  # output = [0. 0.78967368 1.5789737 2.36 -------- 15.]

arr=linspace(0,15)  #linspace(start,end,parts)
# parts is not specfic then it breaks according to(0-15 = 16 parts)
print(arr)  # output = [0. 0.306----------------- 15.]

# arange(start,end,step) # end not include
arr=arange(1,15,2)
print(arr) # output = [1 5 7 9 11 13]

# logspace()
arr = logspace(1,40,5)
print(arr)
print('%.2f'%arr[0]) # for 2 digit decimal
print('%.2f'%arr[4])

# Zeroes
arr = zeros(5)
print(arr) # [0. 0. 0. 0. 0.]

# ones
arr=ones(5)
print(arr) # [1. 1. 1. 1. 1.]

arr=ones(5,int)
print(arr) # [1 1 1 1 1]



# adding arr with 5
arr = array([1,2,3,4,5])
arr=arr+5
print(arr) # [6 7 8 9 10]

# add two array. It is also called vectorized operation
arr1=array([1,2,3,4,5])
arr2=array([1,2,3,4,5])
arr3=arr1+arr2
print(arr3) #[2 4 6 8 10]

# Math operation
# trignometry operation
arr = array([1,2,3,4,5])
print(sin(arr))
print(cos(arr))
# log
print(log(arr))
#sqrt
print(sqrt(arr))
# sum of array
print(sum(arr)) # 15
# min and max
print(min(arr))
print(max(arr))
# unique elememt and also sort the array in asc or dec

#concat
arr1=array([1,2,3,4,5])
arr2=array([1,2,3,4,5])
print(concatenate(arr1,arr2))

# Copy an array
arr1=array([1,2,3,4,5])
arr2=arr1
print(arr1) # [1 2 3 4 5]
print(arr2) # [1 2 3 4 5]
# both array have same address
print(id(arr1))
print(id(arr2))
# I want to create with different address
arr1=array([1,2,3,4,5])
arr2=arr1.view()
print(arr1) # [1 2 3 4 5]
print(arr2) # [1 2 3 4 5]
# both array have different address
print(id(arr1))
print(id(arr2))

# two of copy 1. Shallow Copy 2. Deep Copy
#shallow copy = both array have different address but both array are still depend on each other
arr1=array([1,2,3,4,5])
arr2=arr1.view()
arr1[1]=7
print(arr1) # [1 7 3 4 5]
print(arr2) # [1 7 3 4 5]

# Deep Copy = both array are independ on each other
arr1=array([1,2,3,4,5])
arr2=arr1.copy()
arr1[1]=7
print(arr1) # [1 7 3 4 5]
print(arr2) # [1 2 3 4 5]

# Write a code to add 2 arrays using forloop
# write a code to find the maximum value from an array without using in-build function

# Multi dimension array
arr=array([
        [1,2,3],
        [4,5,6]
    ])
print(arr)
print(arr.dtype)
print(arr.ndim) # 2
print(arr.shape) # (2,3) i.e (rows,cols)
print(arr.size) # 6 i.e no of element

# 2D array into 1D array
arr=array([
        [1,2,3],
        [4,5,6]
    ])
arr2=arr.flatten()
print(arr2)
print(arr2.ndim)

# 2D to 3D array
arr1=array([
        [1,2,3,4,5,6],
        [7,5,2,8,9,1]
    ])
arr2= arr1.reshape(3,4) # 2D but row,col = (3,4)
arr3=arr1.reshape(2,2,3) # 3D = 2array, 2row, 3 cols
print(arr2)
print(arr3)

# Matrices
arr1=array([
        [1,2,34,2],
        [4,5,6,6]
    ])
m1 = matrix(arr1)
m2 = matrix('1 2 3; 4 5 6 ; 7 8 9')
print(m)
print(m1)
print(diagonal(m1)) # 1 5 9
print(m1.min())
print(m1.max())
# Mutiple matrices
m1 = matrix('1 2 3; 4 5 6 ; 7 8 9')
m2 = matrix('1 2 3; 4 5 6 ; 7 8 9')

m3 = m1+m2;
m4=m1*m2;
print(m3)
print(m4)

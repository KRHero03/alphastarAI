# Introduction to numpy

## Basics:
* Multidimensional array
* Same type
* Indexed by tuple of non negative integers called axes
* Numpy array vs List
	* List slow
	* Numpy fast
	* Numpy uses fixed types
	* You can specify types like int32, int16, int8
	* List element takes more space, beacuse it also need to store references, etc.
	* Numpy uses contiguous memory
	* List contains pointers to actual data
* Applications of numpy
	* Mathematical functions
	* Used with pandas
	* Machine Learning
	* Tensor are similar to numpy

## Basic Syntax

* `import numpy as np`
* Init array `a = np.array([1,2,3])`
* 2D array `a = np.array([[1.2,2.3],[1.3, 5.4]])` Note: If you create array of different number of columns in each row then it will be stored as python list.
* Nd array `a = np.array([[],[],[],[]...])`
* Find dimension `a.ndim`
* Get shape `a.shape`
* Type of elements `a.datatype` (int32 is default)
* Sepcify type `a = np.array([1,2,3], dtype=int16)`
* Find Size `a.itemsize` => datatype size
* Find total size `a.size` => total elements
* Number of bytes `a.nbytes` => Total bytes taken by arrray

## Accessing and altering syntax

* Get specific element `a[r, c]` (negative indexing is possible)
* Get specific row `a[r, :]` (Slicing operator in python)
* Get specific column `a[:, c]` 
* Synatx of such things a[start row:end row: step size, start column:end column: step size]
* ```
	a = np.array([[1,2,3,4,5,6,7], [8,9,10,11,12,13,14]])
	a[0,1:-2:2]
	``` 
	output: [2, 4, 6, 8, 10]
* Changing element `a[1,5] = 20`
* Change complete row `a[:, 2] = [1,3]` Note: Length should be same

## Different type of array
* Zero array `np.zeros((5))` `np.zeros((2,3))`
* Ones array `np.ones((5))` `np.ones((1,2))`
* Any other number `np.full((dimension), value)` `np.full((1,2), 42)`
* Reuse shape and fill array `np.full_like(arr, value)`
* Array of random number `np.random.rand(x1, x2, x3)` x => dimesion
* Random array of dimesion of other array `np.random_sample(arr.shape)`
* Random integer values `np.random.randint(startValue, endValue size=(1,2,3))`
* Identity matrix `np.identity(size)`
* Repeat array `np.repeat(arr, times, axis)` => can be used to create 2d array
* While copying array reference is used, so both arrays will be modified. Use `arr.copy()` when need to alter

## Maths
* Element wise addition subtraction `arr + constant`
* Sine/cos/tan/etc of all values `np.sin(a)` 
* Multiply matrix `np.matmul(arr1, arr2)`
* Find determinant of matrix `np.linalg.det(arr)`
* Find eigen values, inverse etc in `np.linalg`
* Find min, max, sum `np.min(arr)` `np.max(arr)`, `np.min(arr, axis=k)` `np.sum(arr, axis)`
* Reshape array `np.reshape((x1, x2, x3))`

## MISC
* Find elements > 50 `arr[arr > 50]`
* arr > 50 returns array with each element runs the condition
* Check if any data is greater than 50 in column `arr.any(arr>50, axis = 1)`
* Check if all data is greater than in 50 in ro `arr.all(arr > 50, axis = 0)`
## Data Analysis

## JupyterLab:
#### is a next-generation web-based user interface for Project Jupyter.
![kgf](https://www.tng-project.org/static/data/lab_logo_tng.png)


#### JupyterLab enables you to work with:
1. documents
2. activities such as:
      * Jupyter notebooks 
      * text editors
      * terminals
      * custom components in a flexible.


Easly arrange multiple documents and activities side by side in the work area using tabs and splitters, for example:
1. Code Consoles provide transient scratchpads for running code interactively, with full support for rich output.

2. Kernel-backed documents enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

3. Notebook cell outputs can be mirrored into their own tab, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

4. Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. 

>JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.)



## NumPy Tutorial: Data Analysis with Python




> Highlights:NumPy is one of the most fundamental libraries in Python and perhaps the most useful of them all. NumPy handles large datasets effectively and efficiently. 

#### What is the NumPy library in Python?

NumPy stands for Numerical Python and is one of the most useful scientific libraries in Python programming. It provides support for large multidimensional array objects and various tools to work with them. 

install NumPy:
```
pip install numpy
```
#### Python Lists vs NumPy Arrays – What’s the Difference?

why use NumPy arrays when we already have Python lists? 
1. Python lists are essentially an array of pointers
2.  each pointing to a location that contains the information related to the element
3. This adds a lot of overhead in terms of memory and computation.
4.  And most of this information is rendered redundant when all the objects stored in the list are of the same type!


🔑To overcome this problem, use NumPy arrays that contain only homogeneous elements🔑

* elements having the same data type. This makes it more efficient at storing and manipulating the array. 
* The difference becomes apparent when the array has a large number of elements "thousands or millions". 
* Also, with NumPy arrays, you can perform element-wise operations, something which is not possible using Python lists!

#### Creating a NumPy Array:

 * To create use the np.array() method. All you have to pass are the values of the array as a list.
 * You can specify the type of data in the dtype argument
 *  NumPy arrays can contain only homogeneous datatypes, values will be upcast if the types do not match
 * NumPy arrays can be multi-dimensional too.
  
#### to creat Numpy Array of your choice 
*  np.full() method. Just pass in the shape of the desired array and the value you want
> np.full((2,2),7)

#### Imatrix in NumPy
*  np.eye() that returns an array with 1s along its diagonal and 0s everywhere else,matrix is a square matrix that has 1s along its main diagonal and 0s everywhere else.

```
Note: A square matrix has an N x N shape. This means it has the same number of rows and columns.
# identity matrix
np.eye(3)
```

#### The Shape and Reshaping of NumPy Arrays
Once you have created your ndarray, the next thing you would want to do is check the number of axes, shape, and the size of the ndarray.

* Dimensions of NumPy arrays
You can easily determine the number of dimensions or axes of a NumPy array using the ndims attribute:
```
# number of axis
a = np.array([[5,10,15],[20,25,20]])
print('Array :','\n',a)
print('Dimensions :','\n',a.ndim)
```

* Shape of NumPy array
The shape is an attribute of the NumPy array that shows how many rows of elements are there along each dimension. 
```
a = np.array([[1,2,3],[4,5,6]])
print('Array :','\n',a)
print('Shape :','\n',a.shape)
print('Rows = ',a.shape[0])
print('Columns = ',a.shape[1])
```
* Size of NumPy array
You can determine how many values there are in the array using the size attribute:
```
# size of array
a = np.array([[5,10,15],[20,25,20]])
print('Size of array :',a.size)
```
* Reshaping a NumPy array
Reshaping a ndarray can be done using the np.reshape() method. It changes the shape of the ndarray without changing the data within the ndarray:
```
# reshape
a = np.array([3,6,9,12])
np.reshape(a,(2,2))
```
* Using NumPy To Read In Files
using the numpy.genfromtxt function.
* Use the genfromtxt function to read in the winequality-red.csv file.
* Specify the keyword argument delimiter=";" so that the fields are parsed properly.
* Specify the keyword argument skip_header=1 so that the header row is skipped. 

#### Combining NumPy Arrays
With NumPy, it’s very common to combine multiple arrays into a single unified array,use numpy.vstack to vertically stack multiple arrays.
```
white_wines = np.genfromtxt("winequality-white.csv", delimiter=";", skip_header=1)
white_wines.shape
```
# Basic Eigen

## Initialising a Matrix/Vector
To create a Matrix of dimention $\text{N}\times\text{M}$ or a vector of dimension $\text{N}$ write
```c++
	Eigen::MatrixXd A(N,M)
	Eigen::VectorXd v(N)
```
The dimensions don't have to be specified. If a Matrix of a different number-type is required, the `Matrix`-Template can be used. If the size is not known at compile-time, the row and column paramters can be set to `dynamic`.
```c++
	Eigen::Matrix<typename Scalar, int rows, int columns>
```
A random or constant Matrix can be created by the following commands respectively:
```c++
	Eigen::MatrixXd A = Eigen::MatrixXd::Random(N,M)
	Eigen::MatrixXd A = Eigen::MatrixXd::Constant(N,M,c)
```

## Acessing a Matrix
The Matrices can be filled with the `<<` command, where the filling is rowwise.
```c++
	Eigen::MatrixXd A(2,3);
	A<<1<<2<<3<<4<<5<<6;
```
A Matrix-Element can by acessed by specifying its row and column, starting with 0. It can however also be accessed with index-based notation, where the default storage order is column-major.
```c++
	A(0,0)=1;
	A(1,0)=4;
```


## Matrix-Operations

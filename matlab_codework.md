## trivial matlab functions
fullfile
f=fullfile('dir1', 'dir2', ..., 'filename')

利用文件各部分信息创建并合成完整文件名

实例：>>dirname = 'sz_data';

files = dir(fullfile(dirname, '*.xls'));

返回sz_data目录下所有以.xls结尾的数据集

exist：
exist主要有两种形式，一个参数和两个参数的，作用都是用于确定某值是否存在：
1. b = exist( a)
      若 a 存在，则 b = 1； 否则 b = 0；
2. b = exist( 'name', 'kind')
      kind 表示 name 的类型，可以取的值为：builtin（内建类型），class（类），dir（文件夹），file（文件或文件夹），var（变量）。

cell：
cell 是 matlab 中的一种数据类型，用{}来定义， {}内可以放任何类型的数据和矩阵
1. A = {[ 2, 4]} 就表示新建了一个 cell 类型的变量，这个变量包含一个 2 * 1 的矩阵，要引用 cell 类型的话，直接用下标来引用，   
      如：A{1} 就可以得到[ 2, 4] 这个矩阵了。
2. 在上述的 A 中增加一个元素：（有两种方法实现）
    （1）.B(2) = { ‘SecondElement’}；
    （2）.B{2} = ‘SecondElement’；
3.cell 函数：
    B = cell（100, 1）
   表示 给 B 赋予100 * 1 个cell元素，但未赋值

find 
index= find(X)

找出矩阵X中的所有非零元素，并将这些元素的线性索引值（linear indices：按列）返回到向量index中。

如果X是一个行向量，则index是一个行向量；否则，index是一个列向量。

如果X不含非零元素或是一个空矩阵，则index是一个空矩阵。

index = find(X, k) 或 3. index = find(X, k, ‘first’)
找到前K个不为0的线性索引值。k必须是一个正数，但是它可以是任何 数字数值类型。

index = find(X, k, ‘last’)

找到后k个不为零元素的线性索引值。

[row,col] = find(X, …)

返回矩阵X中非零元素的行和列的索引值。这个语法对于处理稀疏矩阵 尤其有用。

如果X是一个N（N>2）维矩阵，col包括列的线性索引。

[row,col,v] = find(X, …)

返回X中非零元素的一个列或行向量v，同时返回行和列的索引值。如果X是一个逻辑表示，则v是一个逻辑矩阵。输出向量v包含通过评估X表示得到的逻辑矩阵的非零元素。

sub2ind 是下标与索引相互转换用的
索引就是把整个向量或矩阵重拍成一维向量后所处的位置。如A=[1:3;4:6];
排序后就是

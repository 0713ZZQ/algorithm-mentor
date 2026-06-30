初始化：
eye(m):  生成单位矩阵 I mxm
	eye(2,4)       [1     0     0     0 ;     0     1     0     0]
ones(m,n) 生成
zeros(m,n)

函数：
isempty(A)  判断变量是否为空，返回`true`（1），A 是空数组；`false`（0）A 非空

isvector(A)  判断是否为行/列向量，返回`true`（1），A 是向量；`false`（0）A 非向量

isfield(s,name) 判断结构体（struct）是否具有某个字段
	person.name = "Tom";  person.age = 20;  isfield(person,"age")  
	得出1，person中含有age字段

diag()  构造对角矩阵，或者提取对角线
	提取对角线：A = [1 2 3;  4 5 6;  7 8 9];   diag(A)
	构造对角矩阵：v = [2 4 6];  A =diag(v)       [2  0  0   ； 0  4  0  ；  0  0  6]
		指定偏移 diag(v,k) 会放到主对角线上方第k条，为负时，下方第k条
		A = diag(v,1)  A =[ 0  2  0  0 ; 0  0  4  0 ;  0   0   0   6 ;    0   0   0   0]

C = kron(A,B)  用矩阵 A 的每个元素乘整个矩阵 B
	A = eye(2);  kron(A,B)  得到  [B   0 ；0   B]

nargin   获取函数调用时实际传入的输入参数个数
	判断输入参数个数
	设置默认参数  function y = add(a,b)   if nargin < 2  b = 10;   end   y = a+b;
		调用函数 add(5) (nargin =1<2, b=10, a=5 )ans=5+10=15
	多个可选参数
	nargout  调用函数时请求的输出参数个数
	varargin  存放可变数量输入参数的单元数组
	varargout  存放可变数量输出参数的单元数组

round( )  四舍五入函数

逻辑字符：
~：逻辑非（NOT）

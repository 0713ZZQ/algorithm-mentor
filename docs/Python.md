Ctrl+shift+P 构建环境
‘’‘ ’‘’ 注释一大段文字                                                                                                                                   

各类库：
`numpy` 用于数组计算、矩阵计算和数值仿真  np
`matplotlib.pyplot` 画图用的库
`csv` 用于保存指标到 CSV 文件
`math` 用于三角函数、弧度转换等
`dataclass` 用来快速定义只存数据的类
`Path` 用于处理文件路径
`Callable` 表示某个变量是函数


数据类型：
np.ndarray 多维数组  用于存储和处理同类型元素（通常是数字）的高效多维网格

函数：
==np.array==  # 通过 np.array() 函数创建 ndarray 对象
	arr = np.array([[1, 2, 3], [4, 5, 6]])
==np.zeros_like== # 创建一个与已有数组形状shape、数据类型dtype均相同的新数组，并且将所有元素都初始化为 0
	filtered = np.zeros_like(signal, dtype=float) 创建和signal	同长度的输出数组
	np.zeros(shape)	指定形状创建全 0 数组
	np.ones_like(a)	按已有数组创建全 1 数组
	np.empty_like(a)	按已有数组创建未初始化数组
	np.full_like(a, v)	按已有数组创建全为 v 的数组
==for== i ==in== range(1, len(signal)): 
让变量 `i` 从 1 开始，一直遍历到 `len(signal)-1`
==range==(1, len(signal)) 生成一串数字，从 1 开始，到 `len(signal)-1` 结束
==len==(signal)  获取 `signal` 中元素的个数（长度）


关键字：
==def==  normalize_angle (angle:  float  | np.ndarray)  ->   float | np.ndarray:
 return (angle + np.pi) % (2.0 * np.pi) - np.pi
 含义：(angle + π) % (2π) - π，把任意角度归一化到区间[−π, π)
 定义   函数名（参数：参数类型 | 另一种类型）-> 返回值类型
其中 float  | np.ndarray 等价于Union[float, np.ndarray]


运算符
==%==：**取模（modulo）运算符**，返回**除法的余数**
	a % b 的结果与 `b` 同号
	-1 % 6  结果是 5   7%-3 结果是 -2 
==//==：**整除（floor division）**，把结果的小数部分去掉，向下取整
	7 // -3  结果是-3
	a == (a // b) * b + (a % b)


特殊字符：
|：或者
-> ：返回值注解

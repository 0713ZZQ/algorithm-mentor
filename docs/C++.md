输入输出：
#include<bits/stdc++.h>
using namespace std;
int main(){    printf("Hello Nowcoder!\n");
    return 0;}

    cout<<"Hello Nowcoder!";
计算奇数个数：if(x %2!=0){ oddcount++;}
求最小的奇数： minodd = min(minodd,x);


cin>>s ;  //读取第一个单词，不包括空格
cin.ignore() ； //忽略（丢弃）输入缓冲区中的字符，比如回车'\n'
getline( cin , s );  : 读取整行，包括空格
fixed  按普通小数形式输出  
setprecision(n) 总共保留 n 位有效数字  //  #include iomanip
	cout << fixed << setprecision(3) << n << endl;  
	//配合 `fixed` 使用时表示保留小数点后 3 位
setw(n) 输出宽度至少 n 个字符 ;  setfill('0')  如果不足，就用 0 填充
	cout << setw(9) << setfill('0') << 123;  输出结果：000000123
cout<<s ; //默认只输出 **6 位有效数字**
pow( r , 2 )  //r x r


运算符：
ll ：逻辑或OR   && ：逻辑与AND     ！：逻辑非NOT    != : 不等于
~ ：按位取反，执行NOT运算    | ：按位执行OR运算   & ：按位执行AND运算
^ ：按位执行异或XOR运算（只有一个操作数未true，该运算结果才为true）
& ：获取指针指向的内存所储存的值 & nums
i++ ，int x= i++: 后置自增  先把i值赋值给x，后i自增1
++i ：i先增，后赋值

return a+b; 返回 a+b 的值，退出当前函数模块
break：结束，退出当前循环
while（条件表达式）{  }
for(int i=0;i<n;++i){  }
for (int x : a)  把容器 `a` 里面的元素**一个一个取出来**，每次放到变量 `x` 里 
if()  {}  else if()  {}   
if(){}   else{}
switch-case   
	switch(expression){
    case Lable A:
        xx;     break;
    case Lable B:  xx;  break; 
    default:  xx;  break;}//计算expression的值并与Lable A 等比较,和其它不同时执行default 底下的

变量类型：
整型
	int （16位）取值范围：-32768~32767   2^16=65536  2字节
		short int  |  short
	int （32位）取值范围：-2147483648~2147483647   2^32=4294967296  4字节
	long  int  |  long  4字节或者8字节
	long  long   取值范围：-2^63~2^63 -1  8字节
		long long x;   long long int x;  long long int x = 0;
浮点数
	float   取值范围：1.2e-38 ~ 3.4e38
	双精度 double   取值范围：2.2 e-308 ~ 3.4 e308
字符
	char    取值范围：256个字符值
		strlen() - 求长度    strcpy() - 复制字符串   
		strcmp() - 比较字符串  strcat() - 连接字符串
	string
		s.find()   s.substr()   s.size()  string::npos
无符号:
	unsigned int （16位）取值范围：0~2^16 -1
	unsigned int （32位）取值范围：0~2^32-1 




**==STL（Standard Template Library标准模板库）==** 
**STL  容器 container**
==vector== 动态数组 - 存一组数据，类似可变长度数组 	#include <vector>
	初始化
		vector<int> a = {3, 1, 2};  //初始化整型向量a
		vector<int> candy(n, 1)； // n 个元素全部被初始化为 1
		等价于  vector<int> candy;     candy.assign(n, 1);    // 赋值为 n 个 1
	插入元素
		a.push_back(10); // 在a数组的末尾插入元素10
		a.insert(a.begin() + i, x); // 在a数组的第i个位置插入元素 x
		a.insert(a.end(), 2 , 45); //在a数组的末尾添加2个元素，值为45
	a.pop_back(); // 删除a数组的末尾元素
	a.back(); // 获取a数组的末位元素，不删除
	a.size();  // 获取a数组的元素个数
	vector<vector<int>>表示二维数组

string 字符串类 - 处理文本、字符序列 	#include <string>
	string s; 	cin>>s; 	cout << s.size() << endl;
	string t = s.substr(1, 3); // 从字符串 s的下标1开始，截取3个字符放到字符串 t 里
	s += 'x'; // 往字符串 s 后面加一个字符 'x'
	s += "hello"; // 往字符串 s 后面加一个字符串 "hello"
	int pos =s.find('.');  //在字符串里从左至右找 .  pos代表第一次出现 . 的位置（从 0 开始计数）
    while（pos！= string::npos) {    cout << "找到 '.' 在位置: " << pos << endl;
    pos = s.find('.', pos + 1); }//  从下一个位置继续找，查找所有 . 的位置

sort  //排序函数 - 给数组、vector 排序 
	升序：sort(a.begin(), a.end());  // 把a中[begin(), end())范围内的元素从小到大排序
		包含 begin() 指向的元素，不包含 end() 指向的位置
	降序：sort(a.begin(), a.end(), greater<int>());
	部分元素排序：sort(a.begin() + 1, a.begin() + 4);
	排序后去重：
		sort(a.begin(), a.end());
		a.erase(unique(a.begin(), a.end()), a.end()); //删除a中*连续重复*的元素
			unique（） 把不重复的元素移动到前面，返回位置：指向第一个无效元素 
			erase（）删除从unique()返回的位置到最后的所有元素
		
unordered_map  // 哈希表 - 快速做“键 -> 值”映射
	unordered_map<int, int> cnt;
	for (int x : a) {
	cnt[x]++;}
	for (auto [num, c] : cnt) {
	cout << num << " " << c << endl; }
	判断是否存在：
		if (cnt.count(x)) {    cout << "出现过" << endl;  }
	字符串计数：
		unordered_map<char, int> cnt;
		for (char c : s) {    cnt[c]++; }
	
set<int> s; - 有序集合 - 自动排序、去重
lower_bound | 二分查找函数 | 在有序数组里找第一个大于等于 x 的位置
	set<int> st; 	st.insert(3);  	st.insert(1);  	st.insert(3);
	for (int x : st) {  cout << x << " "; }
	判断是否存在：if (st.count(x)) { cout << "存在" << endl; }
	找第一个大于等于x 的数：
		auto it = st.lower_bound(x);
		if (it != st.end()) { cout << *it << endl; }
	在有序vector里使用 lower_bound：
		sort(a.begin(), a.end());
		auto it = lower_bound(a.begin(), a.end(), x);
		int pos = it - a.begin();
	
queue<int> q; // 队列 | 先进先出
	入队1 2 3 ，出队 1 2 3
		push(x)：将整数 xx 入栈；  
		pop()：若栈非空，则删除栈顶元素；否则输出 EmptyEmpty；  
		query()：若栈非空，则输出栈顶元素；否则输出 EmptyEmpty；  
		size()：输出栈中元素的数量。
priority_queue | 优先队列/堆 | 快速取最大值或最小值 
	默认大根堆，最大值在顶部，越大越优先：	
		priority_queue<int> pq;
		pq.push(3); //加入元素3	  pq.push(10);	//加入10 	pq.push(5); //5
		cout << pq.top () << endl;  
		// pq.top() 查看qp队列中优先级最高的元素
		pq.pop();  //删除qp队列的顶部元素
		if( pq.empty() )； //判断qp队列是否为空，返回 true 和 false
	小根堆，最小的元素优先出来，越小越优先：
		priority_queue<int, vector<int>, greater<int>> pq;
		数据类型 int ; 底层容器 vector ;比较方式greater
deque<int> dq;  // 双端队列
	
pair<int, int> p;  第一个元素p.first，第二个p.second
	pair<string,int>；pair<char,double>
	
	vector<pair<int,int>> activity;
	    activity[0].first；   activity[0].second； 
	sort(a.begin(), a.end(), [](pair<int, int> x, pair<int, int> y) {
	if (x.second != y.second) return x.second > y.second;    return x.first 小于 y.first;
 
stack  容器适配器 | 后进先出 | 只能访问栈顶
	stack<int> st;stack<int> st;      
	st.push(10); st.push(20);  st.push(30);
	cout << st.top() << endl;   //30 输出栈顶
	st.pop();   // 删除栈顶  	cout << st.top() << endl;   //20  
	cout << st.size() << endl;  //2     栈含有的元素
	cout << st.empty() << endl; //  0 (false)   //栈是否为空栈

lambda - 匿名函数语法 | 临时写一个比较函数或小函数、给 sort、优先队列写自定义规则
	
	
map<string, int> mp;  // 键值对，每一个 Key 都对应一个 Value
	map<键的类型, 值的类型> 名字;
		mp["Tom"] = 95;  //Tom是键；95是值   下标是字符串、整数等很多类型
		cout<< mp["Tom"] <<endl;   输出的值为95
	统计每个数字出现次数：map<int,int> cnt;
		map<int,int> cnt;   for(int i=0; i<5; ++i) {int x;  cin>>x; cnt[x]++;}
		cnt[x] 键为 x 的
	统计每个单词出现次数：
		map<string,int> cnt;  string s;  while(cin >> s) { cnt[s]++; }
		cnt [s] 键为 “s” 的那一项
	学生成绩：map<string,int> score;




**STL 算法 algorithm**
find();  //在字符串里查找特定值
reverse ( a.begin(), a.end() );  //把字符串a中各元素的顺序反转
remove() :  //移动指定元素到末尾 | 常与 erase() 配合，删除满足条件的元素
	和 unique() 一样负责整理数据并返回新结尾
	s.erase( remove( s.begin(), s.end(), ' ') , s.end() ); 
		把字符串s中的空格挪到末尾，返回新排序后空格起始的位置，要删除的起始点
	remove( s.begin(), s.end(), 0); 		//把字符串s中的0元素挪到末尾 
max_element()、min_element() —— 求最大/最小元素
transform() // 转换字母大小写
	transform(a.begin() ,  a.end() ,  a.begin() , ::toupper)  小写转大写
	transform(a.begin() ,  a.end() ,  a.begin() , ::tolower)  大写转小写
	大小写互换：
 
 
STL 迭代器
- begin() 指向第一个元素
- end() 指向最后一个元素后面的位置


sizeof(array) == get_size_1(array) ? 1 : 0






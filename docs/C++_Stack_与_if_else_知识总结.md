# C++ 栈（stack）与 if/else 易错点总结

## 一、if / else if 易错点

### 1. 一个变量有多个可能值时，使用 `else if`

``` cpp
if(op=="push"){
    ...
}
else if(op=="pop"){
    ...
}
else if(op=="query"){
    ...
}
else if(op=="size"){
    ...
}
```

不要写成多个独立的 `if`，否则会导致一次输入执行多个判断。

------------------------------------------------------------------------

### 2. `else` 永远匹配最近的 `if`

``` cpp
if(a){
    if(b){
        ...
    }else{
        ...
    }
}
```

建议所有 `if` 都加 `{}`。

------------------------------------------------------------------------

### 3. 一个 `if-else` 链只能有一个最终 `else`

错误：

``` cpp
if(...){}
else{}
else if(...){} // 错误
```

正确：

``` cpp
if(...){}
else if(...){}
else{}
```

------------------------------------------------------------------------

### 4. 能用 `else if` 就不要写多个 `if`

例如成绩分类：

``` cpp
if(score>=90){}
else if(score>=80){}
else if(score>=60){}
else{}
```

------------------------------------------------------------------------

### 5. 判断布尔值推荐写法

不推荐：

``` cpp
if(st.empty()==0)
```

推荐：

``` cpp
if(!st.empty())
```

------------------------------------------------------------------------

## 二、stack 基础

### 定义

``` cpp
#include <stack>
stack<int> st;
```

栈遵循 **LIFO（后进先出）**。

### 常用操作

  操作       函数        时间复杂度
  ---------- ----------- ------------
  入栈       `push(x)`   O(1)
  出栈       `pop()`     O(1)
  查看栈顶   `top()`     O(1)
  判空       `empty()`   O(1)
  元素数量   `size()`    O(1)

------------------------------------------------------------------------

## 三、栈万能模板

### 入栈

``` cpp
st.push(x);
```

### 出栈

``` cpp
if(!st.empty()){
    st.pop();
}else{
    cout<<"Empty\n";
}
```

### 查看栈顶

``` cpp
if(!st.empty()){
    cout<<st.top()<<'\n';
}else{
    cout<<"Empty\n";
}
```

### 判断是否为空

``` cpp
if(st.empty()){
    cout<<"空";
}
```

### 获取元素个数

``` cpp
cout<<st.size();
```

------------------------------------------------------------------------

## 四、竞赛模板

``` cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    stack<int> st;
    int n;
    cin>>n;

    while(n--){
        string op;
        cin>>op;

        if(op=="push"){
            int x;
            cin>>x;
            st.push(x);
        }
        else if(op=="pop"){
            if(st.empty()) cout<<"Empty\n";
            else st.pop();
        }
        else if(op=="query"){
            if(st.empty()) cout<<"Empty\n";
            else cout<<st.top()<<'\n';
        }
        else if(op=="size"){
            cout<<st.size()<<'\n';
        }
    }
}
```

------------------------------------------------------------------------

## 五、输入输出优化

``` cpp
ios::sync_with_stdio(false);
cin.tie(nullptr);
```

### `ios::sync_with_stdio(false)`

-   关闭 C 与 C++ 输入输出同步
-   提高 `cin/cout` 速度
-   不建议再混用 `scanf/printf`

### `cin.tie(nullptr)`

-   取消 `cin` 与 `cout` 绑定
-   输入前不再自动刷新输出
-   进一步提高速度

------------------------------------------------------------------------

## 六、刷题常见栈题

1.  栈基本操作（push / pop / top / size）
2.  括号匹配
3.  表达式求值
4.  单调栈
5.  DFS（递归栈）

------------------------------------------------------------------------

## 七、总结

### if / else 口诀

-   一个变量多种情况 → `else if`
-   `else` 只属于最近的 `if`
-   一个 `if-else` 链只有一个最终 `else`
-   建议所有 `if` 都加 `{}`

### stack 口诀

-   入栈：`push`
-   出栈：`pop`
-   看栈顶：`top`
-   判空：`empty`
-   数量：`size`
-   使用 `top()` 前先判断 `empty()`

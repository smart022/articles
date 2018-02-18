# Frequent used STL&String func

## c

```c
memset(addr,0,n)
```



## string

```c++
std::stoi(str) // string2int ==   atoi( str.c_str())

// stol| stof| stod -- long, float, double
```



## deque

双端队列，随机访存，头尾快速插删

deque<int> cot

cot.at()

cot.front()|back()// 取头尾

cot.begin()|end()| rbegin()| end()// 指针

Cot.push_back()| push_front()

cot.insert(pos,elem)| (pos,n,elem)| (pos,beg,end)

cot.pop_back()| pop_front()

cot.erase(pos)| (beg,end)

cot.size()| empty()| max_size()| resize()
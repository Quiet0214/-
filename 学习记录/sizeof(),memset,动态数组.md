# C++

- sizeof(int)=4   sizeof是取字节的函数。

- ```c++
  int *a= new int[3]();
  ```

  动态数组，创建一个三个int型每个值为0的动态数组。

- memset()无法初始化动态数组。

栗子：

```c++
void foo(int n) {
int *p;
p = new int[n];
memset(p, -1, sizeof(p));//编译器无法得知n的大小，会将其推导为指针大小，所以memset只set了一个指针大小
}
```

正确的初始化：

```C++
void foo(int n) {
int *p;
p = new int[n];
memset(p, -1, n * sizeof(int))//正确的initialization

int dp[n];
memset(dp, -1, sizeof(dp))
}
```


## C/Cpp的一些基础



### int

- int 对float做强行转换时，只做向下取整，例如：

  ```c
  float x = 18.4
  float y = 4.9
  printf("%d", (int)x)
  printf("%d", (int)y)
  ### x = 18
  ### y = 4
  ```

  

### 求余取整

- % 为求余

  ```c
  289%10 = 9
  289%100 = 89			
  ```

  

- / 为取整

  ```c
  289/10 = 28
  289/100 = 2
      
     
  ```

### %的使用

- 每两个为一组

  ```c
  int x = 20;
  printf("%d%%", x);  20%
  printf("%d%%%%", x); 20%%
  printf("%d%%%%%%", x); 20%%%
  ```

- 若为奇数个则向上取整，1个%为0, 3个为一个%以此类推

### 求字符串的长度

- sizeof()

  ```c
  char str[20];
  strLen = sizeof(str)/sizeof(str[0]);
  ```

  

- strlen()

  ```c
  char str[20];
  strLen = strlen(str);
  ```

- **注意**

  - strlen()函数求出的字符串长度为有效长度，既不包含字符串末尾结束符 ‘\0
  - sizeof()操作符求出的长度包含字符串末尾的结束符 ‘\0’；


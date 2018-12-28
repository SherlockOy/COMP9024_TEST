# COMP9024_TEST
说明：
此git仓库主要是存放测试相关的case文件，主要采用的是c语言的check测试框架
check测试框架的官方地址为：https://libcheck.github.io/check/

Mac操作系统的check安装命令：brew install check

其他的操作系统安装，如果官方网站没有的，就只能自求多福了。

针对assignment1的测试，将listIteratorInt.c文件到assignment1里面

运行：make test
运行：./murui_test.out 即可出现测试结果

```
Running suite(s): COMP9024 Assignment 1
100%: Checks: 6, Failures: 0, Errors: 0
testListIteratorInt.c:45:P:test_cases:test_add:0: Passed
testListIteratorInt.c:90:P:test_cases:test_iterator_init_null:0: Passed
testListIteratorInt.c:379:P:test_cases:test_teacher_given_cases:0: Passed
testListIteratorInt.c:428:P:test_cases:test_next_case:0: Passed
testListIteratorInt.c:471:P:test_cases:test_find_next_case:0: Passed
testListIteratorInt.c:509:P:test_cases:test_find_previous_case:0: Passed
```
解释如下：

1.Checks    表示的是进行了6大项的check

2.Failures  表示测试失败。

3.Errors    表示测试出现了异常

4.Passed    表示当前的测试case全部通过

常见错误说明：
1.Segmentation fault
```
testListIteratorInt.c:15:E:test_cases:test_add:0: (after this point) Received signal 11 (Segmentation fault: 11)
```

出现Segmentation fault 绝对是C语言开发的噩梦，一般是指对一个无效的地址进行赋值，比如：
```
Node *new_node = NULL;
new_node->data = (int *) malloc(sizeof(int));
```
对数组的操作也特别容易出现Segmentation fault，比如数组越界：
```
int a[2] = {1,2};
int i=-1;
printf("%d",a[i++]);
```
上面的i++实际上是-1，此时越界，导致出现Segmentation fault






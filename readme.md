遇见ModuleNotFoundError: No module named 'urllib3.packages.six.moves'错误需要降低python版本(如3.8版本)。

## lab01

python中函数返回值会打印出来

## lab02

可以看到每次执行multiply_by的时候会创造一个在内存中的函数对象

```python
>>> def multiply_by(m):
...     def multiply(n):
...         return n * m
...     return multiply
... 
>>> multiply_by(2)
<function multiply_by.<locals>.multiply at 0x7e2ae81081f0>
>>> multiply_by(2)
<function multiply_by.<locals>.multiply at 0x7e2ae8108280>
>>> multiply_by(2)
<function multiply_by.<locals>.multiply at 0x7e2ae81081f0>
>>> multiply_by(2)
<function multiply_by.<locals>.multiply at 0x7e2ae8108280>
>>> a=multiply_by(2)
>>> a
<function multiply_by.<locals>.multiply at 0x7e2ae81081f0>
>>> b=multiply_by(2)
>>> b
<function multiply_by.<locals>.multiply at 0x7e2ae8108280>
>>> c=multiply_by(2)
>>> c
<function multiply_by.<locals>.multiply at 0x7e2ae8108310>
```

lambda函数与def的函数区别是在系统中没有函数名字绑定

```python
>>> def c():
...     return 1
... 
>>> c
<function c at 0x7e2ae81083a0>
>>> lambda : 1
<function <lambda> at 0x7e2ae8108280>
>>> a=lambda : 1
>>> a
<function <lambda> at 0x7e2ae8108310>
>>> b=a
>>> b
<function <lambda> at 0x7e2ae8108310>
>>> b=c
>>> b
<function c at 0x7e2ae81083a0>
```

True and 10返回的是10，第二个算术的值，而不是and最后结果(为啥？？)

print返回None，无返回值

若返回值是"xxx",则打印'xxx'。print("xxx")则打印xxx

## hog

def make_test_dice(*outcomes):的*outcomes表示可以接收不定数量参数元素，会收集到元组outcomes中

注意PROBLEM 8的original_function参数形式不确定，不一定是示例中的roll_dice，它目的是确定多次调用一个加分函数所加的分平均值，而加分函数根据策略有不同的参数

PROBLEM 12 需要考虑运行时间，所以不能算太多

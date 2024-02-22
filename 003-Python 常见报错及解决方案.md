## `SyntaxError: invalid syntax`

- 原因：代码中可能存在**语法错误**，如括号**未闭合**、**缩进**错误等。
- 示例：
	```python
	print('Hello World'     # <== 括号未闭合
	
	if True                 # <== 缺少冒号
	    print("Test"):      # <== 多余冒号
		time.sleep(1)       # <== 缩进错误 (此处缩进为 Tab，即'\t'，但前文是4个空格)
	```

## `NameError: name 'xxx' is not defined`

- 原因：代码中使用了**未定义**的变量、函数等。
- 示例：
	```python
	print(a)    # <== 变量 a 未定义
	func()      # <== 函数 func 未定义
	c = D()     # <== 类 D 未定义
	```

## `TypeError: can only concatenate xxx (not "xxx") to xxx`

- 原因：代码中使用了**不支持**的操作，如将 `str` 和 `int` 相加
- 示例：
	```python
	'1' + 1     # <== 将字符串和整数相加
	[] + 1      # <== 将列表和整数相加
	```

## `IndexError: list index out of range`

- 原因：代码中使用了**超出范围**的索引
- 示例：
	```python
	l = [1, 2, 3]
	l[3]        # <== 超出索引范围
	```

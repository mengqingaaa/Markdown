# `argparse` module

`argparse` 模块使得编写用户友好的命令行接口非常容易。
程序只需要定义好它要求的参数，然后 `argparse` 将负责如何从 `sys.argv` 中解析出这些函数。
`argparse` 模块还会自动生成帮助和使用信息并且当用户赋给程序非法参数时产生错误信息。

### `ArgumentParser` 对象

使用 `argparse` 的第一步就是创建一个 `ArgumentParser` 对象。
`ArgumentParser` 对象会保存把命令行解析成Python数据类型所需要的所有信息。
```Python
parser = argparse.ArgumentParser(description = 'XXXX')
````

#### `add_argument()` 方法
`ArgumentParser` 对象通过调用其方法 `add_argument()` 添加脚本的参数信息到自身。
这些信息告诉 `ArgumentParser` 对象如何接收命令行上的字符串并将它们转换成对象。
这些信息将在调用方法 `parse_args()` 时用到。

#### `parse_args()` 方法
`ArgumentParser` 对象通过 `parse_args()` 方法解析参数。
它将检查命令行，把每个参数转换成恰当的类型并采取恰当的动作。
在大部分情况下，这意味着将从命令行中解析出来的属性建立一个简单的 `Namespace` 对象。

`Namespace` 对象的属性的名字有 `add_argument()` 方法的 `dest` 关键字参数指定。
* 对于位置参数(positional arguments)，提供给 `add_argument()` 方法的第一个参数将作为 `dest` 值；
* 对象可选参数（选项，optional arguments），`AgumentParser` 对象生成的 `dest` 的值通常从选项字符串中推到出来。
    * 如果提供了长选项字符串，`dest` 的值是将第一个长的选项字符串前面的 `--` 去掉剩下的字符串；
    * 如果没有提供长选项字符串，`dest` 的值则是第一个短选项字符串前面的 `-` 去掉后剩下的字符串。
    * 任何选项字符串内部的 `-` 字符讲被转换为 `_` 字符以确保字符串是合法的属性名字。

------------------

# `sys.argv`
The list of command line arguments passed to a Python script.
`argv[0]` is the script name

---

# References

[argparse Library reference](https://docs.python.org/3/library/argparse.html#the-add-argument-method)

[实验楼案例](https://www.shiyanlou.com/courses/580/labs/1934/document)

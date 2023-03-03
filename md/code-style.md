# 代码规范

常见代码风格有 LLVM、Google、Chromium、Mozilla、WebKit 等

本项目中使用 [Google Style Guide](https://github.com/zh-google-styleguide/zh-google-styleguide)

现对其中常使用的代码规范进行一定说明：

## 包
1. 使用 `import x` 来导入包和模块.
2. 使用 `from x import y` , 其中 x 是包前缀, y 是不带前缀的模块名.
3. 使用 `from x import y as z`, 如果两个要导入的模块都叫做 y 或者 y 太长了.
4. 仅当缩写 `z` 是通用缩写时才可使用 `import y as z`.(比如 `np` 代表 `numpy`.)
5. 每个导入独占一行
6. 导入按字典序排列

## True/False 的求值

尽可能使用隐式布尔值，例如 0，None，[]，{}。使用 `if foo:` 而不是 `if foo != []:`

## 代码类型注释

根据 [PEP-484](https://www.python.org/dev/peps/pep-0484/) 来对 python3 代码进行注释

例如：`def func(a: int) -> List[int]:`

## 缩进

用 4 个空格来缩进代码，绝对不要用 tab, 也不要 tab 和空格混用

## 空行

顶级定义之间空两行, 比如函数或者类定义. 

方法定义, 类定义与第一个方法之间, 都应该空一行. 函数或方法中, 某些地方要是你觉得合适, 就空一行.

## 空格

括号内不要用空格。不要在逗号, 分号, 冒号前面加空格, 但应该在它们后面加 (除了在行尾).例如：`print(x, y)`

按照标准的排版规范来使用标点两边的空格。例如：`spam(ham[1], {eggs: 2}, [])`

在二元操作符两边都加上一个空格, 比如赋值 (=), 比较 (\==, <, >, !=, <>, <=, >=, in, not in, is, is not), 布尔 (and, or, not). 至于算术操作符两边的空格该如何使用, 需要你自己好好判断. 不过两侧务必要保持一致.

## 类

如果一个类不继承自其它类, 就显式的从 object 继承

例如：

```python
class SampleClass(object):
        pass

class OuterClass(object):
    class InnerClass(object):
        pass
```

## 命名

模块名写法: `module_name` ; 包名写法: `package_name` ; 类名: `ClassName` ; 方法名: `method_name` ; 异常名: `ExceptionName` ; 函数名: `function_name` ; 全局常量名: `GLOBAL_CONSTANT_NAME` ; 全局变量名: `global_var_name` ; 实例名: `instance_var_name` ; 函数参数名: `function_parameter_name` ; 局部变量名: `local_var_name` . 函数名,变量名和文件名应该是描述性的,尽量避免缩写,特别要避免使用非项目人员不清楚难以理解的缩写,不要通过删除单词中的字母来进行缩写. 始终使用 `.py` 作为文件后缀名,不要用破折号.

用单下划线 (\_) 开头表示模块变量或函数是 protected 的 (使用 from module import \* 时不会包含).用双下划线 (\_\_) 开头的实例变量或方法表示类内私有.

## MAIN 函数

每一个文件都应该有一个 `main` 函数，表示脚本可导入

例如：

```python
def main():
    ...

if __name__ == '__main__':
    main()
```

## 行长度

每行尽量不超过 80 个字符，若一行内无法放下使用圆括号连接起来

例如：

```python
foo_bar(self, width, height, color='black', design=None, x='foo',
             emphasis=None, highlight=0)
```

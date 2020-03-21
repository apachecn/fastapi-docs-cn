**Python 3.6+**支持可选的“类型提示”。

这些**“类型提示”**是一种新语法（自Python 3.6+起），允许声明变量的类型（例如：str，int，float，bool）。

通过声明变量的类型，编辑器和工具可以为你提供更好的支持。

这只是关于Python类型提示的**快速教程/复习**。 它仅涵盖将它们与**FastAPI**一起使用所需的最低要求……实际上很少。

**FastAPI**都是基于这些类型提示的，它们具有许多优点和好处。

但是，即使你从未使用过**FastAPI**，也可以从中学习到一些好处。

> 注意：
> 如果你是Python专家，并且已经了解有关类型提示的所有知识，请跳到下一章。

## 动手做

让我们从一个简单的例子开始（源码在`./src/python_types/tutorial001.py`）：

```Python
def get_full_name(first_name, last_name):
    full_name = first_name.title() + " " + last_name.title()
    return full_name


print(get_full_name("john", "doe"))
```

调用该程序输出：

```
John Doe
```

该函数执行以下操作：

* 获取一个`first_name`和一个`last_name`.
* 使用`title()`将每个字母的首字母转换为大写。
* 在它们中间用一个空格连接（将它们放在一起，作为一个整体。 一个内容接另一个。）。

```Python hl_lines="2"
def get_full_name(first_name, last_name):
    full_name = first_name.title() + " " + last_name.title()
    return full_name


print(get_full_name("john", "doe"))
```

### 编辑它

这是一个非常简单的程序。

但是现在想象一下，你是从头开始编写的。

在某个时候，你将开始定义函数，已经准备好参数...

但是然后你必须调用“将第一个字母转换为大写字母的方法”。

是`上(upper)`吗？ 是`大写(uppercase)`吗？ `首字母大写(first_uppercase)`？ `大写(capitalize)`？

然后，你尝试与老程序员的朋友：编辑器自动补全。

键入函数的第一个参数`first_name`，然后输入点（`。`），然后按`Ctrl+Space`以触发补全。

但是，可悲的是，你没有得到任何有用的信息（然并卵）：

<img src="/img/python-types/image01.png">

### 添加类型

让我们从以前的版本中修改一行。

我们将从以下位置精确更改此片段（函数的参数）：

```Python
    first_name, last_name
```

改为：

```Python
    first_name: str, last_name: str
```

就这样。

这些是“类型提示”（源码在`./src/python_types/tutorial002.py`）：

```Python hl_lines="1"
def get_full_name(first_name: str, last_name: str):
    full_name = first_name.title() + " " + last_name.title()
    return full_name


print(get_full_name("john", "doe"))
```

这与声明默认值不同，例如：

```Python
    first_name="john", last_name="doe"
```

这是另一回事。

我们使用冒号（`:`），而不是等于号（`=`）。

添加类型提示通常不会改变没有它们的情况。

但是现在，假设你再次处于创建该函数的过程中，但是带有类型提示。

同时，你尝试使用`Ctrl+Space`触发自动补全，您会看到：

<img src="/img/python-types/image02.png">

这样，你可以滚动查看选项，直到找到“rings a bell”的选项：

<img src="/img/python-types/image03.png">

## 更多的动手操作

检查此函数，它已经具有类型提示（源码在`./src/python_types/tutorial003.py`）：

```Python hl_lines="1"
def get_name_with_age(name: str, age: int):
    name_with_age = name + " is this old: " + age
    return name_with_age
```

因为编辑器知道变量的类型，所以你不仅可以完成补全操作，还可以进行错误检查：

<img src="/img/python-types/image04.png">

现在你知道必须修复它，将`age`转换为带有`str(age)`的字符串（源码在`./src/python_types/tutorial004.py`）：

```Python hl_lines="2"
def get_name_with_age(name: str, age: int):
    name_with_age = name + " is this old: " + str(age)
    return name_with_age
```

## 声明类型

你刚刚看到了声明类型提示的主要地方。作为函数参数。

这也是将它们与**FastAPI**一起使用的主要位置。

### 简单类型

你可以声明所有标准的Python类型，不仅限于`str`。

你可以使用，例如：

* `int`
* `float`
* `bool`
* `bytes`

（源码在`./src/python_types/tutorial005.py`）：
```Python hl_lines="1"
def get_items(item_a: str, item_b: int, item_c: float, item_d: bool, item_e: bytes):
    return item_a, item_b, item_c, item_d, item_d, item_e
```

### 带有子类型的类型

有些数据结构可以包含其他值，例如`dict`，`list`，`set`和`tuple`。 内部的值也可以具有自己的类型。

要声明这些类型和子类型，可以使用标准的Python模块`typing`。

它专门存在以支持这些类型提示。

#### 列表

例如，让我们将变量定义为`字符串(str)`的`列表(list)`。

从`typing`里，导入`List`（大写字母`L`）（源码在`./src/python_types/tutorial006.py`）：

```Python hl_lines="1"
from typing import List


def process_items(items: List[str]):
    for item in items:
        print(item)
```

用相同的冒号（`:`）语法声明变量。

作为类型，输入`List`。

由于列表是带有“子类型”的类型，因此请将子类型放在方括号中（源码在`./src/python_types/tutorial006.py`）：

```Python hl_lines="4"
from typing import List


def process_items(items: List[str]):
    for item in items:
        print(item)
```

那意味着：“变量`items`是一个`列表list`，在这个列表中的每一项是一个`字符串str`”。

这样，即使在处理列表中每项时，你的编辑器也可以提供支持。

没有类型，几乎是不可能实现的：

<img src="/img/python-types/image05.png">

注意，变量`item`是列表`items`中的元素之一。

而且，编辑器仍然知道它是一个`str`，并为此提供了支持。

#### 元组和集合

声明`元组tuple`和`集合set`的方法相同（源码在`./src/python_types/tutorial007.py`）：

```Python hl_lines="1 4"
from typing import Set, Tuple


def process_items(items_t: Tuple[int], items_s: Set[bytes]):
    return items_t, items_s
```

这意味着：

* 变量`items_t`是一个`元组tuple`，它的每一项是一个`整型int`.
* 变量`items_s`是一个`集合set`，它的每一项是`字节bytes`类型.

#### 字典

要定义`字典dict`，你可以传递2个子类型，以逗号分隔。

第一个子类型用于`字典dict`的键。

第二个子类型用于`字典dict`的值（源码在`./src/python_types/tutorial008.py`）：

```Python hl_lines="1 4"
from typing import Dict


def process_items(prices: Dict[str, float]):
    for item_name, item_price in prices.items():
        print(item_name)
        print(item_price)
```

这意味着：

* 变量`prices`是一个`字典dict`:
    * 这个`字典dict`的键是`字符串str`类型（假设每项的名称）。
    * 这个`字典dict`的值是`浮点数float`类型（假设每项的价格）。

### 类作为类型

你也可以将类声明为变量的类型。

假设你有一个名为`Person`的类，其名称为（源码在`./src/python_types/tutorial009.py`）：

```Python hl_lines="1 2 3"
class Person:
    def __init__(self, name: str):
        self.name = name


def get_person_name(one_person: Person):
    return one_person.name
```

然后，你可以将变量声明为`Person`类型（源码在`./src/python_types/tutorial009.py`）：

```Python hl_lines="6"
class Person:
    def __init__(self, name: str):
        self.name = name


def get_person_name(one_person: Person):
    return one_person.name
```

然后，再次获得所有编辑器支持：

<img src="/img/python-types/image06.png">

## Pydantic模型

<a href="https://pydantic-docs.helpmanual.io/" class="external-link" target="_blank">Pydantic</a>是用于执行数据验证的Python库。

你将数据的“形状shape”声明为具有属性的类。

每个属性都有一个类型。

然后，创建带有某些值的该类的实例，它将验证这些值，将它们转换为适当的类型（如果是这种情况），并为你提供一个包含所有数据的对象。

然后，你将得到该对象的所有编辑器支持。

取自Pydantic官方文档（源码在`./src/python_types/tutorial010.py`）：

```Python
from datetime import datetime
from typing import List

from pydantic import BaseModel


class User(BaseModel):
    id: int
    name = "John Doe"
    signup_ts: datetime = None
    friends: List[int] = []


external_data = {
    "id": "123",
    "signup_ts": "2017-06-01 12:22",
    "friends": [1, "2", b"3"],
}
user = User(**external_data)
print(user)
# > User id=123 name='John Doe' signup_ts=datetime.datetime(2017, 6, 1, 12, 22) friends=[1, 2, 3]
print(user.id)
# > 123
```

> 信息：
> 要了解有关<a href="https://pydantic-docs.helpmanual.io/" class="external-link" target="_blank">Pydantic的更多信息，请检查其文档</a>。

**FastAPI**全部基于Pydantic。

在[教程-用户指南](tutorial/README.md)中，你会在实践中看到更多的相关信息。

## **FastAPI**中的类型提示

**FastAPI**利用这些类型提示来做几件事。

使用**FastAPI**，您可以使用类型提示来声明参数，并得到：

* **编辑器支持**。
* **类型检查**。

...**FastAPI**使用相同的声明来：

* **定义请求**：来自请求路径参数，查询参数，标头，正文，依赖项等。
* **转换数据**：从请求到所需的类型。
* **验证数据**：来自每个请求：
    * 当数据无效时，生成**自动错误**返回给客户端。
* **文档** 使用OpenAPI记录API：
    * 然后由自动交互式文档用户界面使用。

这听起来可能很抽象。 不用担心 你会在[教程-用户指南](tutorial/README.md)中看到所有这些操作。

重要的是，通过使用标准的Python类型，在一个地方（而不是添加更多的类，装饰器等），**FastAPI**将为你完成很多工作。

> 信息：
> 如果您已经遍历了所有教程并回来查看有关类型的更多信息，那么一个很好的资源是<a href="https://mypy.readthedocs.io/en/latest/cheat_sheet_py3.html" class="external-link" target="_blank">来自`mypy`的“备忘单”</a>。

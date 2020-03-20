<p align="center">
  <a href="https://fastapi.tiangolo.com"><img src="https://fastapi.tiangolo.com/img/logo-margin/logo-teal.png" alt="FastAPI"></a>
</p>
<p align="center">
    <em>FastAPI 框架，高性能，易学，快速编码，随时可供生产</em>
</p>
<p align="center">
<a href="https://travis-ci.com/tiangolo/fastapi" target="_blank">
    <img src="https://travis-ci.com/tiangolo/fastapi.svg?branch=master" alt="Build Status">
</a>
<a href="https://codecov.io/gh/tiangolo/fastapi" target="_blank">
    <img src="https://codecov.io/gh/tiangolo/fastapi/branch/master/graph/badge.svg" alt="Coverage">
</a>
<a href="https://pypi.org/project/fastapi" target="_blank">
    <img src="https://badge.fury.io/py/fastapi.svg" alt="Package version">
</a>
<a href="https://gitter.im/tiangolo/fastapi?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge" target="_blank">
    <img src="https://badges.gitter.im/tiangolo/fastapi.svg" alt="Join the chat at https://gitter.im/tiangolo/fastapi">
</a>
</p>

---

**文档**：<a href="https://fastapi.tiangolo.com" target="_blank">https://fastapi.tiangolo.com</a>

**源码**：<a href="https://github.com/tiangolo/fastapi" target="_blank">https://github.com/tiangolo/fastapi</a>

---

FastAPI 是一个现代、快速（高性能）的 Web 框架，基于标准 Python 类型提示，使用 Python 3.6+ 构建 API。

主要功能包括：

* **快速**: 与 **NodeJS** 和 **Go** ，相比有相当的高性能（感谢 Starlette 和 Pydantic）。 [现有最快的Python框架之一](#performance)。

* **快速编码**：将功能开发速度提高约200％至300％。
* **更少的Bug**：减少约40％的人为（开发人员）导致的错误。
* **直观**：更好的编辑支持。补全任何地方（也称为自动完成，自动完成，IntelliSense）。更少的调试时间。
* **简单**：方便使用和学习。减少阅读文档的时间。
* **简洁**：最小化代码重复。每个参数声明的多个要素。更少的错误。
* **Robust**：获取便于生产的代码。带自动交互式文档。
* **基于标准**：基于（并完全兼容）API 的开放标准：<a href="https://github.com/OAI/OpenAPI-Specification" class="external-link" target="_blank">OpenAPI</a>（以前称为Swagger）和 <a href="http://json-schema.org/" class="external-link" target="_blank">JSON Schema</a>。

<small>* 根据内部开发团队的测试进行估算，以构建生产应用程序。</small>

## 观点

"*[...] I'm using **FastAPI** a ton these days. [...] I'm actually planning to use it for all of my team's **ML services at Microsoft**. Some of them are getting integrated into the core **Windows** product and some **Office** products.*"

<div style="text-align: right; margin-right: 10%;">Kabir Khan - <strong>Microsoft</strong> <a href="https://github.com/tiangolo/fastapi/pull/26" target="_blank"><small>(ref)</small></a></div>
---

"*I’m over the moon excited about **FastAPI**. It’s so fun!*"

<div style="text-align: right; margin-right: 10%;">Brian Okken - <strong><a href="https://pythonbytes.fm/episodes/show/123/time-to-right-the-py-wrongs?time_in_sec=855" target="_blank">Python Bytes</a> podcast host</strong> <a href="https://twitter.com/brianokken/status/1112220079972728832" target="_blank"><small>(ref)</small></a></div>
---

"*Honestly, what you've built looks super solid and polished. In many ways, it's what I wanted **Hug** to be - it's really inspiring to see someone build that.*"

<div style="text-align: right; margin-right: 10%;">Timothy Crosley - <strong><a href="http://www.hug.rest/" target="_blank">Hug</a> creator</strong> <a href="https://news.ycombinator.com/item?id=19455465" target="_blank"><small>(ref)</small></a></div>
---

"*If you're looking to learn one **modern framework** for building REST APIs, check out **FastAPI** [...] It's fast, easy to use and easy to learn [...]*"

"*We've switched over to **FastAPI** for our **APIs** [...] I think you'll like it [...]*"

<div style="text-align: right; margin-right: 10%;">Ines Montani - Matthew Honnibal - <strong><a href="https://explosion.ai" target="_blank">Explosion AI</a> founders - <a href="https://spacy.io" target="_blank">spaCy</a> creators</strong> <a href="https://twitter.com/_inesmontani/status/1144173225322143744" target="_blank"><small>(ref)</small></a> - <a href="https://twitter.com/honnibal/status/1144031421859655680" target="_blank"><small>(ref)</small></a></div>
---

"*We adopted the **FastAPI** library to spawn a **REST** server that can be queried to obtain **predictions**. [for Ludwig]*"

<div style="text-align: right; margin-right: 10%;">Piero Molino, Yaroslav Dudin, and Sai Sumanth Miryala - <strong>Uber</strong> <a href="https://eng.uber.com/ludwig-v0-2/" target="_blank"><small>(ref)</small></a></div>
---

## **Typer**，CLI中的FastAPI

<a href="https://typer.tiangolo.com" target="_blank"><img src="https://typer.tiangolo.com/img/logo-margin/logo-margin-vector.svg" style="width: 20%;"></a>

如果要构建用于终端而不是Web API的CLI（Command Line Interface）应用，请查看<a href="https://typer.tiangolo.com/" class="external-link" target="_blank">**Typer**</a>。

**Typer**是FastAPI的小兄弟。它打算成为**CLI中的FastAPI**。⌨️ 🚀

## 依赖

Python 3.6+

FastAPI站在巨人的肩膀上：

* <a href="https://www.starlette.io/" class="external-link" target="_blank">Starlette</a> 用于Web部分。
* <a href="https://pydantic-docs.helpmanual.io/" class="external-link" target="_blank">Pydantic</a> 用于数据部分。

## 安装

```bash
$ pip install fastapi

---> 100%
```

你还需要一个ASGI服务器来进行生产，例如<a href="http://www.uvicorn.org" class="external-link" target="_blank">Uvicorn</a> 或者 <a href="https://gitlab.com/pgjones/hypercorn" class="external-link" target="_blank">Hypercorn</a>。

```bash
$ pip install uvicorn

---> 100%
```

## 示例

### 创建

* 创建一个`main.py` 文件：

```Python
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}
```

<details markdown="1">
<summary>或者使用<code>async def</code>...</summary>
<p>如果你的代码使用 <code>async</code> / <code>await</code>，请使用 <code>async def</code>：</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> fastapi <span class="pl-k">import</span> FastAPI

app <span class="pl-k">=</span> FastAPI()


<span class="pl-en">@app.get</span>(<span class="pl-s"><span class="pl-pds">"</span>/<span class="pl-pds">"</span></span>)
<span class="pl-k">async</span> <span class="pl-k">def</span> <span class="pl-en">read_root</span>():
    <span class="pl-k">return</span> {<span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>World<span class="pl-pds">"</span></span>}


<span class="pl-en">@app.get</span>(<span class="pl-s"><span class="pl-pds">"</span>/items/<span class="pl-c1">{item_id}</span><span class="pl-pds">"</span></span>)
<span class="pl-k">async</span> <span class="pl-k">def</span> <span class="pl-en">read_item</span>(<span class="pl-smi">item_id</span>: <span class="pl-c1">int</span>, <span class="pl-smi">q</span>: <span class="pl-c1">str</span> <span class="pl-k">=</span> <span class="pl-c1">None</span>):
    <span class="pl-k">return</span> {<span class="pl-s"><span class="pl-pds">"</span>item_id<span class="pl-pds">"</span></span>: item_id, <span class="pl-s"><span class="pl-pds">"</span>q<span class="pl-pds">"</span></span>: q}</pre></div>
<p><strong>注意</strong>：</p>
<p>如果你不知道，请在文档中的 <em>"急吗？"</em> 查看有关 <a href="https://fastapi.tiangolo.com/async/#in-a-hurry" rel="nofollow"><code>async</code> 和 <code>await</code></a>的部分。</p>
</details>


### 运行

使用以下命令运行服务：

```bash
$ uvicorn main:app --reload

INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [28720]
INFO:     Started server process [28722]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

<details>
<summary>关于 <code>uvicorn main:app --reload</code>命令...</summary>
<p><code>uvicorn main:app</code> 命令指：</p>
<ul>
<li><code>main</code>：<code>main.py</code>文件（Python“模块”）。</li>
<li><code>app</code>：在<code>main.py</code>内部创建的对象，其中的行是<code>app = FastAPI()</code>。</li>
<li><code>--reload</code>：使服务在代码更改后重新启动。 仅在开发时这样做。</li>
</ul>
</details>


### 检查

在浏览器中打开 <a href="http://127.0.0.1:8000/items/5?q=somequery" class="external-link" target="_blank">http://127.0.0.1:8000/items/5?q=somequery</a>。

你会看到 JSON 响应像是：

```JSON
{"item_id": 5, "q": "somequery"}
```

你已经创建了一个API：

* 在 _路径_ `/`和`/items/{item_id}`中接收HTTP请求。
* 两个 _路径_ 都执行`GET`<em>操作</em>（也称为HTTP_方法_）。
* _路径_ `/items/{item_id}` 有一个 _路径参数_ `item_id` 应该是一个 `int`。
* _路径_ `/items/{item_id}` 有一个可选的`str`类型的 _查询参数_`q`。

### 交互式API文档

现在前往 <a href="http://127.0.0.1:8000/docs" class="external-link" target="_blank">http://127.0.0.1:8000/docs</a>。

你将看到自动交互式API文档（由<a href="https://github.com/swagger-api/swagger-ui" class="external-link" target="_blank">Swagger UI</a>提供）：

![Swagger UI](https://fastapi.tiangolo.com/img/index/index-01-swagger-ui-simple.png)

### 备用的API文档

现在，前往 <a href="http://127.0.0.1:8000/redoc" class="external-link" target="_blank">http://127.0.0.1:8000/redoc</a>。

你将看到备用的自动文档（由<a href="https://github.com/Rebilly/ReDoc" class="external-link" target="_blank">ReDoc</a>提供）：

![ReDoc](https://fastapi.tiangolo.com/img/index/index-02-redoc-simple.png)

## 示例升级

现在修改文件`main.py`以接收来自`PUT`请求的主体。

使用标准的Python类型声明主体，感谢Pydantic。

```Python hl_lines="2  7 8 9 10  23 24 25"
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    price: float
    is_offer: bool = None


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: str = None):
    return {"item_id": item_id, "q": q}


@app.put("/items/{item_id}")
def update_item(item_id: int, item: Item):
    return {"item_name": item.name, "item_id": item_id}
```

服务应该会自动重新加载（因为你在上面的`uvicorn`命令中添加了`--reload`）。

### 交互式API文档升级

现在前往 <a href="http://127.0.0.1:8000/docs" class="external-link" target="_blank">http://127.0.0.1:8000/docs</a>。

* 交互式API文档将自动更新，包含新的正文：

![Swagger UI](https://fastapi.tiangolo.com/img/index/index-03-swagger-02.png)

* 单击按钮“Try it out”，它允许你填充参数并直接与API交互：:

![Swagger UI interaction](https://fastapi.tiangolo.com/img/index/index-04-swagger-03.png)

* 然后单击“Execute”按钮，用户界面将与你的API通信，发送参数，获取结果并将其显示在屏幕上：

![Swagger UI interaction](https://fastapi.tiangolo.com/img/index/index-05-swagger-04.png)

### 备用API文档升级

现在，前往 <a href="http://127.0.0.1:8000/redoc" class="external-link" target="_blank">http://127.0.0.1:8000/redoc</a>。

* 替代文档也将体现新的查询参数和正文：

![ReDoc](https://fastapi.tiangolo.com/img/index/index-06-redoc-02.png)

### 概括

总而言之，你**一次性**将参数的类型，主体等声明为函数参数。 

你可以使用标准的现代Python类型来做到这一点。

你不必学习新的语法，特定库的方法或类等。

只是标准的**Python 3.6 +**。

例如，对于一个`int`：

```Python
item_id: int
```

或更复杂的`Item`模型：

```Python
item: Item
```

...通过单个声明，你将得到：

* 编辑器支持，包括：
    * 代码补全。
    * 类型检查。
* 数据验证：
    * 数据无效时自动清除错误。
    * 甚至对深度嵌套的JSON对象也进行验证。
* 输入数据的转换（也称为：序列化，解析，编组）：从网络转换为Python数据和类型。 阅读：
    * JSON。
    * 路径参数。
    * 查询参数。
    * Cookies。
    * 标头。
    * 表单。
    * 文件。
* 输入数据的转换（也称为：序列化，解析，编组）：从Python数据类型转换为网络数据（如JSON）：
    * 转换Python类型（`str`，`int`，`float`，`bool`，`list`等）。
    * `datetime`对象。
    * `UUID`对象。
    * 数据库模型。
    * ...还有很多。
* 自动交互式API文档，包括2个备用用户界面：
    * Swagger UI.
    * ReDoc.

---

回到前面的代码示例，**FastAPI**将：

* 验证路径中是否有用于`GET`和`PUT`请求的`item_id`。
* 验证`item_id`的类型是否为`GET`和`PUT`请求的`int`类型。
    * 如果不是，客户端将看到一个有用的明确错误。
* 检查是否有一个名为`q`的可选查询参数（如`http://127.0.0.1:8000/items/foo?q=somequery`中的内容）用于`GET`请求。
    * 由于`q`参数是用`= None`声明的，因此它是可选的。
    * 如果没有`None`，则将是必需的（与`PUT`一样，主体也是如此）。
* 对于`/items/{item_id}`的`PUT`请求，将正文读取为JSON：
    * 检查它是否具有必需的`name`属性，该属性应为`str`。
    * 检查它是否具有必需的`price`属性，该属性必须是`float`。
    * 检查它是否具有可选属性`is_offer`，如果存在则应为`bool`。
    * 所有这些对于深度嵌套的JSON对象也适用。
* 自动转换为JSON。
* 使用OpenAPI记录所有内容，可用于：
    * 交互式文档系统。
    * 自动客户端代码生成系统，适用于多种语言。
* 直接提供2个交互式文档Web界面。

---

我们只是从头开始，但你已经了解了所有工作原理。

尝试使用以下更改：

```Python
    return {"item_name": item.name, "item_id": item_id}
```

...从：

```Python
        ... "item_name": item.name ...
```

...到：

```Python
        ... "item_price": item.price ...
```

...并查看编辑器如何自动补全属性并了解其类型：

![editor support](https://fastapi.tiangolo.com/img/vscode-completion.png)

有关包含更多功能的更完整示例，请参阅<a href="https://fastapi.tiangolo.com/tutorial/">教程-用户指南</a>。

**剧透警报**：教程-用户指南包括：

* 从其他不同地方声明**参数**：**标头**，**Cookies**，**表单字段**和**文件**。
* 如何将**验证约束**设置为`maximum_length`或`regex`。
* 一个非常强大且易于使用的**依赖注入**（也称为组件，资源，提供者，服务，可注入）系统。
* 安全性和身份验证，身份验证支持**OAuth2**包括通过**JWT令牌**和**HTTP Basic**。
* 用于声明**深度嵌套的JSON模型**的更高级（但同样容易）的技术（感谢Pydantic）。
* 许多额外的功能（感谢Starlette）：
    * **WebSockets**
    * **GraphQL**
    * 基于`requests`和`pytest`的极其简单的测试
    * **CORS**
    * **Cookie会话**
    * ...和更多。

## 性能

独立的TechEmpower基准测试显示**FastAPI**应用程序在Uvicorn下运行为<a href="https://www.techempower.com/benchmarks/#section=test&runid=7464e520-0dc2-473d-bd34-dbdfd7e85911&hw=ph&test=query&l=zijzen-7" class="external-link" target="_blank">最快的Python框架之一</a>，仅在Starlette和Uvicorn（由FastAPI内部使用）之下。

要了解更多信息，请参阅<a href="https://fastapi.tiangolo.com/benchmarks/" class="internal-link" target="_blank">基准测试</a>。

## 可选依赖项

使用Pydantic：

* <a href="https://github.com/esnme/ultrajson" target="_blank"><code>ujson</code></a> - 为了更快的JSON“解析”（将来自HTTP请求的字符串转换为Python数据）。
* <a href="https://github.com/JoshData/python-email-validator" target="_blank"><code>email_validator</code></a> - for email validation.

使用Starlette：

* <a href="http://docs.python-requests.org" target="_blank"><code>requests</code></a> - 如果要使用`TestClient`，则为必需。
* <a href="https://github.com/Tinche/aiofiles" target="_blank"><code>aiofiles</code></a> - 如果要使用`FileResponse`或`StaticFiles`，则为必需。
* <a href="http://jinja.pocoo.org" target="_blank"><code>jinja2</code></a> - 如果要使用默认模板配置，则为必需。
* <a href="https://andrew-d.github.io/python-multipart/" target="_blank"><code>python-multipart</code></a> - 如果你想使用`request.form()`支持“解析”（将来自HTTP请求的字符串转换为Python数据），则为必需。
* <a href="https://pythonhosted.org/itsdangerous/" target="_blank"><code>itsdangerous</code></a> - 对于`SessionMiddleware`支持是必需的。
* <a href="https://pyyaml.org/wiki/PyYAMLDocumentation" target="_blank"><code>pyyaml</code></a> - 是支持Starlette的`SchemaGenerator`所必需的（FastAPI可能不需要它）。
* <a href="https://graphene-python.org/" target="_blank"><code>graphene</code></a> - 对于`GraphQLApp`支持是必需的。
* <a href="https://github.com/esnme/ultrajson" target="_blank"><code>ujson</code></a> - 如果要使用`UJSONResponse`，则为必需。

使用FastAPI/Starlette：

* <a href="http://www.uvicorn.org" target="_blank"><code>uvicorn</code></a> - 用于加载和服务你的应用程序的服务器。
* <a href="https://github.com/ijl/orjson" target="_blank"><code>orjson</code></a> - 如果要使用`ORJSONResponse`，则为必需。

你可以使用`pip install fastapi[all]`安装所有这些。

## 许可证

该项目根据MIT许可条款获得许可。
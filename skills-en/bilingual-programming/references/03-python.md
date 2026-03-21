# Python Bilingual Guide

## EN: Overview

Python uses docstrings. Google style with triple quotes `"""`.

## CN: 概述

Python 使用文档字符串。Google 风格，三引号 `"""`。

---

## Function

```python
def max(a: T, b: T) -> T:
    """
    EN: Returns the maximum of two values.
    CN: 返回两个值中的最大值。

    Args:
        a:
            EN: First value.
            CN: 第一个值。
        b:
            EN: Second value.
            CN: 第二个值。

    Returns:
        EN: Maximum value.
        CN: 最大值。
    """
```

---

## Class

```python
class Config:
    """
    EN: Generic configuration holder.
    CN: 通用配置持有者。

    Important:
        EN: Immutable after construction.
        CN: 构造后不可变。
    """

    def __init__(self, values: dict) -> None:
        """
        EN: Initialize with values.
        CN: 用值初始化。
        """
        self._values = dict(values)
```

---

## Dataclass

```python
@dataclass
class Status:
    """
    EN: Represents operation status.
    CN: 代表操作状态。
    """
    # EN: Status code.
    # CN: 状态码。
    code: int
    # EN: Status message.
    # CN: 状态消息。
    message: str

---

## Inline

```python
# EN: Check if value is valid.
# CN: 检查值是否有效。
if value is None: return

# EN: Use dict.get with default.
# CN: 用默认值调用 dict.get。
count = data.get('count', 0)
```

---

## Naming

| Type | Style | Example |
|------|-------|---------|
| Function | snake_case | `max` |
| Class | PascalCase | `ConfigManager` |
| Constant | SCREAMING_SNAKE | `MAX_RETRIES` |
| Private | _leading | `_cache` |

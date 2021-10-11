<!-- TOC -->

- [规则](#规则)
    - [DAR002：参数/异常缺少描述](#dar002参数异常缺少描述)
    - [DAR003：参数之间不需要空行](#dar003参数之间不需要空行)
    - [DAR005：文档字符串包含类型括号，但是没有类型](#dar005文档字符串包含类型括号但是没有类型)
    - [DAR006：文档字符串没有Summary](#dar006文档字符串没有summary)
    - [DAR101：文档字符串缺少参数定义](#dar101文档字符串缺少参数定义)
    - [DAR102：文档字符串中存在多余的参数](#dar102文档字符串中存在多余的参数)
    - [DAR104：参数缺少类型](#dar104参数缺少类型)
    - [DAR201：文档字符串缺少定义的返回值](#dar201文档字符串缺少定义的返回值)
    - [DAR401：文档字符串中缺少定义的异常](#dar401文档字符串中缺少定义的异常)
    - [DAR402：文档字符串中包含了不会触发的异常](#dar402文档字符串中包含了不会触发的异常)
    - [DAR600：无序列表前需要空一行](#dar600无序列表前需要空一行)
    - [DAR601：无序列表缩进对齐](#dar601无序列表缩进对齐)

<!-- /TOC -->

# 规则

本文档包含对所有规则的描述、检查的内容，以及违反规则的文档示例和示例的更正版本。

## DAR002：参数/异常缺少描述

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x:

        Returns:
            x * 2
        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```


## DAR003：参数之间不需要空行

- 错误示例

    ```py
    def multiplication(x,y):
        """
        Find the product of two parameters.

        Args:
            x (int): a parameter

            y (int): a parameter

        Returns:
            x * y
        """
        return x * y
    ```

- 正确示例

    ```py
    def multiplication(x,y):
        """
        Find the product of two parameters.

        Args:
            x (int): a parameter
            y (int): a parameter

        Returns:
            x * y
        """
        return x * y
    ```

## DAR005：文档字符串包含类型括号，但是没有类型

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```
- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR006：文档字符串没有Summary

- 错误示例

    ```py
    def double(x):
        """
        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR101：文档字符串缺少参数定义

- 错误示例

    ```py
    def multiplication(x,y):
        """
        Find the product of two parameters

        Args:
            x (int): a parameter

        Returns:
            x * y
        """
        return x * y
    ```

- 正确示例

    ```py
    def multiplication(x,y):
        """
        Find the product of two parameters

        Args:
            x (int): a parameter
            y (int): a parameter

        Returns:
            x * y
        """
        return x * y
    ```

## DAR102：文档字符串中存在多余的参数

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter
            y (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR104：参数缺少类型

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x: a parameter

        Returns:
            x * 2
        """
        return x *2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR201：文档字符串缺少定义的返回值

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR401：文档字符串中缺少定义的异常

- 错误示例

    ```py
    def Positive_judgment(x):
        """
        Determine the positive and negative of the entry parameters.

        Args:
            x (int): a parameter

        """
        if x > 0:
            raise ValueError("a的值大于0，不符合要求")
    ```

- 正确示例

    ```py
    def Positive_judgment(x):
        """
        Determine the positive and negative of the entry parameters.

        Args:
            x (int): a parameter

        Raises:
            ValueError: if x > 0
        """
        if x > 0:
            raise ValueError("a的值大于0，不符合要求")
    ```

## DAR402：文档字符串中包含了不会触发的异常

- 错误示例

    ```py
    def Positive_judgment(x):
        """
        Determine the positive and negative of the entry parameters.

        Args:
            x (int): a parameter

        Raises:
            ValueError: if x > 0

        """
        if x > 0:
            print(x)
    ```

- 正确示例

    ```py
    def Positive_judgment(x):
        """
        Determine the positive and negative of the entry parameters.

        Args:
            x (int): a parameter

        """
        if x > 0:
            print(x)
    ```

## DAR600：无序列表前需要空一行

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter
                - xxxxx
                - xxxxx

        Returns:
            x * 2
        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

                - xxxxx
                - xxxxx

        Returns:
            x * 2
        """
        return x * 2
    ```

## DAR601：无序列表缩进对齐

- 错误示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

                - xxxxxxxxxxxxxxxxxxxxxxxx
                xxxxxxxxxxxxxxxxxxx
                - xxxxx

        Returns:
            x * 2
        """
        return x * 2
    ```

- 正确示例

    ```py
    def double(x):
        """
        Double the input.

        Args:
            x (int): a parameter

                - xxxxxxxxxxxxxxxxxxxxxxxx
                  xxxxxxxxxxxxxxxxxxx
                - xxxxx

        Returns:
            x * 2
        """
        return x * 2
    ```

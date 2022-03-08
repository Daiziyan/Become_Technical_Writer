Python
===========

Basic
------------

通用的装饰器：可以装饰任意类型的函数

.. code:: python

    def decorator(func):
        def inner(num1,num2):
            print("extra function")
            func(num1,num2)

        return inner



    @decorator  #用语法糖方式装饰带有参数的函数 add_number = decorator(add_number)
    def add_number(num1,num2):

        result = num1+ num2
        print(result)

    add_number(1,2)


.. code:: python

# 装饰带有参数带有返回值

    def decorator(func):
        def inner(num1,num2):
            print("extra function")
            num = func(num1,num2)
            return num

        return inner



    @decorator  #用语法糖方式装饰带有参数的函数 add_number = decorator(add_number)
    def add_number(num1,num2):

        result = num1+ num2
        return result

    add_number(1,2)


.. code:: python

# 通用装饰器，可以装饰任意类型函数

    def decorator(func):
        def inner(*args, **kwargs):
            print("extra function")

            num= func(*args, **kwargs)
            return num

        return inner

    @decorator
    def add_number(*args, **kwargs):
        result = 0

        for value in args:
            result += value

        for value in kwargs.values():
            result += value

        return result

    result = add_number(1,2,3)
    print(result)



.. note::

    使用装饰器装饰已有函数时候，内部函数的类型需要与被装饰的函数保持一致。











Advanced
-------------
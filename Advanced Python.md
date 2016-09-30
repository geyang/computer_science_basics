## Class Decorators
```python
class A(object):
    def foo(self,x):
        print "executing foo(%s,%s)"%(self,x)

    @classmethod
    def class_foo(cls,x):
        print "executing class_foo(%s,%s)"%(cls,x)

    @staticmethod
    def static_foo(x):
        print "executing static_foo(%s)"%x    
        
    @property
    def some_foo(self):
        return self._foo
        
    @some_foo.setter
    def some_foo(self, value):
        self._foo = value

a=A()
```

@classmethod
: first variable is class, not instance.

@staticmethod
: there is no first variable. A.k.a no `self` keyword

@property
: pretty self-explainatory.

@<property>.setter
: the setter syntax for a property.

## Python FlatMap

FlatMap is super useful when dealing with nested arrays that you want to treat
as a flat array. In python, this is:
```python
import itertools

flatMap = lambda x: list(itertools.chain.from_iterable(x))

# now you can do:
nested_list = [['haha'], ['this', 'is', 'awesome!']]
standard_out = ' '.join(flatMap(nested_list))
print(standard_out)

"""
haha this is awesome!
"""
```

## 
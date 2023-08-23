# Hi there 👋

Can you help me learn `Haskell`?

My OOP mind struggles every time I attempt to learn it 😢

```haskell
fibs = 0 : 1 : zipWith (+) fibs (tail fibs)
```

## About me

I am a Software Engineer who mostly works with `Python` but used to work with `C/C++` and `Java` a long time ago.
Hope one day I will be able to understand `Haskell` (I have a dream to learn functional programming).

[`PEP 505 None-aware operators`](https://peps.python.org/pep-0505/) is a feature that I miss the most in `Python`.
```js
I?.really?.want?.this?.feature ?? "Or not?"
```

## Things done by me

### FastAPI related

If you are using `FastAPI` and use function return type annotation as `response_model` you should know -
I am the one who implemented it 😄 [(FastAPI #1436)](https://github.com/tiangolo/fastapi/pull/1436).

```py
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI(title="Bio")


class Bio(BaseModel):
    name: str
    education: str
    languages: set[str]


@app.get("/me")
async def get_bio() -> Bio:
    return Bio(
        name="Yurii",
        education="Master's degree in Computer Engineering",
        languages={"Ukrainian", "English", "Polish", "German (a bit)"},
    )
```

Also, I have created [`fastapi-pagination`](https://github.com/uriyyo/fastapi-pagination)
package that helps you to paginate things (obviously) using `FastAPI` 📖.
Another thing that I currently work on is [`fastapi-filters`](https://github.com/uriyyo/fastapi-filters) package.
Hope one day it will be useful for someone as `fastapi-pagination` is 🍸.

### Python related

I have several contributions to `Python` itself ([commits](https://github.com/python/cpython/commits/main/?author=uriyyo)).
The most interesting one is [(#23316 Store func annotations as a tuple)](https://github.com/python/cpython/pull/23316).
This optimization reduces memory footprint and improves performance of loading modules having many func annotations.

```py
>>> sys.getsizeof({"a":"int","b":"int","return":"int"})
232
>>> sys.getsizeof(("a","int","b","int","return","int"))
88
```

The tuple is converted into `dict` on the fly when `func.__annotations__` is accessed first.

### PyCharm related

I have created a plugin ([pycharm-evaluate-async-code](https://github.com/uriyyo/pycharm-evaluate-async-code))
for PyCharm that helps you evaluate async code the using `Evaluate Expression` window.
This is really useful when you are debugging your code and want to check some async stuff.
I guess it's my favorite project that I have ever done (because I used it every day and it really saved me a lot of time).

<h1 align="center">
<img width="75%" alt="evaluate_expression" src="https://github.com/uriyyo/pycharm-evaluate-async-code/blob/master/images/evaluate_expression.jpeg?raw=true">
</h1>

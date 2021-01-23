---
tags:
---
Link: [StackOverflow](https://stackoverflow.com/questions/1788923/parameter-vs-argument)

# Parameter vs. Argument
Consider the following code:

```
void Foo(int i, float f)
{
    // Do things
}

void Bar()
{
    int anInt = 1;
    Foo(anInt, 2.0);
}
```

Here `i` and `f` are the parameters, and `anInt` and `2.0` are the arguments.
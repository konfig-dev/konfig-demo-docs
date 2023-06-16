# How to create a select input

To do this:

:::form

::enum{name=SERVICE label=Service description="Was your service good?" data="Good,Bad"}

```python
if SERVICE == "Good":
    print("Come again!")
else:
    print("What happened?")
```

::button[Run Code]

:::

Write this:

````markdown
:::form

::enum{name=SERVICE label=Service description="Was your service good?" data="Good,Bad"}

```python
if SERVICE == "Good":
    print("Come again!")
else:
    print("What happened?")
```

::button[Run Code]

:::
````

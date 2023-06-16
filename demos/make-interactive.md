# Input: Text

To do this:

:::form

::input{name=NAME label=Name description="What is your name?"}

```python
print("Hello {}!".format(NAME))
```

::button[Run Code]

:::

Write this:

````markdown
:::form

::input{name=NAME label=Name description="What is your name?"}

```python
print("Hello {}!".format(NAME)) # Note that "NAME" comes from the "name" attribute on the above ::input
```

::button[Run Code]

:::
````

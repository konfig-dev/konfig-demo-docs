# Input: Password

To do this:

:::form

::input{name=PASSWORD label=Password description="Password type inputs are hidden" type="password"}

```python
print("Your password is {}!".format(PASSWORD))
```

::button[Show Password]

:::

Write this:

````markdown
:::form

::input{name=PASSWORD label=Password description="Password type inputs are hidden" type="password"}

```python
print("Your password is {}!".format(PASSWORD))
```

::button[Show Password]

:::
````

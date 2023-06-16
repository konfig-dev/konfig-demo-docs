# How to write multi-step interactive demo

To do this:

# 1) Assign First and Last Name

:::form

::input{name=FIRST_NAME label="First Name" description="Assign 'first_name' to a string"}
::input{name=LAST_NAME label="Last Name" description="Assign 'last_name' to a string"}

```python
first_name = FIRST_NAME
last_name = LAST_NAME
print("Assigned first and last name")
```

::button[Initialize First and Last Name]

:::

# 2) Print Full Name

:::form

```python
print("{} {}".format(first_name, last_name))
```

::button[Print Full Name]

:::

Write this:

````markdown
:::form

::input{name=FIRST_NAME label="First Name" description="Assign 'first_name' to a string"}
::input{name=LAST_NAME label="Last Name" description="Assign 'last_name' to a string"}

```python
first_name = FIRST_NAME
last_name = LAST_NAME
print("Assigned first and last name")
```

::button[Initialize First and Last Name]

:::

# 2) Print Full Name

:::form

```python
print("{} {}".format(first_name, last_name))
```

::button[Print Full Name]

:::
````

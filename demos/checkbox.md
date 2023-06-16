# How to create a checkbox input

To do this:

:::form

::input{name=BURGER type="checkbox" defaultValue=false label="Burger" description="Give me a burger!"}
::input{name=FRIES type="checkbox" defaultValue=true label="Fries" description="Give me fries!"}

```python
if BURGER:
    print("Here is your burger!")
if FRIES:
    print("Here is your fries!")
if not BURGER and not FRIES:
    print("Are you even hungry?")
```

::button[Order]

:::

Write this:

````markdown
:::form

::input{name=BURGER type="checkbox" defaultValue=false label="Burger" description="Give me a burger!"}
::input{name=FRIES type="checkbox" defaultValue=true label="Fries" description="Give me fries!"}

```python
if BURGER:
    print("Here is your burger!")
if FRIES:
    print("Here is your fries!")
if not BURGER and not FRIES:
    print("Are you even hungry?")
```

::button[Order]

:::
````

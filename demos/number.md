# Input: Number

To do this:

:::form

::number{name=PRICE label="Price" defaultValue=1 step=0.01 precision=2 min=0 description="Has 2 decimal precision and a minimum value of 0.00"}

```python
print(PRICE)
```

::button[Print Number]

:::

Write this:

````markdown
:::form

::number{name=PRICE label="Price" defaultValue=1 step=0.01 precision=2 min=0 description="Has 2 decimal precision and a minimum value of 0.00"}

```python
print(PRICE)
```

::button[Print Number]

:::
````

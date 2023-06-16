# Connect outputs to inputs

To do this:

:::form

```python
outputs = [1, 2, 3, 4, 5]
for output in outputs:
    print("::SAVE[OUTPUT]/{}".format(output))
print("Printed outputs according to '::SAVE[LABEL]/TEXT' protocol")
```

::button[Produce Outputs]

:::

:::form

::enum{name=OUTPUT label="Output" placeholder="Select an output" savedData=OUTPUT description="Taken from output of previous cell"}

```python
print(OUTPUT)
```

::button[Print Selection]

:::

Write this:

````markdown
:::form

```python
outputs = [1, 2, 3, 4, 5]
for output in outputs:
    print("::SAVE[OUTPUT]/{}".format(output))
print("Printed outputs according to '::SAVE[LABEL]/TEXT' protocol")
```

::button[Produce Outputs]

:::

:::form

::enum{name=OUTPUT label="Output" placeholder="Select an output" savedData=OUTPUT description="Taken from output of previous cell"}

```python
print(OUTPUT)
```

::button[Print Selection]

:::
````

# Connect outputs to inputs

To do this:

:::form

```python
import random
import string

def generate_random_string(length):
    characters = string.ascii_letters + string.digits
    return ''.join(random.choice(characters) for _ in range(length))

num_strings = 10
string_length = 8

random_strings = [generate_random_string(string_length) for _ in range(num_strings)]

for string in random_strings:
    print(string)
    print("::SAVE[OUTPUT]/{}".format(string))

print("Printed outputs using the '::SAVE[LABEL]/TEXT' protocol")
```

::button[Produce Outputs]

:::

The following select input contains generated values from the previous code snippet.

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
import random
import string

def generate_random_string(length):
    characters = string.ascii_letters + string.digits
    return ''.join(random.choice(characters) for _ in range(length))

num_strings = 10
string_length = 8

random_strings = [generate_random_string(string_length) for _ in range(num_strings)]

for string in random_strings:
    print(string)
    print("::SAVE[OUTPUT]/{}".format(string))

print("Printed outputs using the '::SAVE[LABEL]/TEXT' protocol")
```

::button[Produce Outputs]

:::

The following select input contains generated values from the previous code snippet.

:::form

::enum{name=OUTPUT label="Output" placeholder="Select an output" savedData=OUTPUT description="Taken from output of previous cell"}

```python
print(OUTPUT)
```

::button[Print Selection]

:::
````

# How to format outputs

Konfig will automatically detect and format the output from the Python code that
is executed. The following formats are supported:

### Raw

:::form{skippable}

```python
print("Hello, world!")
```

::button[Show Raw Output]
:::

### JSON

:::form{skippable}

```python
import json

json_object = {"hello": "world!"}

json_formatted_str = json.dumps(json_object, indent=2)

print(json_formatted_str)
```

::button[Show JSON Output]
:::

### Table [JSON Array]

:::form{skippable}

```python
import json
import random

first_names = [
    "John", "David", "Michael", "James", "Robert", "William", "Joseph",
    "Daniel", "Thomas", "Charles", "Christopher", "Matthew", "Andrew",
    "Steven", "Edward", "Brian", "Kevin", "Mark", "Anthony", "Donald"
]

last_names = [
    "Smith", "Johnson", "Brown", "Taylor", "Miller", "Anderson", "Clark",
    "Walker", "Hall", "Allen", "Young", "King", "Scott", "Lee", "Baker",
    "Green", "Hill", "Adams", "Nelson", "Carter"
]

def generate_random_name():
    first_name = random.choice(first_names)
    last_name = random.choice(last_names)
    return {"First Name": first_name, "Last Name": last_name}

array = []

# Generate and print 200 random names
for _ in range(200):
    array.append(generate_random_name())

json_formatted_str = json.dumps(array, indent=2)
print(json_formatted_str)
```

::button[Show Table Output]
:::

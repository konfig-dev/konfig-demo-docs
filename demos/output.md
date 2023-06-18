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

### Table

:::form

```python
import json

json_object = [{"index": 1, "message": "hello"}, {"index": 1, "message": "world!"}]

json_formatted_str = json.dumps(json_object, indent=2)

print(json_formatted_str)
```

::button[Show Table Output]
:::

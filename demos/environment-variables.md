# How to dynamically set environment variables

To set an environment variable use `%env` and prepend your variable with a `$` sign in your Python code.

:::form

::input{name=MY_VAR label="My Variable"}

```python
%env MY_ENVIRONMENT_VARIABLE = $MY_VAR
import os

print(os.environ["MY_ENVIRONMENT_VARIABLE"])
```

::button[Set Environment Variable]

:::

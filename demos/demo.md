# Demo: User API

This demo runs through a sequence of read and write operations on a fake User API.

## Read

### List users

:::form

```python
import random
from uuid import uuid4
import json

def id():
    return str(uuid4())

# Fake dataset initialization
users = [
    {"id": id(), "name": "John Doe", "email": "john@example.com"},
    {"id": id(), "name": "Jane Smith", "email": "jane@example.com"},
    {"id": id(), "name": "Alice Johnson", "email": "alice@example.com"}
]

products = [
    {"id": id(), "name": "Product A", "price": 9.99},
    {"id": id(), "name": "Product B", "price": 14.99},
    {"id": id(), "name": "Product C", "price": 19.99}
]

# CRUD operations

# Read operation: Get all users
def get_all_users():
    # Save all users for usage in next cell
    for user in users:
        print("::SAVE[USERS]/{}".format(user["id"]))
    return users

# Read operation: Get user by ID
def get_user_by_id(user_id):
    for user in users:
        if user['id'] == user_id:
            return user
    return None

# Create operation: Add a new user
def add_user(user_data):
    user_data["id"] = id()
    users.append(user_data)
    return user_data

# Update operation: Update user details
def update_user(user_id, new_data):
    user = get_user_by_id(user_id)
    if user:
        user.update(new_data)
    else:
        print(f"User with ID {user_id} not found.")

# Delete operation: Remove a user
def delete_user(user_id):
    user = get_user_by_id(user_id)
    if user:
        users.remove(user)
    else:
        print(f"User with ID {user_id} not found.")

# Print all users (initial state)
print(json.dumps(get_all_users(), indent=2))
```

::button[List users]

:::

### Get user by ID

:::form{skippable}

::enum{name=USER_ID label="User ID" savedData=USERS}

```python
# Read a user by ID
user = get_user_by_id(USER_ID)
print(json.dumps(user, indent=2))
```

::button[Get user by ID]

:::

## Write

### Create user

:::form{skippable}

::input{name=NAME label=Name}
::input{name=EMAIL label=Email}

```python

# Add a new user
new_user = {"name": NAME, "email": EMAIL}
created_user = add_user(new_user)
print(json.dumps(get_all_users(), indent=2))
```

::button[Create user]

:::

### Update user

:::form{skippable}

::enum{name=USER_ID label="User ID" savedData=USERS}
::input{name=NAME label=Name}
::input{name=EMAIL label=Email}

```python
# Update user details
update_user(USER_ID, {"name": NAME, "email": EMAIL})

print(json.dumps(get_all_users(), indent=2))
```

::button[Update user]

:::

### Delete user

:::form{skippable}

::enum{name=USER_ID label="User ID" savedData=USERS}

```python
# Delete a user
delete_user(USER_ID)
print(json.dumps(get_all_users(), indent=2))
```

::button[Delete user]

:::

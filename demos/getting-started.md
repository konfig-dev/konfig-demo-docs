# Create your first demo

In this tutorial we will create a demo portal from scratch and add a piece of interactivity.

### 1) Create a GitHub repository

Demo portals are hosted in a GitHub repository. The repository must contains a
folder called `demos/` with a `demo.yaml` file.

```
[git repo]
└── demos
    └── demo.yaml
```

The `demo.yaml` consists of three fields:

- `organizationName`: shows in the name of the tab in the browser
- `portalName`: shows in the top-left corner of the demo portal
- `demos`: defines the order of demos in the left-side navigation bar

```yaml
organizationName: Konfig
portalName: Konfig Documentation
demos:
  - id: getting-started
```

Add a new file called `getting-started.md` under the `demos/` folder.

```markdown
# Getting Started

Hello world!
```

Finally, add a GitHub workflow under
`.github/workflows/konfig-revalidate-demos.yaml`. This workflow ensures that
updates to your demo portal are automatically published.

```yaml
name: konfig-revalidate-demos
on:
  push:
    branches:
      - main
jobs:
  konfig-revalidate-demos:
    runs-on: ubuntu-latest
    env:
      CLI_VERSION: 1.0.208
    steps:
      - uses: actions/checkout@v3
      - name: Cache node_modules
        id: cache-npm
        uses: actions/cache@v3
        with:
          # npm cache files are stored in "~/.npm" on Linux/macOS
          path: ~/.npm
          key: ${{ runner.os }}-build-${{ env.CLI_VERSION }}
      - name: Install Konfig CLI
        run: npm install -g konfig-cli@$CLI_VERSION
      - name: Revalidate Demos
        run: konfig revalidate-demos -o [GITHUB_OWNER] -p [GITHUB_REPO]
```

### 2) Install Konfig Bot

Go to [https://github.com/apps/konfig-bot](https://github.com/apps/konfig-bot)
and install the Konfig Bot to your newly created repository.

### 3) Push your changes

```shell
$ git add -A
$ git push
```

### 4) Navigate to your demo portal

Your demo portal is now live 🎉! Go to
`https://demo.konfigthis.com/[OWNER]/[REPO]` where `[OWNER]` is the name of your
GitHub username and `[REPO]` is the name of your repository.

## Adding Interactivity

:::info{title="Sandbox Environment"}

To preview your demo portal, go to the :a[sandbox environment]{href="https://demo.konfigthis.com/sandbox" target=\_blank} and click the button that says
`Specify directory with "demo.yaml"`. Once you are prompted with a file viewer,
select the `demo/` directory you created. You will be prompted with a preview of
your demo portal. After you make changes to your demo, you can simply refresh
the preview by clicking the green button in the top-right.
:::

### 5) Running Code

To add interactivity, add a section of code like so:

````markdown
:::form

::input{name=NAME label=Name description="What is your name?"}

```python
print("Hello {}!".format(NAME))
```

::button[Run Code]

:::
````

The `:::form` marks the start of a container block. If the container block
contains a `python` snippet and a `::button` then clicking the button will run
the Python code.

1. Search for a code snippet with `python` language syntax highlighting
2. Run the Python code then a `::button` is clicked

The demo should not include a snippet that looks like:

:::form

::input{name=NAME label=Name description="What is your name?"}

```python
print("Hello {}!".format(NAME))
```

::button[Run Code]

Click the button above ⬆️ to run the code.

:::

### Conclusion

Congratulations, you have now made your first interactive demo!

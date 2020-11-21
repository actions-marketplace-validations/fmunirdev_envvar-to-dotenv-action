# env vars to dotenv action

A GitHub composite action to append environment variables to a dotenv file.

Inspired by: [TickX/var-to-dotenv](https://github.com/TickX/var-to-dotenv) and [CallePuzzle/envvar-to-dotenv-action](https://github.com/CallePuzzle/envvar-to-dotenv-action).

## Usage

### Single variable

```yaml
jobs:
  single:
    name: Single
    runs-on: ubuntu-latest
    steps:
      - name: Creating .env file
        uses: fmunirdev/envvar-to-dotenv-action@v0.1.0
        env:
          ENV_VAR1: 'value'
        with:
          variableName: ENV_VAR1
```

### Multiple variables

```yaml
jobs:
  multiple:
    name: Multiple
    runs-on: ubuntu-latest
    steps:
      - name: Creating .env file
        uses: fmunirdev/envvar-to-dotenv-action@v0.1.0
        env:
          ENV_VAR1: 'value 1'
          ENV_VAR2: 'value 2'
          ENV_VAR3: 'value 3'
        with:
          variableName: ENV_VAR1,ENV_VAR2,ENV_VAR3
```

### With GitHub Secrets

```yaml
jobs:
  multiple:
    name: Multiple
    runs-on: ubuntu-latest
    steps:
      - name: Creating .env file
        uses: fmunirdev/envvar-to-dotenv-action@v0.1.0
        env:
          SECRET_VAR1: ${{ secrets.SECRET_VAR1 }}
          ENV_VAR: 'value'
        with:
          variableName: SECRET_VAR1,ENV_VAR
```

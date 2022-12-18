# django-github-actions
GitHub Actions workflow that runs tests with a consistent Python version whenever someone opens a pull request in the repository:

```
name: Run Django tests

on: pull_request

jobs:
  test:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.8'
      - name: Install dependencies
        run: make install
      - name: Run tests
        run: make test
```

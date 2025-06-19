## COPILOT CODE CREATION OPERATIONAL GUIDELINES FOR Python

### PRIME DIRECTIVE

You are a elite and specialized python coder focused on helping developers create high-quality, maintainable Python code.
You always plan your changes before making any edits, and you ensure that your code is well-structured and easy to understand as expla in <prompt-file>[code.prompt.md](code.prompt.md)</prompt-file>
You follow the MANDATORY CODE CREATION GUIDELINES below to ensure code quality and maintainability this includes following best practices, using appropriate libraries, and writing tests for python code.

### MANDATORY CODE CREATION GUIDELINES

-   Follow the instructions in the <prompt-file>[code.prompt.md](code.prompt.md)</prompt-file> file for general code creation guidelines.
-   Use Python version 3.12.
-   Place all source Python code under `/src/python`.
-   Place all test code under `/tests/python/`.
-   Organize code into logical modules and use descriptive file and folder names.
-   Follow PEP 8 for code style and formatting.
-   Use type hints for all function signatures.
-   Write docstrings for all public functions and classes.
-   Use f-strings for string formatting.
-   Prefer explicit exception handling and fail fast on unexpected errors.
-   Use `pyproject.toml` to manage dependencies and pin versions.
-   Use `numpy` for numerical operations when needed.
-   Use `pytest` for testing.
-   Use `@pytest.mark.parametrize` to write parameterized tests.

#### Example: Python Function Template

```python
import numpy as np

def add(a: int, b: int) -> int:
    return a + b

def divide(a: int, b: int) -> np.float32:
    with np.errstate(divide="raise", invalid="raise"):
        return np.divide(a, b)
```

#### Example: Parametrized Test Template

```python
import pytest

@pytest.mark.parametrize(
  "a, b, expected",
  [
    (1, 2, 3),
    (5, 7, 12),
    (-1, 1, 0),
  ]
)
def test_add(a, b, expected):
  assert add(a, b) == expected
```

#### Practices to Avoid

-   Do not commit API keys, secrets, or credentials to the repository.
-   Do not use deprecated or obsolete libraries.
-   Avoid using `print` except for quick scripts or debugging. Use the `logging` module instead.
-   Do not use wildcard imports (e.g., `from module import *`).
-   Do not ignore test failures or linting errors.

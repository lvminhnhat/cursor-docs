# Python Code Standards Summary

## PEP 8 - Style Guide
- **Indentation**: 4 spaces per indentation level
- **Line length**: Maximum 79 characters
- **Imports**: One import per line, grouped in order (standard library, third-party, local)
- **Whitespace**: No trailing whitespace, one space after commas
- **Blank lines**: 2 blank lines around top-level functions/classes, 1 around methods

## Naming Conventions
- **Variables/functions**: `snake_case` (e.g., `user_name`, `get_data()`)
- **Classes**: `PascalCase` (e.g., `UserProfile`, `DataProcessor`)
- **Constants**: `UPPER_CASE` (e.g., `MAX_SIZE`, `API_KEY`)
- **Private members**: Start with `_` (e.g., `_private_method`)
- **Magic methods**: Double underscores `__init__`, `__str__`

## Code Structure
- **Functions**: Single responsibility, descriptive names, max 20-30 lines
- **Classes**: Group related attributes and methods
- **Modules**: Separate code into logical files
- **Packages**: Organize related modules together
- **Docstrings**: Document functions, classes, and modules

## Best Practices
- **DRY Principle**: Don't Repeat Yourself - avoid code duplication
- **Error Handling**: Use try/except blocks appropriately
- **Type Hints**: Specify data types (Python 3.5+)
- **List Comprehensions**: Use instead of simple loops when readable
- **Context Managers**: Use `with` statements for resource management
- **Virtual Environments**: Isolate project dependencies

## Code Quality Tools
- **Linting**: `flake8`, `pylint`, `ruff`
- **Formatting**: `black`, `autopep8`
- **Type Checking**: `mypy`, `pyright`
- **Testing**: `pytest`, `unittest`
- **Documentation**: `sphinx`, `mkdocs`

## Security Standards
- **Input Validation**: Always validate and sanitize user input
- **SQL Injection**: Use parameterized queries
- **Dependencies**: Keep packages updated, use `pip-audit`
- **Secrets**: Never hardcode credentials, use environment variables

## Performance Guidelines
- **Profiling**: Use `cProfile` to identify bottlenecks
- **Memory Usage**: Be mindful of large data structures
- **Algorithms**: Choose appropriate data structures and algorithms
- **Caching**: Implement caching for expensive operations

## Testing Standards
- **Unit Tests**: Test individual functions/methods
- **Integration Tests**: Test component interactions
- **Coverage**: Aim for >80% code coverage
- **Test Naming**: Descriptive test names following `test_should_do_something_when_condition`

These standards ensure code readability, maintainability, and team collaboration.

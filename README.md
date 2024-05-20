# lsp-grep
An LSP-aware grep tool. `lsp-grep` finds not only the line in which a query is contained but the entire construct in which it is used.

### Example
Given the following code:
```python
def foo(
  bar: str,
  waz: int,
) -> str:
  ...
  return
```

Using traditional `grep` to search for `waz`:
```sh
grep 'waz' example.py
```
Output:
```
  waz: int,
```

Using `lsp-grep` to search for `waz`:
```sh
lsp-grep 'waz' example.py
```
Output:
```python
def foo(
  bar: str,
  waz: int,
) -> str:
```

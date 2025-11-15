# Custom argument types

Helpers used with `argparse` to parse and validate complex values.

## `comma_list(value: str) -> list[str]`
Turn `"a,b, c"` into `["a", "b", "c"]` (trims and drops empties).

## `key_value_pair(value: str) -> dict[str, str]`
Turn `'k=v, a=b'` into `{ 'k': 'v', 'a': 'b' }`.  Raises `ArgumentTypeError` on malformed items.

## `existing_path(value: str) -> pathlib.Path`
Convert to `Path` and ensure it exists; raises `ArgumentTypeError` otherwise.

# ArgParsed base

`ArgParsed` is a small base class to build CLI‑driven components with clean argument registration, validation hooks, and a single `main()` entrypoint.

## Import
```python
from tvi.solphit.base.arg_parsed import ArgParsed
```

## Pattern
```python
import argparse
from tvi.solphit.base.arg_parsed import ArgParsed

class MyJob(ArgParsed):
    @classmethod
    def register_arguments(cls, p: argparse.ArgumentParser) -> None:
        p.add_argument("--name", default="world")
        p.add_argument("--repeat", type=int, default=1)

    def __init__(self, *, name: str, repeat: int):
        self.name, self.repeat = name, repeat

    @classmethod
    def validate_args(cls, args: argparse.Namespace) -> None:
        if args.repeat < 1:
            raise argparse.ArgumentTypeError("--repeat must be >= 1")

    def run(self) -> str:
        return " ".join([self.name] * self.repeat)

if __name__ == "__main__":
    MyJob.main()
```

## API
- `register_arguments(parser)` — subclass hook to define args
- `validate_args(args)` — subclass hook for cross‑arg validation
- `from_args(args)` — map parsed args to constructor (1:1 by default)
- `build_parser(...)` — create parser with helpful defaults
- `parse_args(argv=None, **parser_kwargs)` — parse args (inject `argv` in tests)
- `main(argv=None, instantiate_only=False, **parser_kwargs)` — full pipeline

See also: [Custom argument types](arg_types.md).

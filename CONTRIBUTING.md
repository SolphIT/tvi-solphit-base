# Contributing

### Dev setup
```bash
python -m venv .venv && source .venv/bin/activate
python -m pip install -U pip
python -m pip install -e .[test] || python -m pip install -e . && python -m pip install pytest
```

### Test
```bash
pytest
```

### Style (optional)
If you enable pre-commit hooks:
```bash
pip install pre-commit
pre-commit install
```

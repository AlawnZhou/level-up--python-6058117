## Cursor Cloud specific instructions

This repository is a collection of 15 standalone Python exercise scripts for a LinkedIn Learning course ("Python: Level Up"). There is no application server, database, or multi-service architecture.

### Structure

Each numbered directory (`01/` through `15/`) contains an independent Python script. Scripts are run individually via `python3 <dir>/<script>.py`. Most scripts have their `if __name__ == '__main__'` blocks commented out — import the functions directly or uncomment the blocks to run them.

### Running scripts

```
python3 -c "from importlib.machinery import SourceFileLoader; m = SourceFileLoader('mod', '01/factor.py').load_module(); print(m.get_prime_factors(630))"
```

Or add the directory to `sys.path` and import directly.

### Linting

- `flake8 --max-line-length=120 <dir>/` — style checks
- `pylint --disable=C0111 <dir>/<script>.py` — static analysis

Both `flake8` and `pylint` are installed by the update script.

### Testing

There is no test suite in this repository. Validate scripts by importing and calling functions directly.

### Dependencies

Only external dependency is `requests>=2.28` (used by exercise 15). All other imports are Python standard library. See `requirements.txt`.

### Exercises requiring external resources

- **08/send_email.py** — requires SMTP credentials (not available in CI/cloud environments).
- **15/download_files.py** — requires internet access to download files from URLs.

# reactivated playground

https://www.reactivated.io/

If you don't have yarn installed go to `/python3.9/site-packages/reactivated/processes.py` and change `yarn` to `npx`.

```py
def start_tsc() -> None:
    tsc_process = subprocess.Popen(
        ["npx", "tsc", "--watch", "--noEmit", "--preserveWatchOutput"],
        # stdout=subprocess.PIPE,
        # stderr=subprocess.PIPE,
        env={**os.environ.copy()},
    )
    atexit.register(lambda: tsc_process.terminate())

```

### Setup commands

```
poetry run python manage.py generate_client_assets
poetry run python manage.py migrate
```
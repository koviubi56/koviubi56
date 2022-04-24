# Close

How to exit from my python code?

Press `CTRL+C`. This raises an `KeyboardInterrupt` error, which _can be catched_.

If you're on linux, you can also try `CTRL+Z`.

If you want to exit _with code_, try these:
- best: `sys.exit()`
- still ok: `raise SystemExit`
- please don't: `exit()` or `quit()`
- only if you have to: `os._exit()`

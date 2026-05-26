# scoop-cshw

A [Scoop](https://scoop.sh/) bucket for [cshw](https://github.com/tropibyte/CSHW) — C Shell for Windows.

## Install

```powershell
scoop bucket add tropibyte https://github.com/tropibyte/scoop-cshw
scoop install cshw
```

That's it. Open a fresh terminal and run `cshw`.

## What is cshw?

cshw is a modern, single-binary csh-compatible shell for Windows. It bundles:

- The csh language surface — `set`, `alias`, `foreach`, `if/else/endif`, backticks, etc.
- A POSIX bc + dc calculator built in, with the usual `scale`/`ibase`/`obase` and standard math library.
- An opt-in **exact-arithmetic mode** for bc (`bc -x`) that keeps rationals as `p/q` and `sqrt` as `Power(rational, rational)` — `bc -x "1/3 + 1/6"` prints `1/2`, not `.4999…`.
- Concurrent coroutines via `corunproc` / `cowait`.
- Pathmap-style Unix-path translation (`/tmp`, `/mnt/c`, etc.) so real-world csh scripts mostly Just Work.
- ~200 builtins — text tools (sed, awk, grep, head, tail, cut, sort, uniq, …), file ops, process control, registry access, sockets, archives, hashing, and more.

See the [cshw repo](https://github.com/tropibyte/CSHW) for full documentation, builtin list, and release notes.

## Update

```powershell
scoop update cshw
```

The manifest's `checkver` and `autoupdate` blocks pick up new releases automatically when [the bucket is bumped](https://github.com/lukesampson/scoop/wiki/Updating-bucket).

## Uninstall

```powershell
scoop uninstall cshw
```

This runs cshw's bundled uninstaller, which removes `%ProgramFiles%\Tropibyte\cshw` and reverts the PATH addition.

## License

cshw itself is under the [PolyForm Small Business License 1.0.0](https://polyformproject.org/licenses/small-business/1.0.0) — see [its LICENSE](https://github.com/tropibyte/CSHW/blob/master/LICENSE). The manifests in this bucket are MIT-licensed; do whatever you want with them.

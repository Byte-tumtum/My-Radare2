# My Radare2

Personal radare2 configuration: an rc file plus an r2 aliases profile.

## Files

- `radare2rc` — the main config (`e` settings for UI/colors, disassembly, analysis, hex/search). Install to `~/.radare2rc` (r2's default rc path).
- `profile.rr2` — r2 aliases for quick navigation/inspection ($aa, $M, $df, $op, $dec, $hx, $str, $funcs, ...). Install to `~/.config/radare2/profile.rr2` and add this line to `~/.radare2rc` so it loads every session:

```
. /home/YOURUSER/.config/radare2/profile.rr2
```

In-session you can also load it manually with: `. path/to/profile.rr2`

## Usage example

```
r2 ./binary
$aa        # full analysis (once per file)
$M         # jump to main
$df        # disassemble function at cursor
$dec       # pseudo-C decompiler
$hx        # 64-byte hexdump
```

List all aliases with `$*`; inspect one with `$df?`.

Note: the alias is `$M` (not `$main`) — r2 reserves `$<name>` for "seek to flag <name>", so an alias literally named `$main` collides with that.

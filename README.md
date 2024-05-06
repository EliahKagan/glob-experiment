# glob-experiment - A `.gitignore` glob pattern experiment

This is a test repository for inspecting the output of `git` commands that
operate based on `.gitignore` patterns, such as the command:

```sh
git check-ignore -vn "XXX/\'"
```

That command has the same effect in both PowerShell and in POSIX-compatible
(Bourne-style) shells like Bash: the final command-line argument is treated as
the literal text `XXX/\'`. (On Windows, this is itself escaped and included in
a command string from which it has to be parsed out, but the usual parsing
rules turn it back into the literal value.)

The value `XXX/\'`, and the pattern `*/\'` in `.gitignore`, are from
[`make_baseline.sh`](https://github.com/Byron/gitoxide/blob/048e43e26908b0572852a75780a451460dc152ff/gix-glob/tests/fixtures/make_baseline.sh#L16)
in the test suite of [gitoxide](https://github.com/Byron/gitoxide).

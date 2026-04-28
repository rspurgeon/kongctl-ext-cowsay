# kongctl-ext-cowsay

A sample [kongctl](https://github.com/Kong/kongctl) extension that prints a
message in an ASCII speech bubble alongside a cow. Self-contained — needs only
a POSIX `sh` and `awk`.

## Install

```sh
kongctl install extension rspurgeon/kongctl-ext-cowsay
```

Pin to a specific release:

```sh
kongctl install extension rspurgeon/kongctl-ext-cowsay@v0.1.0
```

## Usage

Render a message:

```sh
kongctl cowsay "hello world"
kongctl cowsay -W 20 "the quick brown fox jumps over the lazy dog"
echo "from stdin" | kongctl cowsay
```

Render the output of a host `kongctl` command via a subcommand:

```sh
kongctl cowsay me            # pipes `kongctl get me` through the cow
```

Use `--` to render a literal message that starts with a subcommand name:

```sh
kongctl cowsay -- me and you
```

## Local development

Link the working tree into `kongctl` to test changes without packaging:

```sh
kongctl link extension .
kongctl cowsay "linked"
```

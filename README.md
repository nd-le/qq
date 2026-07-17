# qq

A tiny AI assistant for your terminal.

`qq` lets you chat directly from your shell and remembers conversation history across invocations, so every command continues where the last one left off. Use `-n` to start a fresh conversation and `-s` to force a live web search.

## Examples

```bash
qq what is the capital of france
qq "how do I squash git commits?"
qqs latest python release
qqn explain recursion            # start a new conversation
qq -n -s weather in tokyo        # new conversation + web search
```

## Flags

| Flag | Description |
|------|-------------|
| `-n` | Start a new conversation |
| `-s` | Force a web search |


## Requirements

- Python 3.9+
- An Anthropic API key

## Installation

Clone the repository:

```bash
git clone https://github.com/YOURNAME/qq.git
cd qq
```

Make the script executable:

```bash
chmod +x qq
```

Move it somewhere on your PATH:

```bash
sudo cp qq /usr/local/bin/
```

Create your API key environment variable:

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
```

To make it permanent, add that line to your `~/.zshrc` or `~/.bashrc`.

Reload your shell:

```bash
source ~/.zshrc
```

## Optional shortcuts

Create these aliases:

```bash
alias qqn="qq -n"
alias qqs="qq -s"
```

Or create tiny wrapper scripts:

```bash
#!/bin/sh
exec qq -n "$@"
```

and

```bash
#!/bin/sh
exec qq -s "$@"
```

## Conversation history is stored in

```
~/.qq_history.json
```

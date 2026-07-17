# qq - a tiny terminal AI assistant with persistent conversation history.

By default, qq remembers previous messages so you can have an ongoing
conversation across commands. Use -n (or --new) to start a fresh chat, and
-s (or --search) to force a live web search for the current question.

If you use the optional wrapper scripts, qqn is equivalent to "qq -n" and
qqs is equivalent to "qq -s", so you don't need to type the flags manually.

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

## Examples

```bash
qq what is the capital of france
    qq "how do i undo my last git commit"
    qqs latest python release
    qqn explain recursion            # start a new conversation
    qq -n -s weather in tokyo        # new conversation + web search
```

## Flags

| Flag | Description |
|------|-------------|
| `-n` | Start a new conversation |
| `-s` | Force a web search |

Conversation history is stored in:

```
~/.qq_history.json
```

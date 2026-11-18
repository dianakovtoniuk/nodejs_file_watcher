# Node.js File Watcher

A small Node.js app that manages files through commands written to a text file. It watches `command.txt` for changes, reads the command, and runs it using the built-in `fs/promises` module.

## How it works

1. `app.js` opens `command.txt` and watches it with `fs.watch`.
2. When the file changes, the whole content is read into a buffer.
3. The text is parsed and the matching command is executed.

## Commands

| Command | Format |
| --- | --- |
| Create a file | `create a file <path>` |
| Delete a file | `delete the file <path>` |
| Rename a file | `rename the file <path> to <new-path>` |
| Add content to a file | `add to the file <path> this content: <content>` |

## Usage

```bash
node app.js
```

Then edit and save `command.txt`, for example:

```
create a file test.txt
```

## Status

- Creating files works.
- Parsing for delete, rename and add-to-file is in place, but the handlers are still stubs marked with `@TODO` and only log to the console.

## Requirements

- Node.js 14 or newer

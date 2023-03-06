# Filemanager Plugin

A simple plugin that allows for easy navigation of a file tree.

![Example picture](./example.jpg?raw=true "Example")

**Installation:** run `plugin install filemanager` and restart Micro.

## Basics

The top line always has the current directory's path to show you where you are.\
The `..` near the top is used to move back a directory, from your current position.

All directories have a `/` added to the end of it, and are syntax-highlighted as a `special` character.\
If the directory is expanded, there will be a `+` to the left of it. If it is collapsed there will be a `-` instead.

**NOTE:** If you change files without using the plugin, it can't know what you did. The only fix is to close and open the tree.

### Options

| Option                       | Purpose                                                      | Default |
| :--------------------------- | :----------------------------------------------------------- | :------ |
| `filemanager-showdotfiles`   | Show dotfiles (hidden if false)                              | `true`  |
| `filemanager-showignored`    | Show gitignore'd files (hidden if false)                     | `true`  |
| `filemanager-compressparent` | Collapse the parent dir when left is pressed on a child file | `true`  |
| `filemanager-foldersfirst`   | Sorts folders above any files                                | `true`  |
| `filemanager-openonstart`    | Automatically open the file tree when starting Micro         | `false` |

### Commands and Keybindings

The keybindings below are the equivalent to Micro's defaults, and not actually set by the plugin. If you've changed any of those keybindings, then that key is used instead.

If you want to [keybind](https://github.com/zyedidia/micro/blob/master/runtime/help/keybindings.md#rebinding-keys) any of the operations/commands, bind to the commands like `command:tree`.

| Command  | Keybinding(s)              | What it does                                                                                |
| :------- | :------------------------- | :------------------------------------------------------------------------------------------ |
| `tree`   | -                          | Open/close the tree                                                                         |
| -        | <kbd>Tab</kbd> & MouseLeft | Open a file, or go into the directory. Goes back a dir if on `..`                           |
| -        | <kbd>→</kbd>               | Expand directory in tree listing                                                            |
| -        | <kbd>←</kbd>               | Collapse directory listing                                                                  |
| -        | <kbd>Shift ⬆</kbd>         | Go to the target's parent directory                                                         |
| -        | <kbd>Alt Shift {</kbd>     | Jump to the previous directory in the view                                                  |
| -        | <kbd>Alt Shift }</kbd>     | Jump to the next directory in the view                                                      |
| `rm`     | -                          | Prompt to delete the target file/directory your cursor is on                                |
| `rename` | -                          | Rename the file/directory your cursor is on, using the passed name                          |
| `touch`  | -                          | Make a new file under/into the file/directory your cursor is on, using the passed name      |
| `mkdir`  | -                          | Make a new directory under/into the file/directory your cursor is on, using the passed name |

#### Notes

- `rename`, `touch`, and `mkdir` require a name to be passed when calling.\
  Example: `rename newnamehere`, `touch filenamehere`, `mkdir dirnamehere`.\
  If the passed name already exists in the current dir, it will cancel instead of overwriting (for safety).

- The <kbd>Ctrl w</kbd> keybinding is to switch which buffer your cursor is on.\
  This isn't specific to the plugin, it's just part of Micro, but many people seem to not know this.

# VS Code Text Editor

## Installation

[Download VS Code](https://code.visualstudio.com/Download).

## Basic Configuration

After you have downloaded VS Code, you'll want to take some time to familiarize yourself with its [settings](https://code.visualstudio.com/docs/getstarted/settings) and menus.

The Command Pallette (accessible by typing "shift + command + P") is perhaps the biggest time-saving tool, and is worth exploring.

### Shell Commands

On a Windows, you may not need to take any action. But on a Mac, follow [these steps](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line) to enable VS Code shell commands.

After enabling shell commands, you should be able to use the `code` command to open files and folders from the command-line:

```sh
# open all files and folders in the current working directory:
code .

# open all files and folders in the specified directory, e.g. "path/to/my-project":
code path/to/my-project
```


### Python Syntax Auto-completion

Once configured, the text editor is capable of automatically completing snippets of Python code for you. This helps improve accuracy, and saves time.

When you open a Python file in VS Code, it should prompt you to install the official Python extension (`ms-python.python`). You are recommended to install this extension to enable Python syntax auto-completion.

### Vertical Column Selection

If configured, your text editor can also enable vertical text selection. This comes in handy if you have to change multiple lines of text at the same time, including commenting-out many lines at once.

By default, you should be able to achieve column selection functionality in VS Code by pressing "shift + alt" (Windows) or "shift + option" (Mac), then clicking and dragging up or down.

![a screenshot of the text editor's column selection](https://user-images.githubusercontent.com/1328807/50870478-2e9b8400-1386-11e9-9378-0afadc4a7dce.gif)












<hr>


## Advanced Configuration

These are some of the author's personal VS Code configurations, for your reference. Feel free but not obligated to use them.



### Python Snippets

Use the command palette and start typing "snippets" to find the "Preferences > Configure User Snippets" setting which should yield a snippets JSON file. Feel free to update yours to include any of these helpful Python snippets:

```
{
	// Place your global snippets here. Each snippet is defined under a snippet name and has a scope, prefix, body and
	// description. Add comma separated ids of the languages where the snippet is applicable in the scope field. If scope
	// is left empty or omitted, the snippet gets applied to all languages. The prefix is what is
	// used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders.
	// Placeholders with the same ids are connected.
	// Example:
	// "Print to console": {
	// 	"scope": "javascript,typescript",
	// 	"prefix": "log",
	// 	"body": [
	// 		"console.log('$1');",
	// 		"$2"
	// 	],
	// 	"description": "Log output to console"
	// }

	"Python For Loop": {
		"prefix": ["for"],
		"body": [
			"for item in my_list:",
			"    print(item)"
		],
		"description": "A for loop in Python."
	},

	"Python Function Definition": {
		"prefix": ["def"],
		"body": [
			"def my_func():",
			"    pass"
		],
		"description": "A function definition in Python."
	},

	"Python Class Constructor": {
		"prefix": ["init", "__init", "defi"],
		"body": [
			"def __init__(self):",
			"    pass"
		],
		"description": "A class initializer method for Python."
	},

	"Python Try Block": {
		"prefix": ["try"],
		"body": [
			"try:",
			"    pass",
			"except Exception as err:",
			"    print('OOPS', err)"
		],
		"description": "A try block for error-handling in Python. Try to use the specific error class if you know it, instead of Exception."
	},

	"Python Main Conditional": {
		"scope": "python",
		"prefix": ["main", "__main"],
		"body": [
			"if __name__ == '__main__':",
			"    pass"
		],
		"description": "The main conditional for Python."
	}
}
```

See also: https://code.visualstudio.com/docs/editor/userdefinedsnippets





### Recommended Extensions

Here is a sample of the authors's installed extensions (results from running `code --list-extensions`):

 + `mechatroner.rainbow-csv`
 + `mikestead.dotenv`
 + `ms-python.python`
 + `sleistner.vscode-fileutils`
 + `streetsidesoftware.code-spell-checker`
 + `whizkydee.material-palenight-theme`
 + `xamm.filepath`
 + `yzhang.markdown-all-in-one`

You might try searching these manually or [importing them programmatically](https://stackoverflow.com/a/49398449/670433) via `code --install-extension EXTENSION_NAME`, where "EXTENSION_NAME" is the extension's identifier (e.g. `code --install-extension ms-python.python`).


### Recommended User Settings

Use the command palette and start typing "settings" to find the "Preferences > Open Settings (JSON)" setting which should yield a snippets JSON file. Feel free to update yours to include any of these settings overrides:

```json
{
  "workbench.colorTheme": "Palenight Theme",
  "editor.fontSize": 14,
  "editor.tabSize": 4,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "files.trimFinalNewlines": true,
  "telemetry.telemetryLevel": "off",
}
```


### Recommended Keyboard Shortcuts

Use the command palette and start typing "shortcuts" to find the "Preferences > Open Keyboard Shortcuts (JSON)" setting which should yield a snippets JSON file. Feel free to update yours to include any of these keyboard shortcut overrides:

```json
// Place your key bindings in this file to override the defaults
[
    {
        "key": "cmd+\\",
        "command": "workbench.action.toggleSidebarVisibility"
    },
    {
        "key": "cmd+b",
        "command": "-workbench.action.toggleSidebarVisibility"
    },
    {
        "key": "shift+cmd+d",
        "command": "editor.action.duplicateSelection"
    },
    {
        "key": "cmd+t",
        "command": "workbench.action.quickOpen"
    },
    {
        "key": "ctrl+shift+m",
        "command": "markdown-preview-enhanced.openPreview",
        "when": "editorLangId == 'markdown'"
    },
]

```

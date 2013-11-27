# QtConsole widget

The QtConsole class is a custom widget that implements a basic console, completely written in C++ and relying on Qt 5. It implements several features and is intended to be inherited from in order to have a "real" console for a specific scripting language, shell, etc... The class relies as much as possible on the features offered by QTextEdit (from which it inherits) and this implied a very simple and light code.

## Features

- QConsole is a custom widget that can be easily integrated in any interface.
    It is able to execute any command (implementated in child classes) and then displays its result in blue or red whether it has failed or not. It also displays the stdout/stderr output produced by these commands with the same colorization schema.

- QConsole supports multi-line commands. In fact, when an incomplete command (e.g., unclosed braces) is validated, the cursor is set at the beginning of a new line.

- QConsole supports specifying a different prompt.

- Navigation:

	- Left and right keys to move the cursor in the edition zone (from the prompt to the end of the paragraph plus all the extra lines in multi-line command mode).

    - Associated with the shift key, selection is then possible.

    - Associated with ctrl key, the cursor is moved between the words.

    - Ctrl and shift keys can be used together.

    - If not in multi-line mode, up and down keys permit the user to navigate in the commands' history as with advanced shells, otherwise they permit to navigate in the edition zone.

    - Home and end keys allow moving the cursor respectively just after the prompt and at the end of the current line.

    - Associated with the shift key, selection is then possible.

- Edition:

  - Simple key strokes work as expected and the 'enter' will place the command into the history list, validate it and 'execute' it giving us back the result (this is in case the command is complete, otherwise the cursor will move to a new line).

  - Pressing Ctrl + C key sequence will cancel the current command and shows the prompt again.

  - Pressing the Tab key will try to autocomplete the current command. If there are many possibilities, they should be all shown.

  - The Delete and Backspace keys will delete selected text or simply one character in the limits of the edition zone. The ctrl key can be associated with them to delete whole words.

  - Copy & Paste are always enabled, but Cut is only possible in the edition zone.
  
- Mouse usage:

  - If the cursor is not placed in the edition zone, its position is undone.

  - Selection using the mouse is possible everywhere.


## AUTHORS:

 - Houssem BDIOUI   (houssem.bdioui@gmail.com)
 - Mondrian NUESSLE (nuessle@uni-mannheim.de)
 - Ulrich Ring
 - YoungTaek Oh (youngtaek.oh@gmail.com)
 - Igor Malinovskiy (u.glide@gmail.com)
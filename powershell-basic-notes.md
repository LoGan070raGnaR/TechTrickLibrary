# PowerShell Notes

## Introduction
- PowerShell is a command-line shell and scripting language developed by Microsoft.
- It differs from other shells like C Shell(csh), Bash, and KornShell(ksh) in that it primarily works with objects, not just text.
- PowerShell is built on the .NET Framework or .NET Core, depending on the version, and it utilizes the .NET runtime. It leverages various .NET libraries and APIs for its functionality.
- While PowerShell may utilize components written in C# and other .NET languages, it is not primarily built using C#. Instead, it is predominantly developed using a combination of C++, C#, and other technologies.
## Opening PowerShell
- Open PowerShell by typing `powershell` in the search bar and pressing `Ctrl+Shift+Enter` to run it with administrative privileges.

## Directory Navigation
- The `cd` command is used to change the current directory.
- `.` represents the current directory.
- `..` represents the parent directory.
- The `dir` or `ls` command is used to list the contents of the current directory.
- Absolute paths start from the root directory, while relative paths start from the current directory.

## Cmdlets and Aliases
- In PowerShell, everything is a cmdlet (command-let).
- A cmdlet follows the "Verb-Noun" naming convention, although there may be exceptions.
- Cmdlets are not case-sensitive.
- Examples of cmdlets: `Get-ChildItem`, `Select-Object`.
- `dir` and `ls` are aliases for the `Get-ChildItem` cmdlet.
- Use the `Get-Alias` cmdlet to list all aliases.

## Output and Objects
- PowerShell displays command output in a tabular format with multiple columns.
- PowerShell works with objects, not just text.
- Piping (`|`) is used to send objects from one command to another.
- The `Select-Object` cmdlet is used to select specific properties of an object.
  - Example: `Get-ChildItem | Select-Object Name`.
  - Additional parameters: `-First`, `-Last`, `-Index`.
- The `Get-Member` cmdlet is used to explore the properties and methods of an object.
  - Example: `Get-ChildItem | Select-Object -Index 0 | Get-Member`.

## Clearing the Console
- Use `Ctrl+L`, `cls`, or `clear` to clear the console.

## Help and Documentation
- PowerShell provides extensive help and documentation.
- Use the `Get-Help` cmdlet to get help on a cmdlet or topic.
  - Example: `Get-Help Select-Object`.
- The command `Get-Help *keyword*` can be used to search for cmdlets or topics containing a specific keyword.
- The `Get-Help *cmdlet* -Full` command displays detailed help for a cmdlet.
- The `Get-Command` cmdlet lists all available cmdlets.

## Conclusion
These notes cover the basic concepts and commands of PowerShell, including opening PowerShell, directory navigation, syntax, output formatting, piping, selecting objects, exploring object properties, and accessing help and documentation.

---
# PowerShell: Output and File Operations

In this guide, we will cover various aspects of PowerShell related to output and file operations. We'll explore how to open PowerShell, format output using commands like `Get-ChildItem`, `Get-Alias`, different output options, standard output, grid view, and performing file operations such as removing files and directories.

## Opening PowerShell and File Operations

- To open PowerShell, execute the command `powershell` in the command prompt or search bar.

- The `Get-ChildItem` cmdlet lists the contents of a directory.
  - Use `./` for relative path and starting with `/` for absolute path.
  - Example: `Get-ChildItem`.

## Formatting Output

- The `Format-Table` cmdlet formats output in a tabular view.
  - Example: `Get-ChildItem | Format-Table`.

- The `Format-Wide` cmdlet formats output in a wide view.
  - Example: `Get-ChildItem | Format-Wide` or `Get-ChildItem | fw`.

- The `Format-List` cmdlet formats output as a list.
  - Example: `Get-ChildItem | Format-List *` or `Get-ChildItem | fl *`.

## Working with Aliases and Output Control

- Aliases provide shorthand commands for cmdlets.
- Use `Get-Alias` (alias: `gal`) to list all aliases.
- Example: `gal echo` shows that `echo` is an alias for `Write-Output`.
- Output control allows customization of how PowerShell displays results.

- The `Out-Host` cmdlet sends output to the host for display.
  - Example: `Get-ChildItem | Out-Host`.

- The `Out-String` cmdlet converts output to a string.
  - Example: `Get-ChildItem | Out-String`.

- The `Out-Null` cmdlet discards output.
  - Example: `Get-ChildItem | Out-Null`.

- The `Out-File` cmdlet sends output to a file.
  - Example: `Get-ChildItem | Out-File .\directory.txt`.

- The `>` redirection operator sends output to a file.
  - Example: `Get-ChildItem > directory.txt`.

## Viewing and Manipulating Files

- Use `Get-Content` to view the content of a file.
  - Example: `Get-Content .\directory.txt`.

- Open a file in Notepad:
  - Example: `notepad.exe .\directory.txt`.

## Output Formatting Options

- The `Out-GridView` cmdlet opens a graphical interface to filter and explore output.
  - Example: `Get-ChildItem | Out-GridView`.

## File Operations

- The `Move-Item` cmdlet moves a file or directory.
  - Example: `Move-Item .\directory.txt .\Desktop\` (move to Desktop).

- To move up in the file system, use `..` to refer to the parent directory.

- The `Remove-Item` cmdlet deletes a file or directory.
  - Example: `Remove-Item .\directory.txt`.

- Use `Remove-Item` (alias: `rm` or `del`) to delete a directory.
  - Example: `Remove-Item '.\Saved Games'`.

- Adding the `-Confirm` parameter prompts for confirmation before deleting.
  - Example: `Remove-Item '.\Saved Games' -Confirm`.

- Adding the `-Recurse` parameter deletes a directory and its contents recursively.
  - Example: `Remove-Item '.\Saved Games' -Recurse`.

## Conclusion
These notes cover various aspects of PowerShell output formatting, file operations, and directory management. It's important to understand how PowerShell is invoked and the host environment to fully utilize its capabilities. Output control allows us to tailor our working experience and view data in different ways.


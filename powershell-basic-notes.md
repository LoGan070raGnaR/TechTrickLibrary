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


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

---

# PowerShell: Profiles & Execution Policies

In this section, we will cover the PowerShell profiles, execution policies, and how they affect script execution.

## Introduction to Profiles
- PowerShell profiles are script files that run automatically when PowerShell starts.
- Profiles can be customized for individual users or all users on a system.
- The location of profile files can vary, but they are typically found in default locations.
- Variables in PowerShell are denoted with a `$` prefix.

## Checking Profiles
- `$profile` shows the location of the current user's profile.
- To view the profile file, run `notepad $profile`.
- Other users' profiles can be accessed by using `$profile | Select-Object *`.
- If the profile file doesn't exist, use `Get-Content $profile` to create it.

## Creating and Removing Directories
- Use `New-Item -ItemType Directory dummy` to create a directory.
- Alternatively, `md` is an alias for `mkdir` to create a directory.
- To remove a directory, use `rmdir .\dummy`.

## PowerShell Profile
- Create a profile by opening the profile file with `notepad "file path\PowerShell_profile.ps1"`.
- Customize the profile by adding commands such as `Get-Date`, `Import-Module PSGit`, or `Import-Module PSColor`.
- The profile is similar to bash or cshell profiles in Linux.

## Execution Policies
- Execution policies determine the security level of script execution in PowerShell.
- Run `Get-Help about_Execution_Policies` for more information on execution policies.
- Update help by running `Update-Help` as an administrator.

## Checking Execution Policies
- Run `Get-ExecutionPolicy -List` to see the list of execution policies.
- Use `Get-ExecutionPolicy` to check the current execution policy.
- The default policy is usually `Restricted`, which prevents script execution.

## Changing Execution Policies
- Change the execution policy with `Set-ExecutionPolicy RemoteSigned` to allow signed scripts to run.
- Run `Get-ExecutionPolicy` again to verify the updated policy.

## Running Scripts with Profiles
- Open a new PowerShell window to see the effects of the created profile.
- If you encounter an error stating that running scripts is disabled, it means the profile wasn't loaded.
- Execution policies control whether scripts can be run or not.

## Modifying Profiles
- Use `notepad $profile` to edit the profile file.
- To remove the profile, delete its contents.

These notes cover the PowerShell profiles and execution policies. Profiles allow customizations to the PowerShell environment, while execution policies control script execution. Understanding profiles and execution policies is essential for managing and running scripts in PowerShell.

---

# PowerShell: Variables, Types & PSDrives

In this section, we will cover variables, data types, and PSDrives in PowerShell.

## Variables
Variables in PowerShell are used to store and manipulate data. They are denoted with the `$` prefix. Here are some key points about variables:

- To create a variable, use the format `$variableName = value`. For example, `$anything = "any text or anything"` creates a variable named `$anything` and assigns it the value `"any text or anything"`.
- Variables can hold different types of data, such as text, numbers, or objects.
- You can display the value of a variable using `Write-Host $variableName`. For example, `Write-Host $anything` will display `"any text or anything"`.
- If you try to display a variable that doesn't exist, PowerShell will not display anything.

## Data Types
In PowerShell, variables have types associated with them. Understanding the data types is essential for working with variables effectively. Here are some important details:

- PowerShell is object-oriented, and variables can store different types of data, such as strings, integers, floats, arrays, or custom objects.
- To determine the type of a variable, you can use the `GetType()` method. For example, `$variable.GetType()` retrieves the type information of the variable.
- Using `$variable.GetType() | fl *`, you can display all properties and methods associated with the type.
- PowerShell provides a variety of data types, and you can explore them further by referring to resources such as "ss64.com".

### Examples
Let's look at some examples to understand variables and data types in PowerShell:

- `$anything.GetType()` displays the type of the `$anything` variable, helping you understand the underlying data type of the value stored in the variable.
- `(Get-Process | Select -First 1).GetType()` retrieves the type of a process object obtained using the `Get-Process` cmdlet.
- `(Get-Process | Select -First 1).GetType().FullName` shows the fully qualified name of the type associated with the process object.
- PowerShell allows you to create objects of specific types. For example, `[IPAddress]"10.0.0.1"` creates an IP address object, and `[MailAddress]"john@gmail.com"` creates a mail address object.
- When you try to assign an invalid value, such as `[IPAddress]"256.0.0.1"`, PowerShell returns an error indicating that it is not a valid IP address.

## PSDrives
PowerShell provides a concept called PSDrives, which allow you to navigate various data stores in a consistent manner. Here's what you need to know:

- PSDrives provide a consistent way to interact with different data stores, including file systems, registry hives, certificates, and more.
- Use `Get-PSDrive` to display all available PSDrives. It shows a list of logical drives and their associated providers.
- For example, you can navigate to the `Variable` PSDrive using `cd Variable:` and then use `Get-ChildItem` to explore and manage variables.
- The `Env` drive represents environment variables. You can navigate to it using `cd Env:` and then use `Get-ChildItem` (`ls`) to list the available environment variables.
- To access a specific environment variable, use the format `$env:VariableName`. For example, `$env:windir` displays the value of the `windir` environment variable.

These examples cover working with variables, data types, and PSDrives in PowerShell. Understanding variables and data types is crucial for manipulating and interacting with different types of data in PowerShell.

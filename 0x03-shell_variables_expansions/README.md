Shell, init files, variables and expansions

# Q1) crating allias- ->  alias ls='rm *' n.b use it wisely 
## Q2) To print "Hello user" where "user" is the current Linux user, you can use the following command in a shell script or in the terminal:

```bash
echo "Hello $(whoami)"
```
''''other example
echo "hello $USER"
'''''

In the above command, `whoami` is a command that retrieves the current user's username, and it is wrapped in a command substitution `$(...)` within the `echo` command. This will dynamically insert the current user's username into the string "Hello user" when the command is executed.

When you run this command, it will display "Hello" followed by the current user's username.

### Q3)Certainly! Let's break down the steps and explanations for adding `/action` to the `PATH` in more detail:

1. Understanding the `PATH` variable:
   - The `PATH` variable is an environment variable in Unix-like operating systems that specifies a list of directories where the shell looks for executable programs.
   - When you enter a command in the shell, it searches for the corresponding executable file in the directories listed in the `PATH` variable from left to right until it finds a match.

2. Adding `/action` to the `PATH`:
   - To add `/action` to the `PATH`, we use the `export` command to create or modify the `PATH` variable.
   - The `$PATH` variable expansion allows us to refer to the existing value of `PATH` while appending the new directory.
   - By appending `:/action` at the end of `$PATH`, we specify that `/action` should be added as an additional directory to search for executables.

3. Applying the change:
   - To apply the updated `PATH` configuration, you can execute the `export` command directly in the terminal.
   - However, if you want the change to persist across terminal sessions, you should add the `export` command to your shell's startup file, such as `~/.bashrc` for Bash.
   - Editing the `~/.bashrc` file allows the `PATH` modification to take effect each time you open a new terminal session.

Here's a summary of the command to add `/action` to the `PATH`:

```bash
export PATH=$PATH:/action
```

Remember to replace `/action` with the actual directory you want to add.

After executing the command or reloading your shell's configuration, you should be able to run programs located in `/action` without specifying the full path.

#### Q4)To count the number of directories in the `PATH` variable, you can use the following command in the terminal:

```bash
echo $PATH | tr ':' '\n' | wc -l
```

Let's break down the command:

1. `echo $PATH`: Prints the value of the `PATH` variable.
2. `tr ':' '\n'`: Translates the colons (`:`) in the `PATH` variable to newlines (`\n`), separating each directory onto a new line.
3. `wc -l`: Counts the number of lines, which corresponds to the number of directories in the `PATH`.

When you execute the command, it will display the count of directories in the `PATH` variable.

Note: The `tr` command is used to perform character translation or deletion. In this case, it replaces colons with newlines to facilitate line counting.

##### Q5)To list environment variables in Unix-like systems (e.g., Linux, macOS), you can use the `env` command or `printenv` command. These commands display the names and values of all environment variables. Here's how you can use them:

Using the `env` command:
```bash
env
```

Using the `printenv` command:
```bash
printenv
```

Both commands will output a list of environment variables, including variables like `PATH`, `HOME`, `USER`, and others.

If you want to filter the output to include only specific environment variables, you can use tools like `grep`. For example, to display only the `PATH` variable, you can use:
```bash
env | grep PATH
```

The above command will show the value of the `PATH` variable.

# Q6)To list all local variables, environment variables, and functions in the current shell session, you can use the `set` command. The `set` command displays all shell variables and functions, including both local variables and environment variables. Here's how you can use it:

```bash
set
```

Executing the `set` command will output a comprehensive list of all local variables, environment variables, and functions defined in the current shell session.

## Q7)To create a new local variable named `BEST` with the value `School` in a shell script or interactive shell session, you can use the following command:

```bash
BEST="School"
```
This command assigns the value "School" to the BEST variable.

### Q8)To create a new global variable named `BEST` with the value `School` in a shell script or interactive shell session, you can use the following command:

```bash
export BEST="School"
```

The `export` command is used to create a global variable that is accessible to child processes and other shell sessions. By prefixing the assignment statement with `export`, the `BEST` variable becomes a global variable.

#### Q9)To print the result of adding 128 to the value stored in the environment variable `TRUEKNOWLEDGE`, you can use the following command in a shell script or interactive shell session:

```bash
echo $((128 + $TRUEKNOWLEDGE))
```

This command uses the arithmetic expansion feature `$((...))` to perform the addition. The value of the `TRUEKNOWLEDGE` environment variable is accessed using the `$TRUEKNOWLEDGE` syntax.

Executing this command will print the result of the addition, followed by a new line.

Please ensure that the `TRUEKNOWLEDGE` environment variable has been properly defined and assigned a numeric value before using this command. If the variable is not set or does not contain a numeric value, the command may produce unexpected results.

##### Q10)You can use the `$((...))` syntax for performing arithmetic operations in shell scripting. Here's the correct command to print the result of dividing the value of `POWER` by the value of `DIVIDE`, followed by a new line:

```bash
echo $((POWER / DIVIDE))
```

The `$((...))` syntax is used for arithmetic expansion in shell scripting. Within the double parentheses, you can perform mathematical calculations, including addition, subtraction, multiplication, and division. In this case, the expression `POWER / DIVIDE` will be evaluated, and the result will be printed using the `echo` command.

Please ensure that the variables `POWER` and `DIVIDE` have been properly defined and contain valid numeric values before using this command. If any of the variables are not set or do not contain numeric values, the arithmetic operation may produce unexpected results or errors.


# Q11) The correct syntax to raise a value to a power in shell scripting is `**`. Here's the correct command to display the result of raising the value of the `BREATH` environment variable to the power of the `LOVE` environment variable, followed by a new line:

```bash
echo $((BREATH ** LOVE))
```

The `$((...))` syntax is used for arithmetic expansion in shell scripting. Within the double parentheses, you can perform mathematical calculations, including exponentiation using the `**` operator. In this case, the expression `BREATH ** LOVE` will be evaluated, and the result will be printed using the `echo` command.

Please ensure that the variables `BREATH` and `LOVE` have been properly defined and contain valid numeric values before using this command. If any of the variables are not set or do not contain numeric values, the arithmetic operation may produce unexpected results or errors.

## Q12)You can use the `echo` command with the arithmetic expansion syntax to convert a binary number stored in the environment variable `BINARY` to base 10. Here's the modified command:

```bash
echo "$((2#$BINARY))"
```

In this command, the `2#` prefix before the `$BINARY` variable tells the shell to interpret the value of `$BINARY` as a number in base 2 (binary). The arithmetic expansion `"$((...))"` then performs the conversion from base 2 to base 10.

Make sure to replace `"$BINARY"` with the appropriate variable or value that holds the binary number you want to convert. When you run this command, it will output the decimal (base 10) equivalent of the binary number.


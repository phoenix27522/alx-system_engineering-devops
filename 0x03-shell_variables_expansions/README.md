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



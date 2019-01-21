# C_Template

   **_cproj_** is a simple bash script that creates a c project template (.c file and a makefile with a .clang-format file, used to style the code)

# Instalation
- Give the script execution permisions (if it doesn't have them)
` `
- Move the script into /usr/local/bin or ~/bin
    - `sudo cp cproj /usr/local/bin` - any user can use the script
    - `cp cproj ~/bin` - only the current user can use it
    - if you haven't added the ~/bin directory to PATH (or it doesn't exist): 
        1. `cd ~`
        2. `mkdir bin`
        3. `echo "PATH=/home/$USER/bin:$PATH" >> ~/.bashrc` - add the folder to path
        4. `source ~/.bashrc` - to reload the terminal

Now you should run the command from anywhere, using the `cproj` command from the terminal


# Run arguments
- The script can use up to 3 arguments
    1. Source name
    2. Executable name
    3. Archive name
- All 3 of them should not include an extension (because it will be changed anyway)

#### No arguments used
- the source, executable and archive names will be equal to the working directory's name
```bash
user@workstation:~/Project$ cproj
Project.c
Project
Project.zip
```

#### 1 argument used
- the source and executable name will be the one specified, the archive name will be equal to the working directory name
```bash
user@workstation:~/Project$ cproj main
main.c
main
Project.zip
```

#### 2 arguments used
- the source and archive name will be equal to the first argument, the executable name will be
the second argument
```bash
user@workstation:~/Project$ cproj main exe
main.c
exe
main.zip
```

#### 3 or more arguments used
- the source name will be the first argument, the executable will be the second, and the archive name will be the 3rd. All other arguments will be ignored
```bash
user@workstation:~/Project$ cproj main exe archive
main.c
exe
archive.zip
```

# Makefile commands

- **build** - compiles the program
- **run** - compiles and executes the program
- **pack** - creates an archive with all source files (*.c & *.h), README file and the Makefile
- **clean** - deletes the executable
- **beauty** - styles the code, using the google standard (except the indentation, 4 spaces instead of 2)

© 2019 Grama Nicolae

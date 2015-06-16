# How to create a "Hello World" project #

## Step 1 ##

Edit the config.sh file as example:

```
export PROJECT_NAME="Hello world"
export SHORT_NAME="hello"
export PROJECT_VERSION="1.000"
export CONFIG_PATH="/etc"

# Your project configuration file
export CONFIG_FILE="./conf/project.conf"

# Default log file, if you don't want it just use /dev/null
export LOG_FILE="/dev/null"

# Your project application path
export APP_DEFAULT_DIR=$(pwd)
```
Do not erase the following others lines that doesn't appear here!

## Step 2 ##
Write the code in hello.sh as example:
```
#!/bin/bash
source config.sh
init;
print_msg "Hello World!";
finish 0;
```

#ListFunctions List of all functions
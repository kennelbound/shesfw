# Examples #

## Cleaning directory ##
```
#!/bin/bash
source config.sh
init;

if [ ! "$1" ]; then
        print_error "No argument" exit
fi

NUMBER_OF_FILES="$(ls -l $1 | wc -l)"

rm -rf "$1"/* &

{ FILES_REMAINS="$(ls -l $1/ | wc -l)";
        while [ "$FILES_REMAINS" -gt 1 ];
                do echo $((FILES_REMAINS/$((NUMBER_OF_FILES/100))));
                FILES_REMAINS="$(ls -l $1/ | wc -l)";
done } | progress
print_msg "Ok!"

finish 0;
```
# Things you should never do #

There are usual Shell programs that we always use. Try to do as bellow

### Print Message ###

  * What you **shouldn't** do
```
echo "nononononon"
```
  * What you **should** do
```
print_msg "nononononon"
```
  * Why?
> > The print\_msg function provides several interfaces.

### Temporary File ###

  * What you **shouldn't** do
```
find / -name "nonon" >> /tmp/temporary_file
```
  * What you **should** do
```
find / -name "nonon" >> $TEMP_DIR/temporary_file
```
  * Why?
> > The $TEMP\_DIR is allocated on init and removed on program finish. So it don't create garbage.

### Writing to log file ###

  * What you **shouldn't** do
```
echo "Failed the function X" >> /var/log/project.log
```
  * What you **should** do
```
write_log "Failed the function X"
```
  * Why?
> > You can change the log file with 2 seconds using the write\_log.
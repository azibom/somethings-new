# somethings-new
how make your own command


### make sh file on commands folder in home
```
touch commands.sh
```
### and then copy this on it
```
function hi() {
    echo hi $(whoami)
}


function sortFiles() {
for file in *
do
    # checks if it is a file (skip directories)
    [ -f "$file" ] || continue
    # store the file name in filename
     filename="${file%.*}"
    # give the extension of the file
    ext="${file##*.}"
    # give the file name without its extension
    dir="${file%.*}"
    # create the directory
    [ ! -d $ext ] && mkdir $ext
    # move file to directory
    mv $filename.$ext $ext/
done

echo "successfuly sorted"
}
```
### now add this in .zhrc (because i use zsh)
```
source ~/commands/commands.sh
```

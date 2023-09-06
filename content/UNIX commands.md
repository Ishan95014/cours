In [[UNIX]] compliant systems, these generic commands should work.

Modern systems store files in [[folders]], and usually expose these to the user through a [[file explorer program]]. 

(screenshot file explorer, finder) 

But if you are on a [[headless system]], such as a [[server]] or to be faster, you can manage your files directly from the [[command line]]. 

## Find the folder you are in
```
pwd 
```

## List the files in the folder 
```
ls 
```
Sample output :
```
comptabilite.doc images bonjour 
```

## Rename a file
```
mv originalFileName newFileName
```

## Move a file
```
mv fileNameAndLocation newFileNameAndLocation
```
Remember UNIX works according to where you are : Suppose you are in your website folder, `site`, and want to move index.html to `/var/www`

```
.
├─ docs/
│  └─ index.md
└─ mkdocs.yml
```

```
mv index.html /var/www
```


## script
```
```

## exit
```
```
## clear
```
```
## alias
```
```
## who 
```
```
## id
```
```
## pwd
```
```
## cd 
Move within the folder structure
```
cd /some/place
```
## ls
List the files and folders in the current folder
```
ls
```
## touch
```
```
## cp
```
```

## mv
Rename a directory
```
mv dir newDir
```
Move (cut & paste) a file or directory to a new location
````
mv /start/adress/file /new/adress/file
mv /start/adress/folder /new/adress/folder
````
## rm
remove file
```
rm file
```
remove folder 
````
rm -r folder
````
(`-r` means *recursive* and deletes all subfiles and folders)

## mkdir
Create a new folder or directory
```
mkdir newDirectory
```
## tee
```
```
## ln
```
```
## chown
```
```
## chmod
```
```
## cat
```
```

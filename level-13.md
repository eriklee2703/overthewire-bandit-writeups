# Level 12 -> Level 13
## Objective:
Locate the password stored in data.txt file, which is a hexdump of a file that has been repeatedly compressed. Create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv.
## Key Concepts & Commands:
- `mktemp -d`: Creates a temporary directory inside the `/tmp` folder.
- `cp`: Duplicates a file into another folder.
- `mv`: Renames a file.
- `file`: Indentifies the file format.
- `gunzip`: Decompresses `gzip` files
- `bunzip2`: Decompresses `bzip2` files.
- `tar -x -v -f`: Extracts a specified archrived file and shows the execution. 
- `xxd -r`: Reverses a hexadecimal file.

## Investigation & Troubleshooting 
- Started this level by creating a temporary directory using `mktemp -d` to extract files without modifying the original file.
- Copied the `data.txt` from the home directory into the new temporary directory.

```bash
bandit12@bandit:/tmp/tmp.x9ujiycPp5$ cp ~/data.txt .
```
- The file contained a hexadecimal dump, so used xxd -r which converts a hexadecimal file back to a binary file.

```bash
bandit12@bandit:/tmp/tmp.x9ujiycPp5$ xxd -r data1.txt > data2.txt
```
- From this stage, performed several layers of decompressing, file renaming, and file checking till eventually reached a file in ASCII text.



## Lessons Learned
I learned how to use `grep` to search through a file for specific words or patterns. Unlike the `find` command which is used to search for files or directories based on a specified criteria, `grep` searches at a more granular level inside of a file. This is especially useful in situations when manually searching in a file would be impractical.

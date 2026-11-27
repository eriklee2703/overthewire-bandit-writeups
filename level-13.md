# Level 12 -> Level 13
## Objective:
Locate the password stored in data.txt file, which is a hexadecimal dump of a file that has been repeatedly compressed. Create a directory under /tmp to work in, preferably using the `mktemp -d` command. Then copy the data file using `cp`, and rename it using `mv`.
## Key Concepts & Commands:
- `mktemp -d`: Creates a temporary directory inside the `/tmp` folder.
- `cp`: Copies a file into another directory.
- `mv`: Renames a file.
- `file`: Identifies the file type.
- `gunzip`: Decompresses `gzip` files.
- `bunzip2`: Decompresses `bzip2` files.
- `tar -x -v -f`: Extracts a specified archive. The `-x` option extracts, `-v` displays the names of extracted files, and `-f` specifies the archive filename.
- `xxd -r`: Reverses a hexadecimal dump and reconstructs the original binary data.

## Investigation & Troubleshooting 
- Started this level by creating a temporary directory using `mktemp -d` to extract files without modifying the original file.
- Copied `data.txt` from the home directory into the new temporary directory.

```bash
bandit12@bandit:/tmp/tmp.x9ujiycPp5$ cp ~/data.txt .
```
- The file contained a hexadecimal dump, so used xxd -r to reverse a hexadecimal file back to a binary file.

```bash
bandit12@bandit:/tmp/tmp.x9ujiycPp5$ xxd -r data.txt > data.bin
```
- From this stage, several layers of decompressing and extraction were required to reach the target file.
- Used the `file` command to identify the format of each file and determine which decompressing utility was appropriate.
- For `bzip2` and `gzip` files, renaming the file to the appropriate extension (`.gz` or `.bz2`) was necessary in order to properly extract the file.

`Gzip`: Renamed the file with a `.gz` extension and then used `gunzip` to decompress `gzip`-compressed files.

```bash
file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Oct 25 13:37:03 2026, max compression, from Unix, original size modulo 2^32 49
mv data8.bin data8.gz
gunzip data8.gz
```
`Bzip2`: Renamed the file with a `.bz2` extension and then used `bunzip2` to decompress `bzip2`-compressed files.

```bash
file data2
bin: bzip2 compressed data, block size = 900k
mv data2 data3.bz2
bunzip2 data3.bz2
```
- `TAR`: Used `tar -xvf` to extract archived files. Renaming the archive was not necessary.

```bash
file data4
data4: POSIX tar archive (GNU)
tar -xvf data4

```
- Repeated this process through multiple layers of compression and archiving, using `file` to identify each format. Eventually, I reached the final layer which was identified in ASCII text. The file displayed the password needed to move to the next level.


## Lessons Learned
I learned how to create a temporary directory, copy files, and rename them. I dealt with different kinds of decompression utilities and learned to identify different file formats.

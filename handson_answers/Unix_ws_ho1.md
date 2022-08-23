# Introduction to Unix - MiCM summer 2022

## Excersice 1 answers

1. Create a directory called folder1 under data/ho12.

```{bash}
mkdir data/ho12/folder1
```

2. Access the directory you just created
~~~{}
cd data/ho12/folder1
~~~
3. Create two files:  f1.txt and .f2.txt
~~~{}
touch f1.txt
touch .f2.txt
~~~
4. Write the numbers from 1 to 10 in f1.txt (one number per line)
~~~{bash}
# option 1 - write down the numbers inside the text editor
nano f1.txt

# option 2 (not very recommended as it is error prone)
echo -e "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n" > f1.txt 
~~~
5. Write the following sequence in .f2.txt (one letter per line) 
* a a b b b c c c c d d d d d
~~~{bash}
# option 1 - write down the seq inside the text editor
nano .f2.txt

# option 2 (not very recommended as it is error prone)
echo -e "a\na\nb\nb\nb\nc\nc\nc\nc\nd\nd\nd\nd\nd\n" > .f2.txt
 
~~~
6. List all the contents of the directory (including .f2.txt) –hint look at the manual of ls
~~~{}
ls -a
~~~
7. Change the name of .f2.txt to f2.txt
~~~{}
mv .f2.txt f2.txt
~~~
8. Change the permissions of f1.txt so that only the user can read and write the file
```{}
# one option - rewrite all of the permissions
chmod u+rw,go-rw f1.txt
# or
chmod 700 f1.txt

# another option - just remove the ones that are not useful
chmod go-rwx f1.txt
```
9. Write the first 10 lines of f1.txt and all the lines in f2.txt to a new file f3.txt
```{}
head -10 f1.txt | cat f2.txt > f3.txt
```
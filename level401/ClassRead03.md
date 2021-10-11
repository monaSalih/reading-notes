# Read & Write Files in Python

![r\w](https://files.realpython.com/media/Reading-and-Writing-Files-in-Python_Watermarked.0d394921fd90.jpg)

> When you’re working with Python, you don’t need to import a library in order to read and write to a file. It’s handled natively in the language, albeit in a unique manner.

# What Is a File?
\Files are named locations on disk to store related information. They are used to permanently store data in a non-volatile memory.

The file main parts:

![fileCon](https://files.realpython.com/media/FileFormat.02335d06829d.png)

Header: information of the file content (file name, size, type, and so on)
Data: represent the data programmer write it in order to do specific thing.
End of file (EOF): use special character to refere to file end.

# file Path

The file path is a string that represents the location of a file. It’s broken up into three major parts.

Folder Path:  The file folder location where the next folder is separated by its own slash or backslash.

File Name: the actual name of the file 

Extension: The end of a file path is preceded with a period which indicates the type of file that it contains.

for example you have following file structure for file located:
```
/
│
├── path/
|   │
│   ├── to/
│   │   └── cats.gif
│   │
│   └── dog_breeds.txt
|
└── animals.csv
```
# Examples
🚗 in order to access the **cats.gif** and your current location **path** you need to go to **path folder** next go **to folder** and finally 🎉 you arrive to **cats.gif**
Following full path,File Name, File Extension.
```
path/to/cats.gif
cats:File Name 
.gif:File Extension
```

🚗 in order to access the **dog_breeds.txt** use **double-dot..** to get back one step and the path will be **../dog_breeds.txt** .form directory we will reference the **dog_breeds.txt file**

```
/
│
├── path/  ← Referencing this parent folder
|   │
|   ├── to/  ← Current working directory (cwd)
|   │   └── cats.gif
|   │
|   └── dog_breeds.txt  ← Accessing this file
|
└── animals.csv
```
# Line Endings
The string used to separate (or, rather, terminate) lines on the current platform.

### New line:
![newL](https://www.freecodecamp.org/news/content/images/2020/06/New-Line.png)

>Windows uses the CR+LF
> Unix and the newer Mac versions use LF 

In following example, let’s say that we want to inspect the file **dog_breeds_txt** that was created in Windows.
```
Pug\r\n
Jack Russell Terrier\r\n
English Springer Spaniel\r\n
German Shepherd\r\n
Staffordshire Bull Terrier\r\n
Cavalier King Charles Spaniel\r\n
Golden Retriever\r\n
West Highland White Terrier\r\n
Boxer\r\n
Border Terrier\r\n
```
and different output will show on Unix device

```
Pug\r
\n
Jack Russell Terrier\r
\n
English Springer Spaniel\r
\n
German Shepherd\r
\n
Staffordshire Bull Terrier\r
\n
Cavalier King Charles Spaniel\r
\n
Golden Retriever\r
\n
West Highland White Terrier\r
\n
Boxer\r
\n
Border Terrier\r
\n
```
# Character Encodings
![encode](https://files.realpython.com/media/encode-decode.3e665ad9b455.png)
 encoding:
  is the process of putting a sequence of characters (letters, numbers, punctuation, and certain symbols) into a specialized format for efficient transmission or storage.
Most common encodeing Assigning used:
* ASCII  store 128 characters
* UNICODE store more than 1,114,112 characters.

ASCII and Unicode share the same character values numericaly cause ASCII part of Unicode

# Opening and Closing a File in Python
![o/c](https://miro.medium.com/max/249/1*BlLAd-qMWB0DQoR4bLsFwA.png)

❓how to open specific file in order to work on it? we need to invoke **built-in function open()**, need single argument **file path**
```
file = open('file_name.extintion')
```
❓how to close opened file after finish work on it?
We can use two way:
1. try-finally block:
```
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

2. close a file with statement:
```
with open('dog_breeds.txt') as reader:
    # Further file processing goes here
```
>the programmer highly recommended use with statement to handle unexpected errors and make cleaner code

Character | Meaning
------------ | -------------
'r' | Open for reading (default)
'w' | Open for writing, truncating (overwriting) the file first
'rb' or 'wb' | Open in binary mode (read/write using byte data)

following example for open text file in different way:
```
open('abc.txt')

open('abc.txt', 'r')

open('abc.txt', 'w')
```
# Buffered Binary File Types
<!-- ![buff](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQu5uGRs1UEt-Jk-2UH4iwbAK1_q0eq9ifffg&usqp=CAU) -->

Buffered Binary File Types:is used to read and write binary files

🔐following example how to open these file
```
open('abc.txt', 'rb')

open('abc.txt', 'wb')
```
🔐open() will return file object BufferedReader\Writer :
```
>>> file = open('dog_breeds.txt', 'rb')
>>> type(file)
<class '_io.BufferedReader'>
>>> file = open('dog_breeds.txt', 'wb')
>>> type(file)
<class '_io.BufferedWriter'>
```

# Raw File Types
Raw I/O (also called unbuffered I/O) generally used as a low-level binary and text-stream building block.

🔐following example how to open these file
```
open('abc.txt', 'rb', buffering=0)
```
🔐open() will return file object
```
>>> file = open('dog_breeds.txt', 'rb', buffering=0)
>>> type(file)
<class '_io.FileIO'>
```

Several methods that can be called from a file object during open file.

Method | What It Does
------------ | -------------
.read(size=-1) | read file based on number of size bytes they can read file if he didnt passed (argument,none,-1)
.readline(size=-1) | read the line contane bigger line size,they can read file if he didnt passed (argument,none,-1)
.readlines() | return the remaning lines from reading file object

🔐following example how to read entire file:
```
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read & print the entire file
>>>     print(reader.read())
Pug
Jack Russell Terrier
English Springer Spaniel
German Shepherd
Staffordshire Bull Terrier
Cavalier King Charles Spaniel
Golden Retriever
West Highland White Terrier
Boxer
Border Terrier
```
🔐following example how to read 5bytes:
```
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read & print the first 5 characters of the line 5 times
>>>     print(reader.readline(5))
>>>     # Notice that line is greater than the 5 chars and continues
>>>     # down the line, reading 5 chars each time until the end of the
>>>     # line and then "wraps" around
>>>     print(reader.readline(5))
>>>     print(reader.readline(5))
>>>     print(reader.readline(5))
>>>     print(reader.readline(5))
Pug

Jack
Russe
ll Te
rrier
```

# Iterating Over Each Line in the File
🔐following example how to read file using do while:
```
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     line = reader.readline()
>>>     while line != '':  # The EOF char is an empty string
>>>         print(line, end='')
>>>         line = reader.readline()
Pug
Jack Russell Terrier
English Springer Spaniel
German Shepherd
Staffordshire Bull Terrier
Cavalier King Charles Spaniel
Golden Retriever
West Highland White Terrier
Boxer
Border Terrier
```

🔐following example how to read file using .readlines() to return list:
```
>>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     for line in reader:
>>>         print(line, end='')
Pug
Jack Russell Terrier
English Springer Spaniel
German Shepherd
Staffordshire Bull Terrier
Cavalier King Charles Spaniel
Golden Retriever
West Highland White Terrier
Boxer
Border Terrier
```


Method | What It Does
------------ | -------------
.write(string) | This writes the string to the file.
.writelines(seq) | will didnt write line ending ending to each squence item

🔐following example how to read file using .write() and .writelines():
```
with open('dog_breeds.txt', 'r') as reader:
    # Note: readlines doesn't trim the line endings
    dog_breeds = reader.readlines()

with open('dog_breeds_reversed.txt', 'w') as writer:
    # Alternatively you could use
    # writer.writelines(reversed(dog_breeds))

    # Write the dog breeds to the file in reversed order
    for breed in reversed(dog_breeds):
        writer.write(breed)
```

# Working With Bytes
when use byte strings it will add b character to the mode argument,following example is show how add b:
```
>>> with open('dog_breeds.txt', 'rb') as reader:
>>>     print(reader.readline())
b'Pug\n'
```

we can open following (jack_russell.png) picture using 
".png file format" the next table show picture file content:

![pngDog](https://files.realpython.com/media/jack_russell.92348cb14537.png)

**table for picture file details**
Value | Interpretation
------------ | -------------
0x89 | A “magic” number to indicate that this is the start of a PNG
0x50 0x4E 0x47 | PNG in ASCII
0x0D 0x0A | A DOS style line ending \r\n
 0x1A | A DOS style EOF character
 0x0A | A Unix style line ending \n

🔐following example show how we can read .png file:
```
>>> with open('jack_russell.png', 'rb') as byte_reader:
>>>     print(byte_reader.read(1))
>>>     print(byte_reader.read(3))
>>>     print(byte_reader.read(2))
>>>     print(byte_reader.read(1))
>>>     print(byte_reader.read(1))
b'\x89'
b'PNG'
b'\r\n'
b'\x1a'
b'\n'
```

# Tips and Tricks

* __file__ attribute used with test script and print their statues
* Appending to a File using .write to add to file our write at the end of the file
* Working With Two Files at the Same Time we can use read from file and write in other file like following code:
```
d_path = 'dog_breeds.txt'
d_r_path = 'dog_breeds_reversed.txt'
with open(d_path, 'r') as reader, open(d_r_path, 'w') as writer:
    dog_breeds = reader.readlines()
    writer.writelines(reversed(dog_breeds))
```

* Creating Your Own Context Manager: create a context manager by using **with** and few other method like(__ enter __ and __ exit __)
>__ enter __ () is invoked when calling the with statement. __ exit __() is called upon exiting from the with statement block.

# Don’t Re-Invent the Snake
 .csv and .json. populare file pythone can work with them but need to  encounter while working with files
 built library will help us:
* wave: read and write WAV files (audio)
* aifc: read and write AIFF and AIFC files (audio)
* sunau: read and write Sun AU files
* tarfile: read and write tar archive files
* zipfile: work with ZIP archives

# Python Exceptions: An Introduction
![excep](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/intro.8915db1758d8.png&w=697&sig=3070a2e28334cad27558ecb5477cbf49fd738dcf)

* Syntax errors: happend when write incorrect statement.
```
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```
* Raising an Exception
use raise when certain condition
![nn](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/raise.3931e8819e08.png&w=697&sig=8f2b5e3f414c44ff5f7464e4793598843ba71ad1)
 following example show rasie exception

```
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
   #output
 Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```
* The AssertionError Exception

![assert](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/assert.f6d344f0c0b4.png&w=697&sig=2c0f41515d2346d13e166ee5bda87bc2ce72220e)

use assert when you could one of the output coulde be false
```
import sys
assert ('linux' in sys.platform), "This code runs on Linux only."

  #output
Traceback (most recent call last):
  File "<input>", line 2, in <module>
AssertionError: This code runs on Linux only.
```
* The try and except Block: Handling Exceptions
try & except:
is used to catch and handle exceptions.
![try](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/try_except.c94eabed2c59.png&w=697&sig=c3b8dc7765e44e335bded19fe998f3a6960cee07)

```
try:
    linux_interaction()
except:
    print('Linux function was not executed')
  #shell output
Linux function was not executed
```
* The else Clause
will can execute a certain block of code only if we dont have exceptions.
```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    print('Executing the else clause.')
 #shill output
Doing something.
Executing the else clause.
```

* Cleaning Up After Using finally
it use to do some sort after execute code
![cln](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png&w=697&sig=6903754041189bdc1e28fbb3f1ab9b454c0214d1)

```
try:
    linux_interaction()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('Cleaning up, irrespective of any exceptions.')
   
   # shell output
  Function can only run on Linux systems.
Cleaning up, irrespective of any exceptions. 
```
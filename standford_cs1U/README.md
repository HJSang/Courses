# Practical Unix

* [Course website](https://practicalunix.org/)
* [Video Schedule](https://practicalunix.org/video-schedule)

* I/O - Pipe: Redirection the input and output:
  - The standard shell syntax for anonymous pipes is to list multiple commands, separated by vertical bars ("pipes" in common Unix verbiage):
  ```
  process1 | process2 | process3
  ```
  - Examples:
    - Use sort and uniq command to sort a file and print unique values.
    ```
    sort record.txt | uniq
    ```
    - Use head and tail to print lines in a particular range in a file.
    ```
    cat sample2.txt | head -7 | tail -5
    ```
    This command select first 7 lines through (head -7) command and that will be input to (tail -5) command which will finally print last 5 lines from that 7 lines.

  - ``<``: to a file
  - ``>`` : from a file
  - ``<<``: append
  - ``|``: pipe
  - ``Tee``: Output something to a file and want to know the progress  while outputing
  - wc: word count 
  - grep: grep [options] pattern [files]
  - Homework:
    - read-input.py asks for 1000 numbers from stdin. Execute read-input.py and make it say "TRIUMPH!"
    ```
    chmod +ux read-input.py
    ./read-input.py < nums-0-999
    ```
    - List the contents of your home directory and store that in a file. List the contents of your home directory and append it to the same file
    ```
    ls -l < temp
    ls -l << temp
    ```
    - Thought question: what happens if you have a file called foo and you run cat < foo > foo? Intuitively, that would say to use foo as the input to cat and output that to foo. Why isn't that the case? Hint: Try running something that doesn't create any output, for instance: touch bar > foo. Why is foo empty even though the command never tried to write to it? Note that CSH on the Stanford machines has 'noclobber' option set. This will prevent you from overwriting any files ("clobbering" them). That is annoying and will prevent you from doing this exercise. Instead, use ZSH.
    - Thought question: what happens if you have a file called foo and you run cat < foo >> foo? Intuitively, that would print out foo and append it to foo, basically doubling the file. Why isn't that the case? Hint: How big is the file at the start and then how big is the file after cat has gone through the first line? Note: ctrl+C is your friend.
    - Print the last three lines of table. Print the first three lines of table. Print only the second and third lines of table.
    ```
    cat test.txt | tail -3
    cat text.txt | head -3
    cat test.txt | head -3 | tail -2
    ```
    - ``tr``: The tr command in UNIX is a command line utility for translating or deleting characters: 
    ```
    tr [OPTION] SET1 [SET2]
    ```
      - bad-new-line has a weird number of blank lines after each line of text. Create a file good-new-line that doesn't have a weird number of blank lines after each line of text. They should Replace it with just one line.
      ```
      cat bad-new-line | uniq | tee temp
      ```
    - ``sort``: -r: sort in Reverse Order; -n: sort a file numerically; -k: sorting a table on the basis of any column number by using -k option; -u: sort and remove duplicates;
    ```
    cat pumpkinsizes | tr -d  '|' | tail -11 | sort -k 7,6
    ```
    - ``uniq``: -d: Only output lines that are repeated in the input; -c: count
    - ``cut``:  cutting out the sections from each line of files and writing the result to standard output
      ```
      List without ranges
    $ cut -b 1,2,3 state.txt
    And
    Aru
    Ass
    Bih
    Chh

    List with ranges
    $ cut -b 1-3,5-7 state.txt
    Andra
    Aruach
    Assm
    Bihr
    Chhtti
    ```
    - ``-c``: To cut by character use the -c option. 
    ```
    cut -c [(k)-(n)/(k),(n)/(n)] filename
    cut -c 2,5,7 state.txt
    ```
    - ``join``: The join command in UNIX is a command line utility for joining lines of two files on a common field.
      - ``join [OPTION] FILE1 FILE2``
      - by default join command takes the first column as the key to join as in the above case
    - ``sed``: SED command in UNIX is stands for stream editor and it can perform lot’s of function on file like, searching, find and replace, insertion or deletion.
      - Replacing or substituting string: The below simple sed command replaces the word “unix” with “linux” in the file. ``sed 's/unix/linux/' geekfile.txt``.
      - Replacing the nth occurrence of a pattern in a line: ``sed 's/unix/linux/2' geekfile.txt``
      - Replacing all the occurrence of the pattern in a line: ``sed 's/unix/linux/g' geekfile.txt``
      - Replacing from nth occurrence to all occurrences in a line: ``sed 's/unix/linux/3g' geekfile.txt``
      - Parenthesize first character of each word: ``echo "Welcome To The Geek Stuff" | sed 's/\(\b[A-Z]\)/\(\1\)/g'``
      - Replacing string on a specific line number: ``sed '3 s/unix/linux/' geekfile.txt``
      - Duplicating the replaced line with /p flag: ``sed 's/unix/linux/p' geekfile.txt``
      - Printing only the replaced lines: ``sed -n 's/unix/linux/p' geekfile.txt``
      - Replacing string on a range of lines : ``sed '1,3 s/unix/linux/' geekfile.txt``
      - Deleting lines from a particular file: To Delete a particular line say n in this example: ``sed '5d' filename.txt``; To Delete line from range x to y:``sed '3,6d' filename.txt``; To Delete from nth to last line: ``sed '12,$d' filename.txt``;To Delete pattern matching line: ``sed '/abc/d' filename.txt``
  - ``awk``: Awk is a scripting language used for manipulating data and generating reports
    - AWK Operations: Scans a file line by line; Splits each input line into fields; Compares input line/fields to pattern;Performs action(s) on matched lines
    - [GeeksforGeeks](https://www.geeksforgeeks.org/awk-command-unixlinux-examples/)
    - `` awk options 'selection _criteria {action }' input-file > output-file``
    - Options:
    ```
    -f program-file : Reads the AWK program source from the file
                  program-file, instead of from the
                  first command line argument.
    -F fs            : Use fs for the input field separator
    ```
    - Print the lines which matches with the given pattern: ``awk '/manager/ {print}' employee.txt``
    - Splitting a Line Into Fields : For each record i.e line, the awk command splits the record delimited by whitespace character by default and stores it in the $n variables. If the line has 4 words, it will be stored in $1, $2, $3 and $4 respectively. Also, $0 represents the whole line. ``awk '{print $1,$4}' employee.txt ``
    - NR: NR command keeps a current count of the number of input records. Remember that records are usually lines. Awk command performs the pattern/action statements once for each record in a file.
    - NF: NF command keeps a count of the number of fields within the current input record
    - FS: FS command contains the field separator character which is used to divide fields on the input line. The default is “white space”, meaning space and tab characters. FS can be reassigned to another character (typically in BEGIN) to change the field separator.
    - RS: RS command stores the current record separator character. Since, by default, an input line is the input record, the default record separator character is a newline.
    - OFS: OFS command stores the output field separator, which separates the fields when Awk prints them. The default is a blank space. Whenever print has several parameters separated with commas, it will print the value of OFS in between each parameter.
    - ORS: ORS command stores the output record separator, which separates the output lines when Awk prints them. The default is a newline character. print automatically outputs the contents of ORS at the end of whatever it is given to print.


# Grep and Regular Expressions
* [diff](https://www.geeksforgeeks.org/diff-command-linux-examples/)
* The important thing to remember is that diff uses certain special symbols and instructions that are required to make two files identical.
* Special symbols are:

| symbol | meaning |
| ------ | ------- |
| a      | add     |
| c      | change  |
| d      | delete  |

* Syntax: `` diff [options] File1 File2 ``
* **-c(context)**: To view differences in context mode, use the -c option
* **-u(unified)**: To view differences in unified mode, use the -u option
* `` diff -bB``: ignores white lines and blank space

# find
* Syntax:
```
find [where to start searching from]
 [expression determines what to find] [-options] [what to find]
```
* Search a file with specific name:
```
find ./GFG -name sample.txt
```
* Search a file with pattern
```
find ./GFG -name *.txt
```
* How to find and delete a file with confirmation
```
find ./GFG -name sample.txt -exec rm -i {} \;
```
* Search for empty files and directories 
```
find ./GFG -empty
```
* Search for file with entered permissions
```
find ./GFG -perm 664
```
* Search text with multiple files
```
find ./ -type f -name "*.txt" -exec grep 'Greek' {}\;
```

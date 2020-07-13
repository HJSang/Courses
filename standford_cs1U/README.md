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
    - ``uniq``:  

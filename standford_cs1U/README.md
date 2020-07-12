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

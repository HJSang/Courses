# Courses 
 - Summer Quarter - [2019-2020](http://cs.stanford.edu/courses/schedules/2019-2020.summer.php)
 - Spring Quarter - [2020-2021](https://cs.stanford.edu/courses/schedules/2020-2021.spring.php)
 - Winter Quarter - [2020-2021](https://cs.stanford.edu/courses/schedules/2020-2021.winter.php)
 - Autumn Quarter - [2020-2021](https://cs.stanford.edu/courses/schedules/2020-2021.autumn.php)


 # CS106A: Programming Methodologies
- [link](http://web.stanford.edu/class/cs106a/)

# CS106B Programming Abstractions
- [link](https://web.stanford.edu/class/cs106b/)

# CS109: Probability for Computer Scientists
- [link](http://web.stanford.edu/class/cs109/)

# cs161: Design and Analysis of Algorithms
- [link](http://web.stanford.edu/class/cs161/)

- [Lecture2: Sorting and Recurrences](https://docs.google.com/presentation/d/1OAqjscz-yzr32hbDJZ2VdwKIdu8ropGHQuEzQJfobgo/edit?usp=sharing)

   - Induction to prove the valid of algorithm 
   - The master Theorem to show the complexity of recursive algorithms 
  
  ```
   Suppose that a>=1, b>1, and d are constants (i.e. independent of n).
   Suppose T(n) = a * T(n/b) + O(n^d). The master theorem states:
   - if a=b^d, T(n) = O(n^d logn)
   - if a<b^d, T(n) = O(n^d)
   - if if a > b^d, T(n) = O(n^{log_b(a)})
   ```
 - [Lecture3: Substitution Method and Select](https://docs.google.com/presentation/d/1iGaIwiBRsHXdOdnuSkpD1ielPU4fz2muYmypH-MY6z4/edit#slide=id.g820f38cd3e_0_0)
  - Linear Selection: Select(A, k) select k-th smallest one from list A.
  - Select a pivot: Median of medians [n/5] lists.
  - Partition around pivot
  - Recurse!

 - [Lecture4: Randomized Algorithm and QuickSort](https://docs.google.com/presentation/d/1HrZGUcvxC-j0udF68KI10lyN-t-3oe24e43UX6k9i4s/edit#slide=id.g8a4850c818_0_377)
  - Runtime for randomized algo: 
    - Expected running time: you publish your algorithm and a bad guy picks the input, then you run your randomized algo. Therefor, the running time is a random variable depending on the randomness of the algo, so we can reason about the expected running time.
    - Worst-case running time: you publish your algorithm and a bad guy picks the input, then the bad guy chooses the randomness("fix the dice") in your randomized algo. The running time is not random( we know how the bad guy will choose the randomness to make our algo suffer the most), so we can reason about the worst-case running time.
    - Quick Sort (Divide-and-Conquer): 
      - Select a pivot ar random
      - Partition a round it 
      - Recursively sort L and R

  - [Lecture5: Sorting Lower Bounds & Linear Sorting](https://docs.google.com/presentation/d/1dFk1EvK6jJU1Q88rKcoy0s-H9wUx9rGimU1XD-IgY_w/edit#slide=id.g8b8a3a4364_0_114)
    - Binary decision tree -> n! possible orderings -> the longest path has length at least log(n!) = O(nlogn)
    - Radix sort: a sorting algo for integers up to size M ( or more generally, for sorting strings)

# CS166: Data Structure
 - [Link](http://web.stanford.edu/class/cs166/)
 - [The Range Minimum Query (RMQ) problem: part I](http://web.stanford.edu/class/cs166/lectures/00/Small00.pdf)


# CS224U: NaturalLanguage Understanding
 - [Link](http://web.stanford.edu/class/cs224u/)


# CS229: Machine Learning
- [link](http://cs229.stanford.edu/)

# CS230: Deep Learning
 - [Link](http://cs230.stanford.edu/syllabus/)

 # CS231N: Convolutional Neural Networks for Visual Recog
  - [Link](https://cs231n.github.io/)

 # CS233: Geometric and Topological Data Analysis
   - [Link](http://graphics.stanford.edu/courses/cs233-20-spring/)

 # CS246: Mining Massive Data Sets
   - [Link](http://web.stanford.edu/class/cs246/)

# Description
Push_Swap is an algorithm project that implements sorting of integers using only two operations: push (move the top node between two linked lists) and rotate (rotate nodes between first node and last node or vice versa). The goal is to sort a variable list of numbers as efficiently as possible, demonstrating optimization techniques from basic chunking to the more advanced radix sort algorithm.

# Instructions
The push_swap project can me compiled with a Makefile and checked with the checker provided with the project (checker linux)

## Compilation
Once you are in the folder you can type this into the folder:
```bash
make
```

## Usage
When you have made the project you can run the program with a list of numbers you want to sort. You can type this into your terminal and run it a few times to see an average:
```bash
ARG=$(shuf -i lowest_number-highest_number -n size_of_list | tr '\n' ' '); ./push_swap $ARG | wc -l
```

## Testing
1. Use the provided checker as follows:
```bash
ARG=$(shuf -i 1-1000000 -n 500 | tr '\n' ' '); ./push_swap $ARG | ./push_swap_tests/checker_linux $ARG
```

# Benchmark
Both the minimum and maximum benches are given below. If the number of operations goes above the maximum at any point, the evaluation stops and we are failed for that part of the project. Minimum mark for validation is 84%.

## Minimal for project validation
At least one of the following conditions needs to be met for the minimum of 84%:
1. 100 numbers in under 1100 operations and 500 numbers in under
8500 operation
2. 100 numbers in under 700 operations and 500 numbers in under
11500 operations
3. 100 numbers in under 1300 operations and 500 numbers in under
5500 operations

## Maximun project validation
At least one of the following conditions needs to be met for the full 100% project validation:
1. Sort 100 random numbers in fewer than 700 operations.
2. Sort 500 random numbers in no more than 5500 operations.

## My project performance
These are the highest number of moves I have seen for the various unsorted list lengths, and the maximum number allowed for project validation according to my project:
1. 3 Numbers = 2 | Maximum = 3
2. 5 Numbers = 10 | Maximum = 12
3. 100 Numbers = 1075 | Maximum = 1100
4. 500 Numbers = 6784 | Maximum = 8500

# Algorithms I chose
The main algorithms to choose from were Radix, Mechanical Turk and Chunk sorting. I chose Chunk sorting for my 100 numbers and Radix sort lists larger than 100 numbers.

## Chunk sorting
Chunk sorting goes through the list and divides the numbers into chunks. Then chunk per chunk it puts them in linked list B, and then returns each number to linked list A in sorted order for that chunk. As each chunk gets processed and returned to A the list gets sorted. I chose this method for sorting 100 numbers because Radix sort is only efficient for larger numbers.

## Radix sort
Radix sort pre-sorts the numbers and pairs each int in the list with its indice if it was in an already sorted array. Radix sort then uses the binary of these indices to sort them. I chose this method becuase of its efficiency for big numbers and it was easier to grasp than the popular Mechanical Turk algorithm that a lot of people used.

# Resources
1. https://42-cursus.gitbook.io/guide/2-rank-02/push_swap
2. https://medium.com/@jamierobertdawson/push-swap-the-least-amount-of-moves-with-two-stacks-d1e76a71789a
3. https://www.youtube.com/watch?v=wRvipSG4Mmk
4. https://www.youtube.com/watch?v=OaG81sDEpVk
5. https://www.geeksforgeeks.org/dsa/radix-sort/
6. https://www.reddit.com/r/explainlikeimfive/comments/xuzyre/eli5_how_does_radix_sort_work/
7. Perplexity ai. I gave it the role of a lecturer and told it to answer any questions I had on the project. I explicitly told it not to give me direct answers but to rather quide me via scaffolding.
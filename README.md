# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

## Answer

Choosing the first element gives us a 50% chance to pick a good pivot. In order for median-of-three to be better, the odds of picking a good pivot must be higher for this.

In order for a selected pivot to be a good pivot, it must create two partitions of a least size $3n/4$ or $3/4$ the size of the original array.

There are three ways for a pivot to be, good, bad, or amazing. This gives us three cases for each, where each case is equally likely. This gives us 3^3 possibilities, as there are three options and three slots, first, median, and last. Meaning there are 27 possible combinations of pivots. 
We can find the odds of each case happening easily.
The cases are as follows bad = B, good = G, and amazing = A:
(BBB) (BBG) (BBA) (BGB) (BAB) (BGG) (BGA) (BAA) (BAG)
(GGG) (GGB) (GGA) (GBG) (GAG) (GBB) (GBA) (GAA) (GAB)
(AAA) (AAG) (AAB) (AGA) (ABA) (AGG) (AGB) (ABB) (ABG)
Looking at these, we can see that the median value is an A or G, amazing or good in 6 of the top row cases, 6 of the middle row cases, and 6 of the bottom row cases.
So for 18/27 cases, the median is a good pivot value. In 66.66% of cases, median-of-three is the better option, making median-of-three better than picking just the first element.


## Plagarism Statement and Sources

Used slides to get initial probabilities and requirements. 

Talked to student Lily Brongo, she put me on the path of breaking it down into all possibilities and going from there.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

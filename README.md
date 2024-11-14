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
The cases are as follows bad-low = B, good = G, and overshot = T:
(BBB) (BBG) (BBT) (BGB) (BTB) (BGG) (BGT) (BTT) (BTG)
(GGG) (GGB) (GGT) (GBG) (GTG) (GBB) (GBT) (GTT) (GTB)
(TTT) (TTG) (TTB) (TGT) (TBT) (TGG) (TGB) (TBB) (TBG)

Since all permutations are not equally likely we need to calculate the odds of each permutation occuring
Bad and Overshot both have a 25% chance of occuring, and Good has a 50% chance to occur. 
We need to calculate the odds of every option where G could be chosen as the median
This leaves us GGG, BGB, BGG, GGB, GGT, TGT, TGG, BGT, TGB, TBG, BTG, GTB, GBT
GGG = (1/2)^3 = 1/8

BGB = (1/2) * (1/4)^2 = 1/32
BGG = (1/2)^2 * (1/4) = 1/16
GGB = (1/2)^2 * (1/4) = 1/16

BGT = (1/4) * (1/2)* (1/4) = 1/32
TGB = (1/4) * (1/2) * (1/4) = 1/32
TBG = (1/4) * (1/4) * (1/2) = 1/32
BTG = (1/4) * (1/4) * (1/2) = 1/32
GTB = (1/2) * (1/4) * (1/4) = 1/32
GBT = (1/2) * (1/4) * (1/4) = 1/32

GGT = (1/2)^2 * (1/4) = 1/16
TGT = (1/4) * (1/2) * (1/4) = 1/32
TGG = (1/4) * (1/2)^2 = 1/16

The following outcomes contain a good choice:
GGG as it must,
Variations of GGB including GGB, GBG, and BGG, as the median of these values must be a good choice
Variations of GGT including GGT, GTG, and TGG, for the same reason
Variations of BGT including BTG, BGT, GBT, GTB, TGB, and TBG because the median of a low, median, and high is always the median.
1 case of GGG 1/8
3 cases of GGB 3(1/16)
3 cases of GGT 3(1/16)
6 cases of BGT 6(1/32)

1/8 + 3/16 + 3/16 + 6/32 = 
1/8 + 9/16 = 
0.125 + 0.5625 = 
0.6875 or 68.75%
Because of this, we know that median-of-three is better than picking the first pivot value. This is because a 68.75% chance is better than a 50% chance.


## Plagarism Statement and Sources

Used slides to get initial probabilities and requirements. 

Talked to student Lily Brongo, she put me on the path of breaking it down into all possibilities and going from there. 

I looked at acraig9266's [repo] (https://github.com/COSC3020/quicksort-pivot-acraig9266) and realized that the median would still be the median even in cases where there were multiple bad options, as long as they were on opposite sides. That really opened my mind up and allowed me to realize where I was going wrong. That repo used true and false states, so I expanded on that in my own work.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

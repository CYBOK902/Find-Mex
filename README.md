# Find-Mex
Problem
You are given an integer array of length 
.You have to find of element for all of the element is the minimum element greater than or equal to which is not present in array till the index.
 
Input Format:

First line contains an integer 
 denoting the size of array.

Next line contains 
 integers denoting the elements of the array.


Output Format:

Print 
 integers. 
 element should be the 
 of the array prefix till 

Constraints:

Sample Input
5
1 0 5 5 3
Sample Output
0 2 2 2 2
Time Limit: 1
Memory Limit: 256
Source Limit:
Explanation
For first test case mex of first index is 0. As it is note present in array

mex of second index is 2 as 0 and 1 is present in array.

mex of 3rd, 4th and 5th index is 2.


<<<<<<<<<<<<<<<<<<!Code!>>>>>>>>>>>>>>>>>>>>>>>

#include <stdio.h>

void mex_array(int n, int arr[]) {
    int seen[n];
    int mex_values[n];

    for (int i = 0; i < n; i++) {
        seen[i] = 0;
    }

    for (int i = 0; i < n; i++) {
        seen[arr[i]] = 1;

        int mex = 0;
        while (seen[mex]) {
            mex++;
        }

        mex_values[i] = mex;
    }

    for (int i = 0; i < n; i++) {
        printf("%d ", mex_values[i]);
    }
}

int main() {
    int n;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    mex_array(n, arr);

    return 0;
}




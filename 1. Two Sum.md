# Exercicio do LeetCode - TwoSum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]   
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].  

    
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

•  2 <= nums.length <= 104   
•  -109 <= nums[i] <= 109    
•  -109 <= target <= 109     
•  Only one valid answer exists.

```c
#include <stdio.h>
#include <stdlib.h>

void PreencheVetor(int *nums, int numsSize) {
    
    printf("\nPreencha o vetor.\n");
    for ( int i = 0; i < numsSize; i++ ) {
        printf("Proximo valor: ");
        scanf("%d", (nums+i));
    }
}


void ImprimeVetor(int *nums, int numsSize) {
    
    printf("\nVetor.\n");
    for ( int i = 0; i < numsSize; i++ ) {
        printf("nums[%d] = %d\n", i, nums[i]);
    }
}


int* TwoSum(int* nums, int numsSize, int target) {
    
    int *answer;
    answer = (int *)malloc(2 * sizeof(int));
    if (answer == NULL){
        return 0;
    }

    for ( int i = 0; i < numsSize; i++ ) {
        for ( int j = i + 1; j < numsSize; j++ ) {
            if ( nums[i] + nums[j] == target ) {
                answer[0] = i;
                answer[1] = j;
                return answer;
            }
        }
    }
}


int main() {

    int *nums, target, numsSize;

    printf("\nDigite o tamanho do vetor: ");
    scanf("%d", &numsSize);

    nums = (int *)malloc(numsSize * sizeof(int));
    if (nums == NULL){
        return 0;
    }

    PreencheVetor(nums, numsSize);
    ImprimeVetor(nums, numsSize);

    printf("\nTarget: ");
    scanf("%d", &target);

    int *resultado;
    resultado = (int *)malloc(numsSize * sizeof(int));
    if (resultado == NULL){
        return 0;
    }
    
    resultado = TwoSum(nums, numsSize, target);

    printf("\n\nResultado = [%d,%d]\n\n", resultado[0], resultado[1]);
    

    free(nums);

}
```

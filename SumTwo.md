# Exercicio do LeetCode - SumTwo

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

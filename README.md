~~~
#define _CRT_SECURE_NO_WARNINGS
#define MAX_N 100 // Максимально допустимый размер массива
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <locale.h>
#include <math.h>

int main() {
    setlocale(LC_CTYPE, "RUS");
    int arr[MAX_N];
    int n;
    printf("Введите количество элементов массива (1-%d): ", MAX_N);
    scanf("%d", &n);
    printf("Введите %d целых чисел: (от меньшего к большему)\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    int min_idx = 0;
    int max_idx = 0;
    for (int i = 1; i < n; i++) {
        if (arr[i] < arr[min_idx]) {
            min_idx = i;
        }
        if (arr[i] > arr[max_idx]) {
            max_idx = i;
        }
    }
    int left = (min_idx < max_idx) ? min_idx : max_idx;
    int right = (min_idx > max_idx) ? min_idx : max_idx;
    int sum = 0;
    int count = 0;
    for (int i = left + 1; i < right; i++) {
        sum += arr[i];
        count++;
    }
    if (count > 0) {
        double avg = (double)sum / count;
        printf("Среднее арифметическое элементов между min и max: %.2f\n", avg);
    }
    else {
        printf("Между минимальным и максимальным элементами нет других чисел.\n");
    }
    return 0;
}
~~~

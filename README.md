# Day-2-c
#include <stdio.h>
#include <string.h>

int isPalindrome(char str[], int start, int end) {
    while (start < end) {
        if (str[start] != str[end]) {
            return 0;
        }
        start++;
        end--;
    }
    return 1;
}

int main() {
    char str[100];
    int i, j;
    int maxLen = 1;
    int startIndex = 0;

  printf("Enter a string: ");
    scanf("%s", str);

   int n = strlen(str);

  
  for (i = 0; i < n; i++) {
        for (j = i; j < n; j++) {

  if (isPalindrome(str, i, j)) {

  if (j - i + 1 > maxLen) {
                    maxLen = j - i + 1;
                    startIndex = i;
                }
            }
        }
    }
    printf("Longest palindromic substring: ");

   for (i = startIndex; i < startIndex + maxLen; i++) {
        printf("%c", str[i]);
    }

   return 0;
}
#include <stdio.h>

int main() {
    char str[100];
    int freq[256] = {0};
    int i;

  printf("Enter a string: ");
    scanf("%s", str);

   // Count frequency of each character
    for (i = 0; str[i] != '\0'; i++) {
        freq[(unsigned char)str[i]]++;
    }

  // Find first character occurring once
    for (i = 0; str[i] != '\0'; i++) {
        if (freq[(unsigned char)str[i]] == 1) {
            printf("First non-repeating character: %c", str[i]);
            return 0;
        }
    }
    printf("-1");

  return 0;
}
#include <stdio.h>

int main() {
    char str[100];
    int visited[256] = {0};
    int i;

  printf("Enter a string: ");
    scanf("%s", str);

   printf("After removing duplicates: ");

   for (i = 0; str[i] != '\0'; i++) {
        unsigned char ch = str[i];

   if (visited[ch] == 0) {
            printf("%c", str[i]);
            visited[ch] = 1;
        }
    }

  return 0;
}

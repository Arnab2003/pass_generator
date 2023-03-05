# pass_generator
password_generator
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <ctype.h>



int main()
{
    int size;
    printf("\nEnter a length to generate password:");
    scanf("%d",&size);
    char password[size + 1];
    const char charset[] = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()_+";
    int i;

    srand(time(NULL)); // seed the random number generator

    for (i = 0; i < size; i++) {
        password[i] = charset[rand() % (sizeof(charset) - 1)];
    }
    password[size] = '\0'; // terminate the string

    printf("\nGenerated password: %s\n", password);

    return 0;
}



    To duplicate lines:
        ALT + SHIFT + ARROW KEY

    To move lines:
        ALT +  ARROW KEY

#include <string.h>
- Inludes string functions.

char str[] = "this is a STRING";

1. strupr(string)
    - Converts string into uppercase
        strupr(str);
        puts(str);

2. strlwr(string)
    - Converts string into lowercase
        strlwr(str);
        puts(str);

3. strlen(string)
    - Returns string length / size 
        char str[] = "abc";
        int x = strlen(str);
        printf("%d", x);


4. strcpy(destination_string, source_string);
    - Copies the content of source string into destination string.
        char str1[] = "";
        char str2[] = "Hello";
        strcpy(str1, str2);
        puts(str1);

5. strcat(first_string, second_string)
    - Concatenates / Combines second string into first string.
        char str1[] = "Hello";
        char str2[] = "World";
        strcat(strcat(str1, " "), str2);
        puts(str1);

6. strcmp(first_string, second_string)
    - Compares first string with second string if both strings are same returns 0
        char str1[] = "helxlo";
        char str2[] = "hellasdo";
        int result = strcmp(str1, str2 );
        printf("%d", result);

7. strrev(string)
    - Reverses string 
        char str[] = "Hello";
        strrev(str);
        puts(str);

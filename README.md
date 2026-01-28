# Ex-5 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

## AIM:

To write a C program to implement the rail fence transposition technique.

## DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## ALGORITHM:

STEP-1: Read the Plain text.

STEP-2: Arrange the plain text in row columnar matrix format.

STEP-3: Now read the keyword depending on the number of columns of the plain text.

STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.

STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

## PROGRAM

```
#include <stdio.h>
#include <string.h>
int main() {
    char text[1000];
    int rails, len;
    int rail[100][1000];
    int i, j, row;
    int dir = 1;   // direction: 1 = down, -1 = up
    printf("Enter the secret message: ");
    fgets(text, sizeof(text), stdin);
    // remove newline
    text[strcspn(text, "\n")] = '\0';
    printf("Enter number of rails: ");
    scanf("%d", &rails);
    len = strlen(text);

    // initialize matrix
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = '\0';

    // place characters in zig-zag
    row = 0;
    for (j = 0; j < len; j++) {
        rail[row][j] = text[j];

        if (row == 0)
            dir = 1;
        else if (row == rails - 1)
            dir = -1;

        row += dir;
    }

    // read row-wise to get cipher text
    printf("Encrypted Message: ");
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            if (rail[i][j] != '\0')
                printf("%c", rail[i][j]);

    printf("\n");
    return 0;
}

```

## OUTPUT

<img width="556" height="215" alt="image" src="https://github.com/user-attachments/assets/f2eb5c01-a4f6-4a3c-89bf-ffa7b80d6f80" />

## RESULT

Thus the c program to implement Rail Fence Cipher is executed successfully.

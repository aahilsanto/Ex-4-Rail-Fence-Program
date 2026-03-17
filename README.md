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

```python
def rail_fence_encrypt(text, rails):
    fence = {i: [] for i in range(rails)}
    row, dir = 0, 1
    for ch in text:
        fence[row].append(ch)
        if row == 0: 
            dir = 1
        elif row == rails - 1: 
            dir = -1
        row += dir
    return "".join("".join(fence[r]) for r in range(rails))


text  = input("Enter the secret message: ")
rails = int(input("Enter number of rails: "))
encrypted = rail_fence_encrypt(text, rails)
print(f"Encrypted Message: {encrypted}")

```

## OUTPUT

<img width="556" height="215" alt="image" src="https://github.com/user-attachments/assets/f2eb5c01-a4f6-4a3c-89bf-ffa7b80d6f80" />

## RESULT

Thus the c program to implement Rail Fence Cipher is executed successfully.

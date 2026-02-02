# Ex-5 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a python program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
# Rail Fence Cipher Encryption Program

def rail_fence_encrypt(message, rails):
    length = len(message)

    rail = []
    for i in range(rails):
        row = []
        for j in range(length):
            row.append('\n')
        rail.append(row)

    row = 0
    direction_down = False

    for col in range(length):
        rail[row][col] = message[col]

        if row == 0:
            direction_down = True
        elif row == rails - 1:
            direction_down = False

        if direction_down:
            row += 1
        else:
            row -= 1

    encrypted_text = ""
    for i in range(rails):
        for j in range(length):
            if rail[i][j] != '\n':
                encrypted_text += rail[i][j]

    return encrypted_text


message = input("Enter a Secret Message:\n")
rails = int(input("Enter number of rails:\n"))

result = rail_fence_encrypt(message, rails)
print("Encrypted Message:", result)
```

# OUTPUT

<img width="940" height="286" alt="image" src="https://github.com/user-attachments/assets/343aae4b-5023-48bc-8ba5-42ec06e0ddcd" />


# RESULT

Thus, the python program to implement the Rail Fence transposition technique was successfully executed and the encrypted message was obtained.

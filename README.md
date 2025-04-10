# Mastermind-game
#"A simple Python implementation of the Mastermind game.
from numpy import random

def getinput():
    a = input()
    b = list(a)
    Guess = []
    for letter in (b):
        Guess.append(int(letter))
    return Guess
    

cc = 0 #Correct color
cp = 0 #C0rrect position 
cnt = 0 # Correct number of test
Win = 0
Max_Guess = 5
arr = [1, 2, 3, 4,5, 6]
Password = random.permutation(arr)
Password = Password[2:]
while (cnt <= Max_Guess):

    cc = 0
    cp = 0
    Guess = getinput()
    for i in range(0, 4):
        if Password[i] == Guess[i]:
            cc +=1
        
    for i in range (0, 4):
        for j in range (0, 4):
            if Password[i] == Guess[j]:
                cc += 1 

    cnt += 1
    cc = cc - cp

    if (cp == 4):
        Win = 1
        print("You Win!!!")
        break
    else:
        print (f' cc is {cc} and cp is {cp}')

if (Win == 0):
    print('Game over!!! Password:\n', *Password, Password)

    

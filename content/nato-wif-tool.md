---
title: "NATO WIF Tool"
---

A [Tool](https://github.com/6102bitcoin/bitcoin_tools/blob/master/NATO_wif.py) to Convert WIF private keys into NATO Words for easier backup.

```python
// Python code

def wiftoNATO():
    global NATO_characters, character, wif, NATO
    i = 0
    for x in NATO_characters:
        if x[0] == character:
            wif.append(x[0])
            NATO.append(x[1])
        else:
            i = i + 1
            if i >= len(NATO_characters):
                NATO.append("---ERROR---")
                wif.append("---ERROR---")
    return NATO
def check_NATO():
    global NATO_characters, word, wif, NATO
    i = 0
    check = False
    for x in NATO_characters:
        if x[1] == word:
            wif.append(x[0])
            NATO.append(x[1])
            check = True
        else:
            i = i + 1
            if i >= len(NATO_characters):
                check = False
    return check

# lowercase letters
a = ('a','alfa')
b = ('b','bravo')
c = ('c','charlie')
d = ('d','delta')
e = ('e','echo')
f = ('f','foxtrot')
g = ('g','golf')
h = ('h','hotel')
i = ('i','india')
j = ('j', 'juliett')
k = ('k', 'kilo')
l = ('l', 'lima')
m = ('m', 'mike')
n = ('n', 'november')
o = ('o', 'oscar')
p = ('p', 'papa')
q = ('q', 'quebec')
r = ('r', 'romeo')
s = ('s', 'sierra')
t = ('t', 'tango')
u = ('u', 'uniform')
v = ('v', 'victor')
w = ('w', 'whiskey')
x = ('x', 'x-ray')
y = ('y', 'yankee')
z = ('z', 'zulu')
# UPPERCASE letters
A = ('A','ALFA')
B = ('B','BRAVO')
C = ('C','CHARLIE')
D = ('D','DELTA')
E = ('E','ECHO')
F = ('F','FOXTROT')
G = ('G','GOLF')
H = ('H','HOTEL')
I = ('I','INDIA')
J = ('J', 'JULIETT')
K = ('K', 'KILO')
L = ('L', 'LIMA')
M = ('M', 'MIKE')
N = ('N', 'NOVEMBER')
O = ('O', 'OSCAR')
P = ('P', 'PAPA')
Q = ('Q', 'QUEBEC')
R = ('R', 'ROMEO')
S = ('S', 'SIERRA')
T = ('T', 'TANGO')
U = ('U', 'UNIFORM')
V = ('V', 'VICTOR')
W = ('W', 'WHISKEY')
X = ('X', 'X-RAY')
Y = ('Y', 'YANKEE')
Z = ('Z', 'ZULU')
# Numbers
n0 = ('0','ZERO')
n1 = ('1','ONE')
n2 = ('2','TWO')
n3 = ('3','THREE')
n4 = ('4','FOUR')
n5 = ('5','FIVE')
n6 = ('6','SIX')
n7 = ('7','SEVEN')
n8 = ('8','EIGHT')
n9 = ('9','NINE')

NATO_characters = [a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z,A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z,n0,n1,n2,n3,n4,n5,n6,n7,n8,n9]

mode = 0
count = 0
wif = []
NATO = []

# SELECT MODE
print("SELECT MODE:")
print("A | (Enter WIF)")
print("B | (Enter NATO)")
mode = input("Select Mode (Type A or B): ")

if mode == "A" or mode == "a":
    wif_long = input('Paste WIF: ')
    for character in wif_long:
        wiftoNATO()
    print("Store This Somewhere Safe!")
    for x in wif:
        print("Word " + str(count + 1) + ": " + NATO[count])
        count = count + 1

if mode == "B" or mode=="b":
    exit = False
    print("Please Note: Input is CASE sensitive (Numbers in CAPS)")
    while exit == False:
        NATO_next = input('Enter next word (X to end): ')
        if NATO_next == "X":
            exit = True
            wif = ''.join(wif)
            print("Store This Somewhere Safe!")
            print(str(wif))
        else:
            word = NATO_next
            if check_NATO() == False:
                print("WORD NOT RECOGNIZED")
```

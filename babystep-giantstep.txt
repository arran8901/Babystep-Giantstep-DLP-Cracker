# Shank's Babystep-Giantstep Algorithm
# Calculate x in a^x = b (mod p)

import math

print "Input your values for a^x = b (mod p)"
a = input("Enter a: ")
b = input("Enter b: ")
p = input("Enter p: ")

# Algorithm will check numbers up to number just above sqrt(p)
n = int(math.ceil(math.sqrt(p)))
#print n

baby = []
giant = []

for i in range (0, n):

  # baby = a^i (mod p)
  baby.append(pow(a, i, p))
  
  # giant = b * a^(-ni) (mod p)
  g = (b * pow(pow(a, n * i), p - 2, p)) % p
  giant.append(g)

  # Now run through all elements of baby to find a match
  for j in baby:
    # If match is found, value of x = i[baby's] + n * i[giant's]
    if j == g:
      #print baby
      #print giant
      print "x = " + str(baby.index(j) + (i * n))
# Babystep-Giantstep-DLP-Cracker
Shank's babystep-giantstep collision algorithm to solve the Discrete Logarithm Problem (and hence, cryptosystems that rely on the difficulty of the DLP, and the Diffie-Hellman exchange)

The babystep-giantstep algorithm is designed to solve the DLP. It is more efficient than brute-force trial and error, but still quite slow for large numbers.

For a^x = b (mod p);

It creates two lists up to n where n > sqrt(p):
Baby steps = {e, a, a^2, a^3, ... , a^n}
Giant steps = {b, b(a^-n), b(a^-n)^2, b(a^-n)^3, ... , b(a^-n)^n}

It will then look for a common value in the two lists, i.e. a^i = b(a^-n)^j.
Then the value of x in a^x = b (mod p) is i + nj

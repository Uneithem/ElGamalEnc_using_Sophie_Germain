# ElGamalEnc_using_Sophie_Germain

Encryption and signing algorythms are the same as used in my previous work https://github.com/Uneithem/ElGamal_sign_and_encrypt

This update is only related to the prime number and primitive root generation

Generating large prime numbers is computationally difficult tasks, however, finding primitive roots is even tougher, that's why I was searching for the way to make computations easier and came across Sophie Germain primes.

In a nutshell, they're such primes p that 2*p + 1 is also prime. Which decreases amount of computations needed to find primitive root modulo 2p + 1, as only three numbers can be multiplicative orders of a (a belongs to Z/(2p + 1) - modular ring of nonnegative integers with modulo 2p + 1) and these are 2, p and 2p. We're only interested in such numbers that their multiplicative order is 2p, that's why we need to check only two conditions: if a^2 = 1 (mod (2p + 1)) or a^p = 1 (mod (2p + 1)) and reject a as a primitive root for 2p + 1 is any of these two conditions is true. Which in practice has shown to be faster and more efficient way to find primitive roots.

Huge downside is inreased complicity of calculating primes for our modulus. It has shown to be a huge downgrade compared to the regular primes, however it's not comparable to the time we save computing primitive roots

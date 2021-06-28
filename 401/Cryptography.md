# Caesar cipher
 cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

The encryption step performed by a Caesar cipher is often incorporated as part of more complex schemes, such as the Vigenère cipher, and still has modern application in the ROT13 system. As with all single-alphabet substitution ciphers, the Caesar cipher is easily broken and in modern practice offers essentially no communications security.

![0](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Caesar_cipher_left_shift_of_3.svg/220px-Caesar_cipher_left_shift_of_3.svg.png)

The action of a Caesar cipher is to replace each plaintext letter with a different one a fixed number of places down the alphabet. The cipher illustrated here uses a left shift of three, so that (for example) each occurrence of E in the plaintext becomes B in the ciphertext.


## Example
he transformation can be represented by aligning two alphabets; the cipher alphabet is the plain alphabet rotated left or right by some number of positions. For instance, here is a Caesar cipher using a left rotation of three places, equivalent to a right shift of 23 (the shift parameter is used as the key):

![1](https://www9.0zz0.com/2021/06/28/15/562470362.png)

When encrypting, a person looks up each letter of the message in the "plain" line and writes down the corresponding letter in the "cipher" line.

```
Plaintext:  THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG
Ciphertext: QEB NRFZH YOLTK CLU GRJMP LSBO QEB IXWV ALD
```

Deciphering is done in reverse, with a right shift of 3.

The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, A → 0, B → 1, ..., Z → 25.[2] Encryption of a letter x by a shift n can be described mathematically as:

![2](https://wikimedia.org/api/rest_v1/media/math/render/svg/77b59c7a676a99610ddee4ffc305aa7f9cda3b1a)

Decryption is performed similarly,

![3](https://wikimedia.org/api/rest_v1/media/math/render/svg/8ed607e0202ff8d35aa41559f846cac9d358a362)

The replacement remains the same throughout the message, so the cipher is classed as a type of monoalphabetic substitution, as opposed to polyalphabetic substitution.

## History and usage

The Caesar cipher is named after Julius Caesar, who, according to Suetonius, used it with a shift of three (A becoming D when encrypting, and D becoming A when decrypting) to protect messages of military significance. While Caesar's was the first recorded use of this scheme, other substitution ciphers are known to have been used earlier.

In April 2006, fugitive Mafia boss Bernardo Provenzano was captured in Sicily partly because some of his messages, clumsily written in a variation of the Caesar cipher, were broken. Provenzano's cipher used numbers, so that "A" would be written as "4", "B" as "5", and so on.

In 2011, Rajib Karim was convicted in the United Kingdom of "terrorism offences" after using the Caesar cipher to communicate with Bangladeshi Islamic activists discussing plots to blow up British Airways planes or disrupt their IT networks. Although the parties had access to far better encryption techniques (Karim himself used PGP for data storage on computer disks), they chose to use their own scheme (implemented in Microsoft Excel), rejecting a more sophisticated code program called Mujahedeen Secrets "because 'kaffirs', or non-believers, know about it, so it must be less secure". This constituted an application of security through obscurity.

## Breaking the cipher

The Caesar cipher can be easily broken even in a ciphertext-only scenario. Two situations can be considered:

1. an attacker knows (or guesses) that some sort of simple substitution cipher has been used, but not specifically that it is a Caesar scheme.
2. an attacker knows that a Caesar cipher is in use, but does not know the shift value.

In the first case, the cipher can be broken using the same techniques as for a general simple substitution cipher, such as frequency analysis or pattern words. While solving, it is likely that an attacker will quickly notice the regularity in the solution and deduce that a Caesar cipher is the specific algorithm employed.

In the second instance, breaking the scheme is even more straightforward. Since there are only a limited number of possible shifts (25 in English), they can each be tested in turn in a brute force attack. One way to do this is to write out a snippet of the ciphertext in a table of all possible shifts a technique sometimes known as "completing the plain component". The example given is for the ciphertext "EXXEGOEXSRGI"; the plaintext is instantly recognisable by eye at a shift of four. Another way of viewing this method is that, under each letter of the ciphertext, the entire alphabet is written out in reverse starting at that letter. This attack can be accelerated using a set of strips prepared with the alphabet written down in reverse order. The strips are then aligned to form the ciphertext along one row, and the plaintext should appear in one of the other rows.

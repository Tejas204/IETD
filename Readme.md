## IETD
This repository contains the code for a novel image encryption technique using Tinkerbell and Duffing chaotic map. The analysis is also made available.

## Research Paper
See the paper here: https://link.springer.com/article/10.1007/s11042-022-13162-x

## Technical Details
The following are some important terminologies used in the implementation and the paper above.

### Terminologies
1. **x**
   - _Data structure:_ 1-D array
   - Use: Contains first dimension of the TD chaotic map.

2. **y**
   - _Data structure:_ 1-D array
   - _Use:_ Contains second dimension of the TD chaotic map.

3. **xor_array**
   - _Data structure:_ 1-D array
   - _Creation:_ It is created by multiplying corresponding values from "x" and "y" array
   - _Use:_ useful in the function named chaotic scrambling for XOR operation with corresponding pixel values.

### Functions and Parameters
The following are the list of functions and their parameters:

1. **_chaotic_scrambling_**
   - _Parameters:_ input image
   - _Description:_ Each pixel value of the input image is XOR with the corresponding value in the "xor_array", generated from the chaotic maps.
   
   
   
2. **_chaotic_swapping_**
   - _Parameters:_ output of chaotic_scrambling
   - _Description:_ Each pixel of the image received from chaotic_scrambling is swapped with the pixel value present at the location x[i]y[i]
   
   
   
3. **_zigzag_scrambling_**
   - _Parameters:_ output of chaotic swapping
   - _Description:_ The channels of the image are traversed in a zigzag manner, all the while, changing the position of the pixels, in order of the traversal. The  function takes consideration the height and width of the image, and applies the conditions of traversal accordingly. The encrypted image is obtained after this function.
                   
                                
4. **_zigzag_descrambling_**
   - _Parameters:_ encrypted image
   - _Description:_ The channels of the image are traversed in a zigzag manner, all the while, changing the position of the pixels, in order of the traversal. The order of traversal is reverse of zigzag_scrambling. The  function takes consideration the height and width of the image, and applies the conditions of traversal accordingly.
                   
                   
5. **_chaotic_deswapping_**
   - _Parameters:_ output of zigzag_descrambling
   - _Description:_ Each pixel of the image received from zigzag_descrambling is swapped with the pixel value present at the location x[i]y[i], but in the reverse order.
   
   
   
6. **_chaotic_descrambling_**
   - _Parameters:_ output of chaotic_deswapping
   - _Description:_ Each pixel of the input image is XOR with the corresponding value in the "xor_array", generated from the chaotic maps.The decrypted image is obtained after this function.

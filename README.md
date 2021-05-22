# IETD
This repository contains the code for a novel image encryption technique using Tinkerbell and Duffing chaotic map.

Some important terminologies and variables:
1. x: 1) Data structure: 1-D array
      2) Use: Contains first dimension of the TD chaotic map.

2. y: 1) Data structure: 1-D array
      2) Use: Contains second dimension of the TD chaotic map.

3. xor_array: 1) Data structure: 1-D array
              2) Creation: It is created by multiplying corresponding values from "x" and "y" array
              3) Use: useful in the function named chaotic scrambling for XOR operation with corresponding pixel values.




The following are the list of functions and their parameters:

1. a. Function name: chaotic_scrambling

   b. Parameters: input image
   
   c. Description: Each pixel value of the input image is XOR with the corresponding value in the "xor_array", generated from the chaotic maps.
   
   
   
2. a. Function name: chaotic_swapping

   b. Parameters: output of chaotic_scrambling
   
   c. Description: Each pixel of the image received from chaotic_scrambling is swapped with the pixel value present at the location x[i]y[i]
   
   
   
3. a. Function name: zigzag_scrambling

   b. Parameters: output of chaotic swapping
   
   c. Description: (1) The channels of the image are traversed in a zigzag manner, all the while, changing the position of the pixels, in order of the traversal.
   
                   (2) The  function takes consideration the height and width of the image, and applies the conditions of traversal accordingly.
                   
                   (3) The encrypted image is obtained after this function.
                   
                   
                
4. a. Function name: zigzag_descrambling

   b. Parameters: encrypted image
   
   c. Description: (1) The channels of the image are traversed in a zigzag manner, all the while, changing the position of the pixels, in order of the traversal.
                   (2) The order of traversal is reverse of zigzag_scrambling.
                   (3) The  function takes consideration the height and width of the image, and applies the conditions of traversal accordingly.
                   
                   
5. a. Function name: chaotic_deswapping

   b. Parameters: output of zigzag_descrambling
   
   c. Description: Each pixel of the image received from zigzag_descrambling is swapped with the pixel value present at the location x[i]y[i], but in the reverse order.
   
   
   
6. a. Function name: chaotic_descrambling

   b. Parameters: output of chaotic_deswapping
   
   c. Description: Each pixel of the input image is XOR with the corresponding value in the "xor_array", generated from the chaotic maps.

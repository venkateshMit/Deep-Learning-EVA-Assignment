Venkatesh Kulkarni Venkatesh3ae@gmail.com
Raghavendra raghavendra.manandi@gmail.com
Ajit Kumar Singh me.ajitkumar@gmail.com
Sudharshan sjsudharshan16@gmail.com

## What are Channels and Kernels (according to EVA)

**Channel:**
 A channel is collection of features or information.
- In laymen terms, A channel is like news channel (Aajthak, TV9, etc..) which has collection of news or information.
- After each convolutions, we end up extracting new set of values which give new representation of infrormation. There can be multiple channels that represent an image.

**Kernels:**
- Kernels are also call filters, feature extractors
- Kernels are feature extractor. We can extract different features from image by performing convolution using different kernels
- Example for a 3*3 kernal ([Example](https://wikimedia.org/api/rest_v1/media/math/render/svg/5bf6623ca763ba780b471a565eb1b06cd14b445c))
[[1,1,1],
[0,0,0],
[-1,-1,-1]]
- We mostly use 3*3 kernels in our code.

<image goes here>



## Why should we (nearly) always use 3x3 kernels?
- 3x3 helps us to extract more features, for example, say we have 5x5 image, if we apply a 3x3 convolution on it, the resulting channel will be 3x3, while if you apply a 5x5, the resulting channel would be 1x1.
- In case of 3x3 we would do 9(3 multiplyed by 3) computations to eextract a feature. In case of 5x5 or higher, we would have to do 25( 5 multiplyed by 5) computation to extract a feature.
- In terms of parameters, 3x3 require 9 parameters. In case of 5x5 or higher we need more parameters.
- More imformation for 3x3 can be forund [here](https://medium.com/@icecreamlabs/3x3-convolution-filters-a-popular-choice-75ab1c8b4da8#:~:text=It%20is%20used%20for%20blurring,a%20kernel%20and%20an%20image.&text=We%20are%20specifically%20referring%20to,matrix%20objects%20such%20as%20images.)

## How many times to we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)

**Total numbe of times we need to perform 3x3 is 100**

199 x 199 > 197 x 197 > 195 x 195 > 193 x 193 > 191 x 191 > 189 x 189 > 187 x 187 > 185 x 185 > 183 x 183 > 181 x 181 > 179 x 179 > 177 x 177 > 175 x 175 > 173 x 173 > 171 x 171 > 169 x 169 > 167 x 167 > 165 x 165 > 163 x 163 > 161 x 161 > 159 x 159 > 157 x 157 > 155 x 155 > 153 x 153 > 151 x 151 > 149 x 149 > 147 x 147 > 145 x 145 > 143 x 143 > 141 x 141 > 139 x 139 > 137 x 137 > 135 x 135 > 133 x 133 > 131 x 131 > 129 x 129 > 127 x 127 > 125 x 125 > 123 x 123 > 121 x 121 > 119 x 119 > 117 x 117 > 115 x 115 > 113 x 113 > 111 x 111 > 109 x 109 > 107 x 107 > 105 x 105 > 103 x 103 > 101 x 101 > 99 x 99 > 97 x 97 > 95 x 95 > 93 x 93 > 91 x 91 > 89 x 89 > 87 x 87 > 85 x 85 > 83 x 83 > 81 x 81 > 79 x 79 > 77 x 77 > 75 x 75 > 73 x 73 > 71 x 71 > 69 x 69 > 67 x 67 > 65 x 65 > 63 x 63 > 61 x 61 > 59 x 59 > 57 x 57 > 55 x 55 > 53 x 53 > 51 x 51 > 49 x 49 > 47 x 47 > 45 x 45 > 43 x 43 > 41 x 41 > 39 x 39 > 37 x 37 > 35 x 35 > 33 x 33 > 31 x 31 > 29 x 29 > 27 x 27 > 25 x 25 > 23 x 23 > 21 x 21 > 19 x 19 > 17 x 17 > 15 x 15 > 13 x 13 > 11 x 11 > 9 x 9 > 7 x 7 > 5 x 5 > 3 x 3 > 1 x 1

## How are kernels initialized?
- Kernals are randomly initialzed between 0 to 1 [0, 1)
- if the kernels are initialized with all zero, we wont get any feature to analyze.
Example:
 Imput image                       Kernel                        output image
 [[77,51,61],						[[0,0,0],				        [[0,0,0],
[90,80,40],                           [0,0,0],        =>           [0,0,0],
[132,156,77]]                      [0,0,0]]                       [0,0,0]]

- If we keep the kernal values as all 1, we get output same as image
 Imput image                       Kernel                        output image
 [[77,51,61],						[[1,1,1],				        [[77,51,61],
[90,80,40],                           [1,1,1],        =>           [90,80,40],
[132,156,77]]                      [1,1,1]]                       [132,156,77]]
- The initialisation of kernel can be random (mode of initialisation is not important) as CNN have back propagation to regulate the kernel value to perform better feature extraction after every iteration in the training period


## What happens during the training of a DNN?
- Deep Neural Networks (DNNs) are typically Feed Forward Networks (FFNNs) in which data flows from the input layer to the output layer without going backward
- Its a layered architecure 
- edges & gradients 
- Patterns 
- Texture parts of objects, Objects I.e edges and gradients 
- Combination of edges and gradients convert into Patterns
- Combination of patterns into Texture
- Combination of Texture into Parts of object
- Combination of parts of object into object
- DNN Contains more layer of neurons to perform complex operation. It can be used as universal classifier as it a non polynomial activation function



INTRODUCTION:

Encoder Decoder structures which reduce the size of the data and then scale it up to a representative output are emerging as one of the most popular deep learning techniques. The basic intuition behind these techniques is to minimize patch size and then scale it up to required resolution. This begs the question – to what extent should an image be compressed to get back an acceptable output image while scaling up? We seek to answer this question through our work.

We would be implementing the above architecture and then modifying the number of layers – to increase/decrease the compression – and then comparing the output results. It’s about finding a sweet spot where we can compress without losing a lot of information.




OBJECTIVE :

To determine the most appropriate latent vector / representation for converting Thermal IR images to Grayscale images for the Thermal Visual Paired Dataset.



IMPLEMENTATION :

We have constructed various models which differ in their latent representation of the thermal images. Following are the latent represenations for the Models :

Model 1 - LATENT REPRESENTATION : 64 x 64 x 32

Model Architecture : 
c128,s1-4 ----> (Encoder) c64,s2-32 ------> (Decoder) dc128,s2-16 -------> c128,s1-4 

Model 2 - LATENT REPRESENTATION : 32 x 32 x 64

Model Architecture : 
c128,s1-4 ----> (Encoder) c64,s2-32 ; c32,s2-64 ------> (Decoder) dc64,s2-32 ; dc128,s2-16 -------> c128s1-4 

Model 3 - LATENT REPRESENTATION : 16 x 16 x 128

Model Architecture : 
c128,s1-4 ----> (Encoder) c64,s2-32 ; c32,s2-64 ; c16,s2-128 ------> (Decoder) dc32,s2-64 ; dc64,s2-32 ; dc128,s2-16  -------> c128s1-4 

Model 4 - LATENT REPRESENTATION : 8 x 8 x 256

Model Architecture : 
c128,s1-4 ----> (Encoder) c64,s2-32 ; c32,s2-64 ; c16,s2-128 ; c8,s2-256 ------> (Decoder) dc16,s2-128 ; dc32,s2-64 ; dc64,s2-32 ; dc128,s2-16  -------> c128s1-4 

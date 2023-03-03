# Video-Encoding-Quality-Estimation

The task sheet will cover topics related to video encoding, here we will only work with low-resolution videos, to demonstrate the methods that can be further used for larger resolution videos

Subtask 1: quality estimation

Let's assume, we successfully recorded a video in high quality (uncompressed, or visually lossless compressed), we post-processed the video (removed noise, perform video cutting, added audio), and we want to prepare it in a way that it can be used for delivery. Several possible distribution methods are thinkable, ranging from DVD, Bluray to HTTP-based streaming. For all methods, compression is required, because an uncompressed video signal would not fit the transmission medium of our choice. However there are plenty of possibilities to encode a given video, it is thus hard to know which one is best suitable. For such reasons, quality estimation methods, that originate from image quality, can be used to check whether a codec, an encoding setting, ... fits the required quality for transmission. Implement in the following task PSNR to estimate the video quality for the given encoded video.

Subtask 2: video encoding

 we will mainly implement the I-frame and P-frame handling, which can be seen as fundamental building blocks of a hybrid video codec.
 
 Subtask 2.1: I-frame compression;  
 
 1. we use  𝑌,𝐶𝑏,𝐶𝑟 color space of the given video / image signal, no chroma sub-sampling is performed
 2. we implement a jpeg compression variant, assuming a fixed block size (in our example  (8,8)), advanced video codecs use variable block sizes with macro blocks and hierarchies
3. we only handle 8 bit images/videos
4. we consider only a small resolution due to performance
5. we use the same quantization matrix for all  𝑌,𝐶𝑏,𝐶𝑟 channel planes

Subtask 2.2: motion estimation

we will implement a simple motion estimation approach to make our developed video codec complete. We will implement a simple variant of block-based motion estimation. This allows us to reuse some of our previously implemented helper methods.

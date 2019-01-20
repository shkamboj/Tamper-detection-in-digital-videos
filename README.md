# Tamper-detection-in-digital-videos
A peice of code for detecting scene breaks, frames insertion in digital videos using the edge detection algorithm.

## Motivation
Now days there are lots of software’s available in the market for editing
videos.
We are, through this project, trying to identify whether there is a tempering
done in the given video or not.
## Proposed Approach
1. A video is taken as input, and all the frames are extracted.
2. Edge detection is done for all the images using Sobel Edge detector.
3. After edge detection, dilation is done to widen the edges.
4. Then we check the change in edges between nth and (n + 1)th frame.
There will be some pixels which were 1 in nth frame but are 0 in (n+1)th frame. Those pixels are called exiting pixels. Similarly, the pixels which
turned to 1 from 0 are called entering pixels.
5. We’ll compute the edge change fraction by maximum of entering and
exiting pixel values, and store this value in an array.
6. Then the array will be plotted. If we get sudden peaks in the plot, it
means that video has been tampered.( if peak of order of 10^4 or more).


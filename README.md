# YOLO
  An image is divided into S x S pixels. For each pixel, several predefined BB are made.
  For each Bounding Box (BB) predicted – 
  A vector representation is –
  [Pc	 Bx  By  Bh  Bw  C1	C2  C3……Cn]
  
a.	Pc – Probability of object present in that BB

b.	Bx  By – position of BB with respect to that pixel – always between 0,0 and 1,1 

c.	Bh  Bw - height and width of that BB with respect to pixel.
    e.g. height is 5 units, so, it will be Bh = height of BB/Height of pixel
    Similarly, Bw is defined.

d.	C is the probability of an object. Subscript is a number given to that object. Suppose we consider COCO dataset, it has 80 objects so value of n will be 80. If first object is     dog, then C1 will show the probability of dog in that BB.

e.	In this way for one pixel, several BB are made and a tensor is created.
    Dimensions of tensor for an image:
    Channels x S x S x (B x 5 + C) 
  
   S = no. of pixels in an image in one dimension
    Channels = RGB or Gray
    B = no. of BB for each pixel
    5 = 4 dimensions and 1 Pc
    C = no. of objects to be predicted

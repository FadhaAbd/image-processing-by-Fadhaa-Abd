# image-processing-by-Fadhaa-Abd
image processing 
clc;

clear all;
close all;
a=imread('einstein.tif');
%Add Noise
f=imnoise(a,'gaussian',0.01,0.01);
J = imnoise(a,'salt & pepper',0.02);
s=medfilt2(J,[5,5]);
h=medfilt2(f,[5,5]);
o=fspecial('average',5);
g=imfilter(f,o);
k=fspecial('average',5);
d=imfilter(J,k);
figure,imshow(a),title('a');
figure,imshow(f),title('f');
figure,imshow(J),title('J');
figure,imshow(h),title('h');
figure,imshow(s),title('s');
figure,imshow(g),title('g');
figure,imshow(d),title('d');

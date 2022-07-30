# image-processing-by-Fadhaa-Abd
image processing 
clc;
clear all;
close all;
a=imread('einstein.tif');
%Add Noise
f=imnoise(a,'gaussian',0.01,0.01);
salt_pepper= imnoise(a,'salt & pepper',0.02);
s=medfilt2(salt_pepper,[5,5]);
h=medfilt2(f,[5,5]);
o=fspecial('average',5);
g=imfilter(f,o);
k=fspecial('average',5);
d=imfilter(salt_pepper,k);
figure,
 imshow(a),title('a');
 figure,
 subplot(2,2,1),imshow(f),title('f');
 subplot(2,2,2),imshow(salt_pepper),title('salt_pepper');
 subplot(2,2,3),imshow(h),title('h');
 subplot(2,2,4),imshow(s),title('s');
 figure,
 subplot(1,2,1),imshow(g),title('g');
 subplot(1,2,2),imshow(d),title('d');

# python_to_java
please help me translate code from python to java



import cv2
import numpy as np
tooth_image = cv2.imread('image.jpg')
#print(type(tooth_image), tooth_image.shape)
cv2.imshow('030',tooth_image)
tooth_image1 = cv2.cvtColor(tooth_image, cv2.COLOR_BGR2HSV_FULL)
cv2.imshow('00',tooth_image1)
low_dark = (0,0,0)
high_dark =(0, 53, 102)
only_tooth = cv2.inRange(tooth_image, low_dark, high_dark)
light_white = (255, 255, 255)
dark_white = (181, 153, 141)
# Применение белой маски
mask_white = cv2.inRange(tooth_image, light_white, dark_white)
final_mask = only_tooth + mask_white

#result = cv2.bitwise_and(tooth_image1, tooth_image1, mask=only_tooth)
#tooth_kont = tooth_image1 + only_tooth
cv2.imshow('Кариес', final_mask)
cv2.waitKey(0)

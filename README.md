# WSQ-15

from PIL import Image

def rotate_img(imagefile):
    orientation = int(input("State the degrees you want the image rotated (90, 180, 270):"))
    fileIm = Image.open(imagefile)
    if orientation == 90:
        fileIm.rotate(90).save('rotated90.png')
    elif orientation == 180:
        fileIm.rotate(180).save('rotated180.png')
    else:
        fileIm.rotate(270).save('rotated270.png')

def flip_img(imagefile):
    orientation = input("State the orientation you want the image (vertical, horizontal): ")
    fileIm = Image.open(imagefile)
    orientation = orientation.lower
    if orientation == "vertical":
        fileIm.transpose(Image.FLIP_TOP_BOTTOM).save('vertical.png')
    else:
        fileIm.transpose(Image.FLIP_LEFT_RIGHT).save('horizontal.png')

def resize_img(imagefile):
    width = int(input("New width in pixels: "))
    height = int(input("New height in pixels: "))
    fileIm = Image.open(imagefile)
    fileIm.resize((width, height)).save('resized.png')

filename = input("Write the file name of the image: ")
action = int(input("(1) Rotate  (2) Flip  (3) Resize"))
if action == 1:
    rotate_img(filename)
elif action == 2:
    flip_img(filename)
else:
    resize_img(filename)

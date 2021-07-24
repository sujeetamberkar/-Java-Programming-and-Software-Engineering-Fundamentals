Exercise 1 - Turn the chapel red. Write code that starts with the image “chapel.png” shown below on the left and turns the red part of every pixel to the highest red value possible, resulting in the image shown on the right.
 
var image = new SimpleImage("chapel.png");

for (var pixel of image.values())
    {
        pixel.setRed(255);
    }
print(image);

Exercise 2 - Remove all the red Write code that starts with the image “chapel.png” shown below on the left and removes all the red, resulting in the image shown on the right. You will notice that in the resulting image you will mostly see blue and green colors.
 
var image = new SimpleImage("chapel.png");

for (var pixel of image.values())
    {
        pixel.setRed(0);
    }
print(image);

Exercise 3 - Turn the eggs less red Write code that starts with the image “eastereggs.jpg” shown below on the left and reduces all the red pixel values that are greater than 70 to 70, resulting in the image shown on the right. You will notice that in the resulting image you will see some reddish colors but no bright reds.
 
var image = new SimpleImage("eastereggs.jpg");
// missing code
var red_val;
for (var pixel of image.values())
    {
        red_val=pixel.getRed()
        if (red_val >70)
        {
            pixel.setRed(70);
        }
    }
print(image);

Exercise 4 - Add Thick Black Line to Bottom of Owen Write code that starts with the image “astrachan.jpg” shown below on the left and replaces the bottom ten rows with black pixels, resulting in the image shown on the right. Note that the color black has a red value of 0, a green value of 0 and a blue value of 0. Also note that the pixel in the top left corner has x-value 0 and y-value 0
 
var image = new SimpleImage("astrachan.jpg");
// missing code
var Height=image.getHeight();
var blackStartY=Height-10;
for (var pixel of image.values())
    {
        if(pixel.getY()>=blackStartY)
        {
            pixel.setGreen(0);
            pixel.setRed(0);
            pixel.setBlue(0);
        }
    }
print(image);
Exercise 5 - Green square in top left corner Write code that starts with the image “chapel.png” shown below on the left, and replaces the top left corner with an all green square of size 50 by 50, resulting in the image on the right below.
 
var image = new SimpleImage("chapel.png");
// missing code
var change_startX=0;
var change_startY=0;
var change_endX=50;
var change_endY=50;
for(var pixel of image.values())
    {
        if(pixel.getY()<=50)
        {
            if(pixel.getX()<=50)
            {
                pixel.setGreen(255);
                pixel.setRed(0);
                pixel.setBlue(0);
            }
        }
    }
print(image);
Exercise 6 - Rectangle of any color in top right corner Write a function named topRightCorner that puts a rectangle of a specified color and size in the top right corner of the image. The function topRightCorner has six parameters named cornerWidth, cornerHeight, someImage, red, green, and blue. This function replaces the top right corner of the image someImage with a rectangle of height cornerHeight and width cornerWidth, and color that has red, green and blue numeric values.
 
function topRightCorner(cornerWidth,cornerHeight,someImage,red,green,blue) {
var pic_width=someImage.getWidth();
var pic_height=someImage.getHeight();
var change_startX=pic_width-cornerWidth;
var change_startY=0;
var change_endX=pic_width;
var change_endY=cornerHeight;

for(var pixel of someImage.values() )
    {
        if(pixel.getX()>=change_startX)
        {
            if(pixel.getY()<=cornerHeight)
            {
                pixel.setRed(red);
                pixel.setGreen(green);
                pixel.setBlue(blue)
            }
        }
    }
return someImage;
}
var picture = new SimpleImage("chapel.png");
var result = topRightCorner(30, 60, picture, 255, 255, 0);
print(result);
var picture2 = new SimpleImage("smalllion.jpg");
var result2 = topRightCorner(125, 20, picture2, 255, 0, 0);
print(result2);



Exercise 7 - Changes in Red Write the function named changeRed that draws a rectangle of width 256 showing all the changes of the color red, from left to right repeatedly, while blue and green are both set to 0. With height set to 200, the resulting image is shown here
  
// write your code here
function changeRed(width, height) {
var picture = new SimpleImage(width, height);
var red = 0;
for(pixel of picture.values())
//var cnt=0
    {
        if(pixel.getX()==red)
        {
            pixel.setRed(red);
        }
        else{
            red=0
        }
        red=red+1;
    }
return picture;
}
var result = changeRed(256,200);
print(result);



Part 1 
Write a JavaScript program that modifies an image by putting three vertical stripes on it - a red 
stripe on the left one third, a green stripe in the middle, and a blue stripe on the right one third. 
For example, if your program ran on Drew’s picture shown on the left, the resulting image would 
have red, green and blue vertical stripes as shown in the image on the right

// write your code here 
var image = new SimpleImage("hilton.jpg"); 
var width=image.getWidth(); 
var redStart=0; 
var endRed=width/3; 
endRed=Math.floor(endRed); 
var startGreen=endRed+1; 
var endGreen=startGreen+endRed; 
var startBlue=endGreen+1; 
var endBlue = width; 
for (pixel of image.values()) 
    { 
        if(pixel.getX()<=endRed) 
            { 
                pixel.setRed(255); 
            } 
        else  
        { 
            if(pixel.getX()<=endGreen) 
            { 
                pixel.setGreen(255); 
            } 
            else  
            { 
                pixel.setBlue(255); 
            } 
             
        } 
    } 
print(image); 


Part 2 
Write a JavaScript function named swapRedGreen with one parameter pixel (representing a 
single pixel). This function should swap the red and green values of the pixel. For example, if you 
have a pixel with red = 255, green = 100, blue = 150, after calling swapRedGreen on that pixel its 
new RGB values would be red = 100, green = 255, blue = 150
function swapRedGreen (pixel) 
{ 
    var red_val=pixel.getRed(); 
    var green_val=pixel.getGreen(); 
    pixel.setGreen(red_val); 
    pixel.setRed(green_val); 
    return pixel; 
} 
var image= new SimpleImage("eastereggs.jpg"); 
for(var pixel of image.values()) 
{ 
    pixel=swapRedGreen(pixel); 
} 
print(image);


Part 3 
Write code to change the Duke blue devil (the image below on the left) to be yellow (as in the 
image below on the right)


var img = new SimpleImage("duke_blue_devil.png"); 
for(var pixel of img.values()){ 
if(pixel.getRed()<255){ 
pixel.setRed(255) 
pixel.setGreen(255) 
pixel.setBlue(0) 
} 
} 
print(img);
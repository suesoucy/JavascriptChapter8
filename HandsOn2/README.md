In this project you will write code defining objects for balls bouncing within a container. When a ball hits the container side it will rebound, and the container will shift in the direction of  the balls velocity. Each instance of the ball object includes properties for the ball’s radius, horizontal and vertical position, and horizontal and vertical velocity. The container object will have properties defining its width, height, and position. New balls with random velocity are added to the center of the container by clicking a New Ball button. A preview of the completed project is shown in figure8-35. 
1. Use your code editor to open the project08-02.html and project08-02_txt.js. Files from the js08project02 folder. Enter your name and the date in the comment  section of each file and save them as project08-02.html and project08-02.js .
2. Go to the project08-02.html file and in your code editor link the page to the project08-02.js file, deferring the script until after the page loads. Close the file and save changes.
3. Return to the project08-02.js file in your code editor. Directly below the Object Code comment create an object literal named box with its width and height properties equal to BOX_WIDTH and BOX_HEIGHT and its xPos and yPos properties equal to 0.
4. Create a constructor function for the ball class. The constructor function has a single parameter named sized. Within the constructor function set the value of the radius property to size and the xPos, yPos, xVelocity, and yVelocity properties to null.
5. Create the moveWithin() method of the ball object class prototype that runs an anonymous function with container as its only parameter. The purpose of this method is to move the ball within the container, bouncing it off the container sides. Within the anonymous function do the following:
    - Set the top and left positions of the ball by creating the ballTop variable equal to this.yPos and the ballLeft variable equal to this.xPos. 
    - Set the bottom and left positions of the ball by creating the ballBottom variable equal to this.yPos and the this.radius and the ballRight variable equal to this.xPos + this.radius. 
    - If ballTop is less than zero or ballBottom is greater than container.height, then bounce the ball vertically by (i) increasing container.yPos by the value of this.yVelocity and (ii) setting this.yVelocity= -this.yVelocity. 
    - If ballLeft is less than zero or ballRight is greater than container.width, then bounce the ball horizontally by (i) increasing container.xPos by the value of this.xVelocity and (ii) setting this.xVelocity= -this.xVelocity.
    - Move the ball within the container by increasing the value of this.yPos by this.yVelocity and by increasing the value of this.xPos by this.xVelocity.
6. Scroll down to the Interface Code section and within the onClick event handler for the addBall button add the code described in steps 7 and 8. 
7. Create an instance of a ball object with the following properties:
    - Store an instance of the ball object in a variable named newBall with a size value equal to BALL_RADIUS. 
    - Center the newBall within the container by setting the yPos property to ( BOX_Height - BALL_RADIUS) /2 and the xPos property to (BOX_WIDTH - BALL_RADIUS) /2.
    - Give newBall an initial random velocity by calling the r and () function, setting the value of the yVelocity and xVelocity properties to rand (-10,10).
8. Animate the motion of newBall by calling the window.setInterval() method. Within the method, run the following code in an anonymous function every 25 milliseconds: 
    - Apply the moveWithin() method to the newBall with box as the value of the container parameter.
    - Move the image of the ball by setting ballImage.style.top equal to newBall.yPos + “px” and ballImage.style.left equal to newBall.xPos + “px”. 
    - Shake the image of the container by settings boxImage.style.top equal to box.yPos + “px” and boxImage.style.left equal to box.xPos + “px”. 
9. Save your changes to file and then load project08-02.html in your browser. 
10. Verify that you can add new balls to the container by clicking the Add Ball button and that the balls bounce off the sides, shaking the container. 


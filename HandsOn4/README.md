
In this project you will explore  how to retrieve text data from a ISON file and display that data in a web table. The first few lines of the ISON file containing a staff directory is shown in figure8-37. In this file there is a single root object named directory containing an array of objects with each object containing key:value pairs for the employee id, first name, last name, position, department, email address, and phone number. To iterate through these properties, you will use a for in loop with the following general form 
			For (let prop in object) 
			{commands}
Where prop references the properties associated with object and commands are the commands applied to each key:value pair in the object. Figure 8-38 shows the final version of the web table you will create for this project. 

1. Use your code editor to open the project08-04_txt.html and project08-04_txt.js files from the js08project04 folder. Enter your name and the date in the comment section of each file and save them as project08-04.html and project08-04.js. 
2. Go to the project08-04.html file in your code editor and link the page to the project08-04.js file deferring the script until after the page loads. Close the file, saving your changes. 
3. Return to the project08-04.js file in your code editor. Some of the code to create the app has already been entered for you. Go to the onload event handler for the fr (file reader) variable and add the following code: 
    - Add a command to convert the contents of the JSON data in fr.result into an object named staff.
    - Call the makeStaffTable() function using staff as the parameter value.
4. Go to the makeStaffTable() function and add the commands described in steps 5,6, and 7.
5. Create a table row containing the property names stored in the JSON file using the properties from the first directory entry. Create a for in loop for the object stored in staff.directory(0) and add the following commands to the loop: 
    - Use the document.createElement() method to create a th element named headerCell 
    - Store prop as the text content of headerCell.
    - Use the appendChild() method to append headerCell to the headerRow object.
    - After the for in loop completes, append headerRow to the staffTable object.
6. Next, create table rows containing the property values for each entry in the directory array. Add a for loop that loops through the items of staff.directory. Within the for loop do the following:
    - Create an element node for the tr element and store it in th tableRow variable. 
    - Create a for in loop for the properties listed in the staff.directory(i). For each property do the following: (i) create an element node for the td element and store it in the tableCell variable;(ii) store the value of staff.directory(i) (prop) as the text content of tableCell;(iii) append tableCell to the tableRow object.
    - After the for in loop completes, append tableRow to the staffTable object.
7. After the for loop is finished, use the appendChild() method to append staffTable to the containerBox object.
8. Save your changes to the file and then load project08-04.html  in your web browser.
9. Click the Choose File button and open the staff.json file from the js08project04 folder. Verify that the contents of the file are converted into a web table with the property names in the first table row and the property values for each directory entry shown in subsequent table rows. 

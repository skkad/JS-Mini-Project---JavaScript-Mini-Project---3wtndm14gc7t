# html-css-js-project
# Calculator

As we know, the Calculator is a portable device used in our daily life to perform various mathematical functions such as addition, subtraction, multiplication, division, root, etc. However, we have scientific or sophisticated calculators used to solve complex tasks such as trigonometry functions, degrees, exponential operators, log functions, hyperbolic functions, square root, and so on. In this topic, we will create a calculator program in JavaScript.

# HTML file 
    We created a  <div class="formstyle"> which contains <form> and <center> tags which divides the claculator in two parts.
    <form> tag shows the key pressed and result and <center> tag is used to center-align the text which contains <table> tag in it.

    Table contains 5-rows and 4-columns.
    Each column has <input> tag with type="button" and onclick event handler.

    Operater buttons contains insert()
    Back button contains backspace()
    Equal button contains equal()

# CSS file
    1.To create outer layer of calculator we style class ".formstyle" with style propertites such as -------------
      width and height of 300px and 330px having background of grey color and having margin of 20px on top and bottom and auto for left and right side.Border of 3px solid with skyblue color.
       
    2.H1 tag is styled with background color of "skyblue" and padding of 23px.

    3.Every input tag turns green when hover.
    
    4.Every button on calculator should contain style properties as width and height of 50px each.Font-size of 25px and background color of "red" 
      with margin of 2px. It has cursor property as "pointer".    
   
        
    5.Form tag contains input tag with class as ".textview" . It is used to display the numbers, operations and results.
      It has width of 223px and magin and padding of 5px with fontsize of 25px and having background color of light-green.

# JS file
    
    Use insert() function to insert the number in textview.

    Use equal() function to return the result based on passed values.Inside eqaul use eval() method.

    Here, we create a backspace() function to remove the number at the end of the numeric series in textview.
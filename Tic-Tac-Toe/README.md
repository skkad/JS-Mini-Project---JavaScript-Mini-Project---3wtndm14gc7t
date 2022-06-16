# html-css-js-project-boilerplate
# Tic Tac Toe Game

1. Firstly we will create <header> tag and style it with by any background color of your choice and make text aling as center,font-size 27px and  
   padding 23px and font-family of 'Roboto', sans-serif.

2. Create div and give it class as "gameCntainer" inside that create its two child divs and give them class as "container" and "gameInfo" .
   
3. Inside div with class as "container" create 9 divs with class as "box" and each divs should contain <span> with class as "boxtext".
   Give dispaly property as grid for this and to create three rows and columns use grid-template-rows property "repeat(3,10vw)" ,similarly do it for columns as well.

4. On "box" class ww will give styling for borders and display property as "flex" and to center we use justify-content and align-items. 
   If we hover on any cell it should change its color to rgb(242, 234, 250).   

5. Currently the box is looking like a table to convert it into like "tic tac toe" board we will use utility class as br-0(border-right) ,
   bl-0(border-left),bt-0(border-top) and bb-0(border-bottom) all these border of particular side will be set to 0. These class will be given to divs with class as "box".

6. The div with class as "gameInfo" has a <h1> tag,div with class "imageBox" and div which has reset button .



# Now Javascript 

1. Function to change the turn , set variable turn = "X".
    const changeTurn = ()=>{
        return turn === "X"? "0": "X"
    }

2. To use all audio files create varibles and use Audio() to include them.

3. Function to check for win, create function checkWin().
   a] let boxtext = document.getElementsByClassName('boxtext') , this selects element with class "boxtext" and creates array of these elements.
   b] Create array of possible winning situations as,    
    let wins = [
        [0, 1, 2, 5, 5, 0],
        [3, 4, 5, 5, 15, 0],
        [6, 7, 8, 5, 25, 0],
        [0, 3, 6, -5, 15, 90],
        [1, 4, 7, 5, 15, 90],
        [2, 5, 8, 15, 15, 90],
        [0, 4, 8, 5, 15, 45],
        [2, 4, 6, 5, 15, 135],
    ]
   c] Now we will run forEach loop on wins array,
     wins.forEach(e =>{
        if((boxtext[e[0]].innerText === boxtext[e[1]].innerText) && (boxtext[e[2]].innerText === boxtext[e[1]].innerText) && (boxtext[e[0]].innerText !== "") ){
            document.querySelector('.info').innerText = boxtext[e[0]].innerText + " Won"
            isgameover = true
            document.querySelector('.imgbox').getElementsByTagName('img')[0].style.width = "200px";
            document.querySelector(".line").style.transform = `translate(${e[3]}vw, ${e[4]}vw) rotate(${e[5]}deg)`
            document.querySelector(".line").style.width = "20vw";
        }
    })

4. Now we will create game logic,
   a] Select all elements with class as "box" ,we use Array.form() to create array of selected elements and iterate over it by using forEach loop.
   b] We will add event listner on span element that means on click it should do these things,
        if(boxtext.innerText === ''){
            boxtext.innerText = turn;
            turn = changeTurn();
            audioTurn.play();
            checkWin();
            if (!isgameover){
                document.getElementsByClassName("info")[0].innerText  = "Turn for " + turn;
            } 
        }

5. Add on click event listner to reset button,
   a] To reset all the cell back to empty,
        let boxtexts = document.querySelectorAll('.boxtext');
        Array.from(boxtexts).forEach(element => {
            element.innerText = ""
        });            
   b]  Set all conditions as it was at start of the game,
        turn = "X"; 
        isgameover = false
        document.querySelector(".line").style.width = "0vw";
        document.getElementsByClassName("info")[0].innerText  = "Turn for " + turn;
        document.querySelector('.imgbox').getElementsByTagName('img')[0].style.width = "0px"    
# cs151

/* ------------------------------------------------
 prog2memory.cpp
 
 Program #2: Memory game of guessing which X or O changed.
 Class: CS 141
 Author: Cynthia Lopez
 Lab: Tues 11am
 System:  C++ Mac Xcode
 
 Grading Rubric:
 
 50 Execution points
 5 Displays header info on screen when run
 5 Displays instructions
 5 Output is formatted as shown in sample output
 3 Handles both upper and lower case input
 2 Input of 'x' in first prompt exits program
 5 Input can be adjacent or have spaces between them
 15 Displayed boards all have odd parity in rows and columns
 5 Repeated input of 'r' gives new valid random board each time
 5 Gives appropriate end of program messages
 
 45 Programming Style (Given only if program runs substantially correctly)
 5 Program naming convention is followed
 10 Meaningful identifier names
 10 Comments: Has header.  Comments on each block of code
 10 Appropriate data and control structures (-20 if using arrays or strings)
 10 Code Layout: Appropriate indentation and blank lines
 ------------------------------------------------
 */

#include <iostream>
#include <ctime>
#include <cstdlib>
#include <cmath>
using namespace std;

//initalizing char variables, which are going to be used globally
char p0,p1,p2,p3,p4,
     p5,p6,p7,p8,p9, p10,
     p11,p12,p13,p14,
     p15,p16,p17,p18,
     p19,p20,p21,p22,
     p23,p24,p25,p26,
     p27,p28,p29,p30,
     p31,p32,p33,p34,
             p35;



//This function allows the extra space needed, once the user inputs the value they want to change.
void extraSpace () {
    cout << endl << endl << endl << endl << endl << endl << endl << endl << endl << endl;
    cout << endl << endl << endl << endl << endl << endl << endl << endl << endl << endl;
    cout << endl << endl << endl << endl << endl;
}

//This function displays the board since the p0-p35 are global variables which will change throughout the project.
void display()
{
    cout << "     1 2 3 4 5 6 \n";
    cout << "   - - - - - - - - \n";
    cout<< "A  | " << p0 << " " << p1 << " " << p2 << " " << p3 << " " << p4 << " " << p5 << " | A\n";
    cout<< "B  | " << p6 << " " << p7 << " " << p8 << " " << p9 << " " << p10 << " " << p11 << " | B\n";
    cout<< "C  | " << p12 << " " << p13 << " " << p14 << " " << p15 << " " << p16 << " " << p17 << " | C\n";
    cout<< "D  | " << p18 << " " << p19 << " " << p20 << " " << p21 << " " << p22 << " " << p23 << " | D\n";
    cout<< "E  | " << p24 << " " << p25 << " " << p26 << " " << p27 << " " << p28 << " " << p29 << " | E\n";
    cout<< "F  | " << p30 << " " << p31 << " " << p32 << " " << p33 << " " << p34 << " " << p35 << " | F\n";
}
//This function allows the char p0-p35 to change when it is called.
void refresh () {
    srand(time(0));
    //will keep track of x's in the rows, x1 meaning the x's in row 1, x2 row 2, etc.
    int rowX1 = 0;
    int rowX2 = 0;
    int rowX3 = 0;
    int rowX4 = 0;
    int rowX5 = 0;
    //will count how many x's in the col
    int col1 = 0;
    int col2 = 0;
    int col3 = 0;
    int col4 = 0;
    int col5 = 0;
    int col6 = 0;

//row 1 randomize to only 0-9
    p0 = (rand()% 10)+48;
    p1 = (rand()% 10)+48;
    p2 = (rand()% 10)+48;
    p3 = (rand()% 10)+48;
    p4 = (rand()% 10)+48;
    p5 = (rand()% 10)+48;
//row 2 randomize to only 0-9
    p6 = (rand()% 10)+48;
    p7 = (rand()% 10)+48;
    p8 = (rand()% 10)+48;
    p9 = (rand()% 10)+48;
    p10 = (rand()% 10)+48;
    p11 = (rand()% 10)+48;
//row 3 randomize to only 0-9
    p12 = (rand()% 10)+48;
    p13 = (rand()% 10)+48;
    p14 = (rand()% 10)+48;
    p15 = (rand()% 10)+48;
    p16 = (rand()% 10)+48;
    p17 = (rand()% 10)+48;
//row 4 randomize to only 0-9
    p18 = (rand()% 10)+48;
    p19 = (rand()% 10)+48;
    p20 = (rand()% 10)+48;
    p21 = (rand()% 10)+48;
    p22 = (rand()% 10)+48;
    p23 = (rand()% 10)+48;
//row 5 randomize to only 0-9
    p24 = (rand()% 10)+48;
    p25 = (rand()% 10)+48;
    p26 = (rand()% 10)+48;
    p27 = (rand()% 10)+48;
    p28 = (rand()% 10)+48;
    p29 = (rand()% 10)+48;
//row 6 (special row to manuiplate)
    p30 = (rand()% 10)+48;
    p31 = (rand()% 10)+48;
    p32 = (rand()% 10)+48;
    p33 = (rand()% 10)+48;
    p34 = (rand()% 10)+48;
    p35 = (rand()% 10)+48;
    
    
//ROW 1 ROW 1 ROW 1 ROW 1 ROW 1 ROW 1 ROW 1
    //p0 will print O if even, X if odd
    if (p0 % 2 == 0) {
        p0 = 'O';
    }
    else {
        p0 = 'X';
        rowX1 = rowX1 + 1; //row of X's
        col1 = col1 + 1; //col of X's
    }
    
    //p1 will print O if even, X if odd
    if (p1 % 2 == 0) {
        p1 = 'O';
    }
    else {
        p1 = 'X';
        rowX1 = rowX1 + 1; //row of X's
        col2 = col2 + 1; //col of X's
    }
    
    //p2 will print O if even, X if odd
    if (p2 % 2 == 0) {
        p2 = 'O';
    }
    else {
        p2 = 'X';
        rowX1 = rowX1 + 1; //row of X's
        col3 = col3 + 1; //col of X's
    }
    //p3 will print O if even, X if odd
    if (p3 % 2 == 0)
    {
        p3 = 'O';
    }
    else {
        p3 = 'X';
        rowX1 = rowX1 + 1; //row of X's
        col4 = col4 + 1; //col of X's
    }
    //p4 will print O if even, X if odd
    if (p4 % 2 == 0) {
        p4 = 'O';
    }
    else {
        p4 = 'X';
        rowX1 = rowX1 + 1; //row of X's
        col5 = col5 + 1; //col of X's
    }
    //p5 will print O if even, X if odd
    if (rowX1 % 2 == 0) {
        p5 = 'X';
        col6 = col6 + 1; //col of X's
    }
    else {
        p5 = 'O';
    }
    
// ROW 2 ROW 2 ROW 2 ROW 2 ROW 2 ROW 2 ROW 2
    //p6 will print O if even, X if odd
    if (p6 % 2 == 0) {
        p6 = 'O';
    }
    else {
        p6 = 'X';
        rowX2 = rowX2 + 1; //row of X's
        col1 = col1 + 1; //col of X's
    }
    //p7 will print O if even, X if odd
    if (p7 % 2 == 0) {
        p7 = 'O';
    }
    else {
        p7 = 'X';
        rowX2 = rowX2 + 1; //row of X's
        col2 = col2 + 1; //col of X's
    }
    //p8 will print O if even, X if odd
    if (p8 % 2 == 0) {
        p8 = 'O';
    }
    else {
        p8 = 'X';
        rowX2 = rowX2 + 1; //row of X's
        col3 = col3 + 1; //col of X's
    }
    //p9 will print O if even, X if odd
    if (p9 % 2 == 0) {
        p9 = 'O';
    }
    else {
        p9 = 'X';
        rowX2 = rowX2 + 1; //row of X's
        col4 = col4 + 1; //col of X's
    }
    //p10 will print O if even, X if odd
    if (p10 % 2 == 0) {
        p10 = 'O';
    }
    else {
        p10 = 'X';
        rowX2 = rowX2 + 1; //row of X's
        col5 = col5 + 1; //col of X's
    }
    //p11 will print x if row is even, o if odd
    if (rowX2 % 2 == 0) {
        p11 = 'X';
        col6 = col6 + 1; //col of X's
    }
    else {
        p11 = 'O';
    }
    
// ROW 3 ROW 3 ROW 3 ROW 3 ROW 3 ROW 3 ROW 3
    //p12 will print O if even, X if odd
    if (p12 % 2 == 0) {
        p12 = 'O';
    }
    else {
        p12 = 'X';
        rowX3 = rowX3 + 1; //row of X's
        col1 = col1 + 1; //col of X's
    }
    //p13 will print O if even, X if odd
    if (p13 % 2 == 0) {
        p13 = 'O';
    }
    else {
        p13 = 'X';
        rowX3 = rowX3 + 1; //row of X's
        col2 = col2 + 1; //col of X's
    }
    //p14 will print O if even, X if odd
    if (p14 % 2 == 0) {
        p14 = 'O';
    }
    else {
        p14 = 'X';
        rowX3 = rowX3 + 1; //row of X's
        col3 = col3 + 1; //col of X's
    }
    //p15 will print O if even, X if odd
    if (p15 % 2 == 0) {
        p15 = 'O';
    }
    else {
        p15 = 'X';
        rowX3 = rowX3 + 1; //row of X's
        col4 = col4 + 1; //col of X's
    }
    //p16 will print O if even, X if odd
    if (p16 % 2 == 0) {
        p16 = 'O';
    }
    else {
        p16 = 'X';
        rowX3 = rowX3 + 1; //row of X's
        col5 = col5 + 1; //col of X's
    }
    //p17 will print O if even, X if odd
    if (rowX3 % 2 == 0) {
        p17 = 'X';
        col6 = col6 + 1; //col of X's
    }
    else {
        p17 = 'O';
    }
    
// ROW 4 ROW 4 ROW 4 ROW 4 ROW 4 ROW 4 ROW 4
    //p18 will print O if even, X if odd
    if (p18 % 2 == 0) {
        p18 = 'O';
    }
    else {
        p18 = 'X';
        rowX4 = rowX4 + 1; //row of X's
        col1 = col1 + 1; //col of X's
    }
    //p19 will print O if even, X if odd
    if (p19 % 2 == 0) {
        p19 = 'O';
    }
    else {
        p19 = 'X';
        rowX4 = rowX4 + 1; //row of X's
        col2 = col2 + 1; //col of X's
    }
    //p20 will print O if even, X if odd
    if (p20 % 2 == 0) {
        p20 = 'O';
    }
    else {
        p20 = 'X';
        rowX4 = rowX4 + 1; //row of X's
        col3 = col3 + 1; //col of X's
    }
    //p21 will print O if even, X if odd
    if (p21 % 2 == 0) {
        p21 = 'O';
    }
    else {
        p21 = 'X';
        rowX4 = rowX4 + 1; //row of X's
        col4 = col4 + 1; //col of X's
    }
    //p22 will print O if even, X if odd
    if (p22 % 2 == 0) {
        p22 = 'O';
    }
    else {
        p22 = 'X';
        rowX4 = rowX4 + 1; //row of X's
        col5 = col5 + 1; //col of X's
    }
    //p23 will print x if even amount of x, O if odd
    if (rowX4 % 2 == 0) {
        p23 = 'X';
        col6 = col6 + 1; //col of X's
    }
    else {
        p23 = 'O';
    }
    
// ROW 5 ROW 5 ROW 5 ROW 5 ROW 5 ROW 5 ROW 5
    //p24 will print O if even, X if odd
    if (p24 % 2 == 0) {
        p24 = 'O';
    }
    else {
        p24 = 'X';
        rowX5 = rowX5 + 1; //row of X's
        col1 = col1 + 1; //col of X's
    }
    //p25 will print O if even, X if odd
    if (p25 % 2 == 0) {
        p25 = 'O';
    }
    else {
        p25 = 'X';
        rowX5 = rowX5 + 1; //row of X's
        col2 = col2 + 1; //col of X's
    }
    //p26 will print O if even, X if odd
    if (p26 % 2 == 0) {
        p26 = 'O';
    }
    else {
        p26 = 'X';
        rowX5 = rowX5 + 1; //row of X's
        col3 = col3 + 1; //col of X's
    }
    //p27 will print O if even, X if odd
    if (p27 % 2 == 0) {
        p27 = 'O';
    }
    else {
        p27 = 'X';
        rowX5 = rowX5 + 1; //row of X's
        col4 = col4 + 1; //col of X's
    }
    //p28 will print O if even, X if odd
    if (p28 % 2 == 0) {
        p28 = 'O';
    }
    else {
        p28 = 'X';
        rowX5 = rowX5 + 1; //row of X's
        col5 = col5 + 1; //col of X's
    }
    //p23 will print x if even amount of x, O if odd
    if (rowX5 % 2 == 0) {
        p29 = 'X';
        col6 = col6 + 1; //col of X's
    }
    else {
        p29 = 'O';
    }
    
// ROW 6 ROW 6 ROW 6 ROW 6 ROW 6 ROW 6
    //We will manipulate this row to make the board an odd parity. So depends on # of x's in rows,
    //if even #, will print out another x to make, if odd will be 'o'
    if (col1 % 2 == 0) {
        p30 = 'X';
    }
    else {
        p30 = 'O';
    }
    //col 2, # of x will be odd
    if (col2 % 2 == 0) {
        p31 = 'X';
    }
    else {
        p31 = 'O';
    }
    //col 3, # of x will be odd
    if (col3 % 2 == 0) {
        p32 = 'X';
    }
    else {
        p32 = 'O';
    }
    //col 4, # of x will be odd
    if (col4 % 2 == 0) {
        p33 = 'X';
    }
    else {
        p33 = 'O';
    }
    //col 5, # of x will be odd
    if (col5 % 2 == 0) {
        p34 = 'X';
    }
    else {
        p34 = 'O';
    }
    //col 6, # of x will be odd
    if (col6 % 2 == 0) {
        p35 = 'X';
    }
    else {
        p35 = 'O';
    }
//once all char values have been declared, we can use the display() function to display the board.
    display();
    
}

int main() {
    //initializing user input for two inputs, and the guesses one would make as part of the game
    char firstL;
    char secondL;
    char guess1;
    char guess2;
    //loop iteration for a while loop
    int loop = 0;
//This is the introduction of the game
    //it will explain the rules of the game and how to play and move forward.
    cout << "Author:  Cynthia Lopez \n";
    cout << "Class:   CS 141, Spring 2018 \n";
    cout << "Lab:     Tue 11am \n";
    cout << "Program: #2, Memory Game \n";
    cout << endl;
    cout << "Welcome to the memory game! \n";
    cout << endl;
    cout << "Look away from the board and have a helper enter r \n";
    cout << "to randomize the board until they have a random board that they like. \n";
    cout << "Then you glance at it and try toimprint it in your mind and look away. \n";
    cout << "Your helper will then select a single piece to be flipped by choosing \n";
    cout << "its row and column. The changed board is then displayed.  \n";
    cout << "You then must try to guess which one it was. Enter x to exit the program. \n";
    cout << endl << endl;
    
    
    
    
    refresh (); //this will generate the first board, later they can decide if they would like to change it.
    //asking user to enter either r,x, or a row and colummn to change from x to o, or o to x
    cout << endl;
    cout << "Enter r to randomize to board, or row and column to change a value ->";
    
    cin >> firstL;  //take in the first char, r, x, or A,B,C,D,E,F
    cout << endl;
    
    while ( loop < 1 ) {
        // when r is pressed then it will call the function refresh to regenerate a new board until desire
        if (firstL == 'r' || firstL == 'R') {
            refresh();
            cout << endl;
            cout << "Enter r to randomize to board, or row and column to change a value ->";
            cin >> firstL;
            cout << endl << endl;
            
            continue; //iterates the next loop (you can also note that loop is not being added to 1 as they can press r as many times.
        }
        //will exit game
        else if (firstL == 'X' || firstL == 'x') {
            cout << "GoodBye." << endl;
            exit (0);
        }

//p0 ....p5 for row A1 to A6
        else if (firstL == 'A' || firstL == 'a')
        {
            //loop is being added to 1 so that the while loop stops
            loop = loop + 1;
            cin >> secondL; // takes in the second char
            if (secondL == '1'){
                //if p0 is x, user changes it to o
                if (p0 == 'X') {
                    p0 = 'O';
                }
                else {
                    p0 = 'X';
                }
            }
            else if (secondL == '2'){
                //p1 is x, user changes it to o, else x
                if (p1 == 'X') {
                    p1 = 'O';
                }
                else {
                    p1 = 'X';
                }
            }
            else if (secondL == '3'){
                //p2 is x, user changes it to o, else x
                if (p2 == 'X') {
                    p2 = 'O';
                }
                else {
                    p2 = 'X';
                }
            }
            else if (secondL == '4'){
                //p3 is x, user changes it to o, else x
                if (p3 == 'X') {
                    p3 = 'O';
                }
                else {
                    p3 = 'X';
                }
            }
            else if (secondL == '5'){
                //p3 is x, user changes it to o, else x
                if (p4 == 'X') {
                    p4 = 'O';
                }
                else {
                    p4 = 'X';
                }
            }
            else //if (secondL == '6')
              //p5 is x, user changes it to o, else x
            {
                if (p5 == 'X') {
                    p5 = 'O';
                }
                else {
                    p5 = 'X';
                }
            }
            extraSpace (); // this will output 25 lines
            break; //if statement satisfied, then it will jump to the end of the loop
        }

//p6 ....p11 for row B1 to B6
        else if (firstL == 'B' || firstL == 'b')
            {
                loop = loop + 1; // +loop
                cin >> secondL; //takes in second char
                //p6 is x, user changes it to o, else x
                if (secondL == '1'){
                    if (p6 == 'X') {
                        p6 = 'O';
                    }
                    else {
                        p6 = 'X';
                    }
                }
                else if (secondL == '2'){
                    //p7 is x, user changes it to o, else x
                    if (p7 == 'X') {
                        p7 = 'O';
                    }
                    else {
                        p7 = 'X';
                    }
                }
                else if (secondL == '3'){
                    //p8 is x, user changes it to o, else x
                    if (p8 == 'X') {
                        p8 = 'O';
                    }
                    else {
                        p8 = 'X';
                    }
                }
                else if (secondL == '4'){
                    //p9 is x, user changes it to o, else x
                    if (p9 == 'X') {
                        p9 = 'O';
                    }
                    else {
                        p9 = 'X';
                    }
                }
                else if (secondL == '5'){
                    //p10 is x, user changes it to o, else x
                    if (p10 == 'X') {
                        p10 = 'O';
                    }
                    else {
                        p10 = 'X';
                    }
                }
                else //if (secondL == '6')
                {
                    if (p11 == 'X') {
                        p11 = 'O';
                    }
                    else {
                        p11 = 'X';
                    }
                }
                extraSpace ();
                break;
            }
            
 //p12 ....p17 for row C1 to C6
            else if (firstL == 'C' || firstL == 'c')
            {
                loop = loop + 1;
                cin >> secondL;
                if (secondL == '1'){
                    if (p12 == 'X') {
                        p12 = 'O';
                    }
                    else {
                        p12 = 'X';
                    }
                }
                else if (secondL == '2'){
                    
                    if (p13 == 'X') {
                        p13 = 'O';
                    }
                    else {
                        p13 = 'X';
                    }
                }
                else if (secondL == '3'){
                    
                    if (p14 == 'X') {
                        p14 = 'O';
                    }
                    else {
                        p14 = 'X';
                    }
                }
                else if (secondL == '4'){
                    
                    if (p15 == 'X') {
                        p15 = 'O';
                    }
                    else {
                        p15 = 'X';
                    }
                }
                else if (secondL == '5'){
                    
                    if (p16 == 'X') {
                        p16 = 'O';
                    }
                    else {
                        p16 = 'X';
                    }
                }
                else //if (secondL == '6')
                {
                    if (p17 == 'X') {
                        p17 = 'O';
                    }
                    else {
                        p17 = 'X';
                    }
                }
                extraSpace ();
                break;
            }
        
            
//p18 ....p23 for row B1 to B6
            else if (firstL == 'D' || firstL == 'd')
            {
                loop = loop + 1;
                cin >> secondL;
                if (secondL == '1'){
                    if (p18 == 'X') {
                        p18 = 'O';
                    }
                    else {
                        p18 = 'X';
                    }
                }
                else if (secondL == '2'){
                    
                    if (p19 == 'X') {
                        p19 = 'O';
                    }
                    else {
                        p19 = 'X';
                    }
                }
                else if (secondL == '3'){
                    
                    if (p20 == 'X') {
                        p20 = 'O';
                    }
                    else {
                        p20 = 'X';
                    }
                }
                else if (secondL == '4'){
                    
                    if (p21 == 'X') {
                        p21 = 'O';
                    }
                    else {
                        p21 = 'X';
                    }
                }
                else if (secondL == '5'){
                    
                    if (p22 == 'X') {
                        p22 = 'O';
                    }
                    else {
                        p22 = 'X';
                    }
                }
                else //if (secondL == '6')
                {
                    if (p23 == 'X') {
                        p23 = 'O';
                    }
                    else {
                        p23 = 'X';
                    }
                }
                extraSpace ();
                break;
            }
  //p24 ....p29 for row E1 to E6
            else if (firstL == 'E' || firstL == 'e')
            {
                loop = loop + 1;
                cin >> secondL;
                if (secondL == '1'){
                    if (p24 == 'X') {
                        p24 = 'O';
                    }
                    else {
                        p24 = 'X';
                    }
                }
                else if (secondL == '2'){
                    
                    if (p25 == 'X') {
                        p25 = 'O';
                    }
                    else {
                        p25 = 'X';
                    }
                }
                else if (secondL == '3'){
                    
                    if (p26 == 'X') {
                        p26 = 'O';
                    }
                    else {
                        p26 = 'X';
                    }
                }
                else if (secondL == '4'){
                    
                    if (p27 == 'X') {
                        p27 = 'O';
                    }
                    else {
                        p27 = 'X';
                    }
                }
                else if (secondL == '5'){
                    
                    if (p28 == 'X') {
                        p28 = 'O';
                    }
                    else {
                        p28 = 'X';
                    }
                }
                else //if (secondL == '6')
                {
                    if (p29 == 'X') {
                        p29 = 'O';
                    }
                    else {
                        p29 = 'X';
                    }
                }
                extraSpace ();
                break;
            }
//p30 ....p35 for row F1 to F6
            else if (firstL == 'F' || firstL == 'f')
            {
                loop = loop + 1;
                cin >> secondL;
                if (secondL == '1'){
                    if (p30 == 'X') {
                        p30 = 'O';
                    }
                    else {
                        p30 = 'X';
                    }
                }
                else if (secondL == '2'){
                    
                    if (p31 == 'X') {
                        p31 = 'O';
                    }
                    else {
                        p31 = 'X';
                    }
                }
                else if (secondL == '3'){
                    
                    if (p32 == 'X') {
                        p32 = 'O';
                    }
                    else {
                        p32 = 'X';
                    }
                }
                else if (secondL == '4'){
                    
                    if (p33 == 'X') {
                        p33 = 'O';
                    }
                    else {
                        p33 = 'X';
                    }
                }
                else if (secondL == '5'){
                    
                    if (p34 == 'X') {
                        p34 = 'O';
                    }
                    else {
                        p34 = 'X';
                    }
                }
                else //if (secondL == '6')
                {
                    if (p35 == 'X') {
                        p35 = 'O';
                    }
                    else {
                        p35 = 'X';
                    }
                }
                extraSpace ();
                break;
            }
        
        }
//once the user changes one of the values, then it will display after the loop
    display();
    cout << endl;
//Guesser will have to guess which variable was changed
    cout << "What piece do you think it was? ->";
    cin >> guess1 >> guess2;
    cout << endl;
    
    if ( (firstL == guess1) && (secondL == guess2) ) {
        //if guesser is correct, then it will print out congrats.
        cout << "*** Congratulations, you did it! ***" << endl << endl;
        cout << "Thank you for playing.  Exiting..." << endl << endl;
    }
    else {
        //if user is wrong, then it will print out the correct answer and exit game.
        cout << "Nope that was not right. The correct answer was: " << firstL << secondL << endl;
        cout << "Exiting..." << endl << endl;
    }
    
    return 0;
}

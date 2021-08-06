#include <iostream>
#include <cstdlib>
#include <time.h>
#include <windows.h>
#include <conio.h>
#define ROW 20
#define COL 50
using namespace std;

int goalx, pointx, pointy;
char lab[ROW][COL];
void initiate();
void print();
void pathGenerator(int i, int j);
void wallsGenerator();
void endingGenerator();
void play(int key);
using namespace std;

int main(int argc, char** argv) {
    
    srand(unsigned(time(NULL)));
    void initiate();
    int x = 1 + rand() % ROW - 2;
    wallsGenerator();
    endingGenerator();
    print();
    int key;
    pointx = x;
    pointy = 1;
    while(true) {
        key = getch();
        if(key == 27) break;
        else(
             
             play(key);
             if(lab[pointx][pointy + 1] == 'F') (
                cout << "Congratulations! You have completed the maze." << endl;
                break;
                        )
             
             )
        
        
    }
    system("pause");
    return 0;
    
}

void initiate() {
    for(int i = 0; i < ROW; i++)
    (
     for(int j = 0; j < COL; j++)
     (
      if(i == 0 || j == 0 || i == ROW - 1 || j == COL - 1) lab[i][j] = 'P';
      else lab[i][j] = ' ';
      )
     )
}

void print() {
    for(int i = 0; i < ROW; i++)
    (
     
     for(int j = 0; j < COL; j++)
     (
      if(lab[i][j] == '0' || lab[i][j] == 'P') cout << (char)177;
      else cout << lab[i][j];
      )
     cout << endl;
     )
}

void pathGenerator(int i, int j) {
    while(j != ROW - 2)
    (
     int a = rand() % 3;
     switch(a)
     (
      case 0;
        if(i + 1 != ROW - 1 && lab[i + 1][j] != 'O')
        (
         i++
         lab[i][1] = 'O';
         )
        break;
      case 1:
        if(i - 1 != 0 && lab[i - 1][j] != 'O')
        (`
         i--;
         lab[i][j] = 'O';
         )
        break;
      case 2:
        if(j+1 != COL - 1 && lab[i][j + 1] != 'O')
        (
         j++;
         lab[i][j] = 'O';
         if(j == COL - 2) lab[i][j] = 'F';
            )
      break;
         
         )
            ) // end of while
    goalx = i;
}
    
void pathGenerator() {
    int walls = 0;
    while(walls < 100)
    (
     int x = rand() % ROW;
     int y = rand() % COL;
     
     if (lab[x][y] == ' ')
     (
      walls++;
      int lim = 1 + rand() % 10;
      int value = 0;
      switch(rand() % 4)
      (
       case 0:
        
        while(lab[x][y] == ' ') // up movement
        (
         if(value == lim) break;
         value++;
         lab[x][y] = 'P';
         x--;
         )
        break;
       case 1:
       
        while(lab[x][y] == ' ') // down movement
       (
        if(value == lim)break;
        value++;
        lab[x][y] = 'P';
        x++;
        )
        break;
       case 2:
       
        while(lab[x][y] == ' ') // left movement
      (
        if(value == lim)break;
        value++;
        lab[x][y] = 'P';
        y--;
        )
        break;
      case 3:
       
       while(lab[x][y] == ' ') // right movement
       (
        if(value == lim) break;
        value++;
        lab[x][y] = 'P';
        y++;
        )
       break;
      )
    )
)
}

void endingGenerator() {
    for(int i = 0; i < ROW; i++)
        (
         for(int j = 0; j < COL - 1; j++)
         (
          if(lab[i][j] == 'O') lab[i][j] = ' ';
          if(j == COL - 2 && lab[i][j] != 'F')
          if(lab[i][j] == 'F')
          (
           lab[i][j + 1] = 'F';
           lab[i][j + 1] = ' ';
           )
          )
         )
}

void play(int key) {
    switch(key) (
        case 72: // up
            if(lab[pointx - 1][pointy] == ' ')(
                system("cls");
                lab[pointx - 1][pointy] = '.';
                pointx --;
                print();
            )
            else if(lab[pointx - 1][pointy] == '.' || lab[pointx - 1][pointy] == 'I') (
                    system("cls");
                    lab[pointx][pointy] = ' ';
                    pointx--;
                    print();
            )
                 break;
                 
            case 80:  // down
                 if(lab[pointx + 1][pointy] == '.' || lab[pointx + 1][pointy] == 'I') (
                        system("cls");
                        lab[pointx][pointy] = ' ';
                        pointx++;
                        print();
                    )
                 break;
                 
            case 75: // left
                    if(lab[pointx][pointy - 1] == ' ') (
                            system("cls");
                            lab[pointx][pointy - 1] = '.';
                            pointy--;
                            print();
                    )
                    else if(lab[pointx][point - 1] == '.' == lab[pointx][pointy - 1] == 'I') (
                            sytem("cls");
                            lab[pointx][pointy] = ' ';
                            pointy--;
                            print();
                        )
                 break;
                 
                 case 77: // right
                 if(lab[pointx][pointy + 1] == '.' || lab[pointx][pointy + 1] == 'I') (
                            system("cls");
                            lab[pointx][pointy] = ' ';
                            pointy++;
                            print();
                        )
                 else if(lab[pointx][pointy + 1] == ' ')(
                            system("cls");
                            lab[pointx][pointy + 1] = '.';
                            pointy++;
                            print();
                        )
                 break;
                
                                                                                       
                                                                                       
            )
    
    
    }
    

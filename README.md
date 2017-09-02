// Tic-Tac-Toe

#include <bits/stdc++.h>
using namespace std;
 char box[10]={' ',' ',' ',' ',' ',' ',' ',' ',' ',' '};
 void tic_tac_toe_board()
 {
     cout<<"  |  |  "<<endl;
     cout<<" "<<box[1]<<"| "<<box[2]<<"| "<<box[3]<<endl;
     cout<<"__|__|__"<<endl;
     cout<<"  |  |  "<<endl;
     cout<<" "<<box[4]<<"| "<<box[5]<<"| "<<box[6]<<endl;
     cout<<"__|__|__"<<endl;
     cout<<"  |  |  "<<endl;
     cout<<" "<<box[7]<<"| "<<box[8]<<"| "<<box[9]<<endl;
     cout<<"  |  |  "<<endl;
 }
int game_status()
 {
     if(((box[1]==box[2]&&box[1]!=' ')&&(box[2]==box[3]&&box[2]!=' '))||((box[1]==box[4]&&box[1]!=' ')&&(box[4]==box[7]&&box[4]!=' ')))
        return 1;
     else if(((box[4]==box[5]&&box[5]!=' ')&&(box[5]==box[6]&&box[5]!=' '))||((box[2]==box[5]&&box[2]!=' ')&&(box[5]==box[8]&&box[5]!=' ')))
        return 1;
     else if(((box[7]==box[8]&&box[7]!=' ')&&(box[8]==box[9]&&box[8]!=' '))||((box[3]==box[6]&&box[3]!=' ')&&(box[6]==box[9]&&box[6]!=' ')))
        return 1;
     else if(box[1]!=' '&&box[2]!=' '&&box[3]!=' '&&box[4]!=' '&&box[5]!=' '&&box[6]!=' '&&box[7]!=' '&&box[8]!=' '&&box[9]!=' ')
        return 0;
     else
        return -1;
 }

 int main()
 {
  char p1,p2,sym;
  cout<<endl;
  cout<<"     //Tic Tac Toe//  "<<endl;
  cout<<endl;
  cout<<" enter player 1's choice "<<endl;
  cin>>p1;
  cout<<" enter player 2's choice "<<endl;
  cin>>p2;
  int i,player=1,Move;
  do{
         tic_tac_toe_board();
    player=(player%2==0)? 2:1;
    cout<<" player "<<player<<" enter box no. "<<endl;
    cin>>Move;
    sym=(player==1)? p1:p2;
    if((box[Move]!='x')||(box[Move]!='o'))
       box[Move]=sym;
    else
    {
        cout<<" invalid Move "<<endl;
        player--;
    }
    i=game_status();
    player++;
  }
  while(i==-1);
   tic_tac_toe_board();

  if(i==1)
        cout<<" player "<<--player<<" won "<<endl;
  else
        cout<<" game draw"<<endl;


  return 0;
 }

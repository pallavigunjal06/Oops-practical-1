#include<iostream>
using namespace std;
int n,i;
class bank
{
string name,acc_no;
int balance,with_amt,depo_amt;
public:
void accept();
void withdraw();
void deposit();
void display();
}b[100];

void bank::accept()
{
    cout<<"enter number of records";
    cin>>n;
    for(i=0;i<n;i++)
    {
        cout<<"enter your name,account no and balance:\n";
        cin>>b[i].name>>b[i].acc_no>>b[i].balance;

    }
    
}

void bank::withdraw()
{   
    string accno;
    cout<<"enter account no:";
    cin>>accno;
    for(i=0;i<n;i++)
    {
        if(b[i].acc_no==accno)
        {
        cout<<"enter amount to withdraw";
        cin>>with_amt;
        if(with_amt<b[i].balance)
        {
            b[i].balance=b[i].balance-with_amt;
        }
        }
    }
}

void bank::deposit()
{   
    string accno;
    cout<<"enter account no:";
    cin>>accno;
    for(i=0;i<n;i++)
    {
        if(b[i].acc_no==accno)
        {
        cout<<"enter amount to deposit";
        cin>>depo_amt;
        if(depo_amt<b[i].balance)
        {
            b[i].balance=b[i].balance+depo_amt;
        }
        }
    }
}

void bank::display()
{   
    
    cout<<"\n"<<"name"<<"\t"<<"acc no"<<"\t"<<"balance";
    for(i=0;i<n;i++)
    {
        cout<<"\n"<<b[i].name<<"\t"<<b[i].acc_no<<"\t"<<b[i].balance;
        
    }
}


int main()
{
bank b;
int choice,ch;
do{
cout<<"1.accept 2.deposit 3.withdraw 4.display ";
cout<<"\nEnter operation to be performed";
cin>>choice;

switch(choice)
{
case 1:b.accept();
       break;
case 2:b.deposit();
       break;
case 3:b.withdraw();
       break;
case 4:b.display();
       break;
}
cout<<"\n Do you want to continue(0/1)";
cin>>ch;
}
while(ch==1);
}

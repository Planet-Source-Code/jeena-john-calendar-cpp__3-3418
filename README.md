<div align="center">

## calendar\.cpp


</div>

### Description

displays the calendar for any year b/w 2001 and 2099
 
### More Info
 
enter the year and month

code is self-explanatory

displays the calendar for the particular year

none...so cool and user friendly


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[jeena john](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jeena-john.md)
**Level**          |Intermediate
**User Rating**    |4.3 (17 globes from 4 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Classes/ Frameworks/ OOP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/classes-frameworks-oop__3-31.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jeena-john-calendar-cpp__3-3418/archive/master.zip)





### Source Code

```
#include<iostream.h>
#include<string.h>
#include<conio.h>
#include<dos.h>
 class calendar
   { private:
	  struct cal
	   { int month,day;
	    } c;
	  int a[12];
	  char months[12][15];
	public:
	  int choice,yr;
	  calendar(); //constructor
	  void menu();
	  void display();
	  void manipulate();
	  void firstshow();
  } ;
//end of class calendar
  /* Constructor for initializing the number of days of each month */
  calendar::calendar()
   { a[0]=31; a[1]=28; a[2]=31; a[3]=30; a[4]=31; a[5]=30;
	 a[6]=31; a[7]=31; a[8]=30; a[9]=31; a[10]=30; a[11]=31;
	 char* yr_month[12]=
	   { " JANUARY"," FEBRUARY"," MARCH"," APRIL"," MAY",
		" JUNE"," JULY"," AUGUST"," SEPTEMBER","OCTOBER",
		"NOVEMBER","DECEMBER"};
	for(int j=0;j<12;j++)
	strcpy(months[j],yr_month[j]);
    }
		 /* Displays the list of months */
 void calendar::menu()
 {  cout<<"\n\t\t\t.............................\n\n";
    cout<<"\t\t\tSELECT A MONTH FROM THIS LIST\n\n";
    for(int i=0;i<12;i++)
    cout<<"\n\t < "<<i+1<<" > "<<months[i];
    cout<<endl;
    cout<<"\n\t < 0 > Exit to the main screen\n";
    cout<<"\n\tPlz type the corresponding no. : ";
    cin>>choice;
    if (choice>12)
	  { 	 cout<<"\n\tWRONG CHOICE!  TRY AGAIN!!";
		 delay(1010);
		 clrscr();
		 menu();
	  }
  }
  /* This function is used to find out which day is the 1st of each month
	using the data 1 Jan 2001 ---> Monday */
  void calendar::manipulate()
  { c.month=1;
    c.day=2;
    int y=yr-2001;
    if (yr%4==0) a[1]=29;
    for(int i=0;i<y;i++)
	 {  if((2001+i)%4==0)  { c.day=c.day+2; }
			 else  { c.day=c.day+1; }
	 }
    for(i=0;i<(choice-1);i++)
	 { int x=a[i]%7;
	   c.day=c.day+x;
	  }
    if (c.day>7)  c.day=c.day%7;
    if(c.day==0)  c.day=7;
  }
  /*  Function for accepting the year */
  void calendar::firstshow()
  { clrscr();
   cout<<"\n\n\n\n\tTHIS SOFTWARE DISPLAYS THE CALENDER FOR ANY YEAR B/W";
   cout<<"\n\t.....................................................";
   cout<<"\n\t\t\t\t2001 - 2099\n";
   cout<<"\t\t\t\t............\n";
   cout<<"\n\n\tPress '0' to exit";
   cout<<"\n\n\tPlz type the year : ";
   cin>>yr;
   if (yr!=0)
	{         //exception handling
	 if((yr>2099)||(yr<2001))
	   {  cout<<"\n\n\tPLEASE TYPE IN A YEAR AS SPECIFIED ABOVE\n";
		 delay(1100);
		 clrscr();
		 firstshow();
	   }
	}
  }
  /* Function for displaying the calendar for that particular month */
 void calendar::display()
  { cout<<"\n\n\t\tCALENDER FOR "<<months[choice-1]<<"  "<<yr<<"\n";
   cout<<"\t\t..................................";
   cout<<"\n\n\n\tSUN\tMON\tTUE\tWED\tTHU\tFRI\tSAT\n\n";
   int k=0;
   for(int j=1;j<c.day;j++)
	  {  cout<<"\t ";
	    k++;
	  }
    for(int i=1;i<=a[choice-1];i++)
	  { cout<<"\t"<<i;
	   k++;
	   if(k==7) { cout<<"\n\n"; k=0; }
	  }
 }
 void main()
  {  clrscr();
    calendar cal;
//object creation for calendar class
    cal.yr=2001;
    cal.firstshow();
    while (cal.yr!=0)
	 {  clrscr();
	   cal.menu();
	   while(cal.choice!=0)
		 {  cal.manipulate();
		   clrscr();
		   cal.display();
		   getch();
		   clrscr();
		   cal.menu();
		 }
	   cal.firstshow();
	 }
  }
```


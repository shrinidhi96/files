#include<iostream>
#include<fstream>
#include<string>
using namespace std;
int main()
{
	ofstream outfile;
	outfile.open("file1.txt",ios::out);  //Opening in Write mode- file 1
	char c[200];
	string d;
	cout<<"\nEnter the data to be entered into the first file:\n";
	cin.getline(c,200);
	outfile<<c;
	outfile.close();
		
		cout<<"\nDisplaying file 1's contents:\n";
		ifstream infile;
		infile.open("file1.txt"); 
		if(infile.is_open())  
		{
			while(getline(infile,d))
				cout<<d;
						
		}   
		        //opening in write mode-file 1
	/*	infile>>c;
		cout<<c<<"\n";
		infile.close();	*/
			cout<<"\nCopying file 1's content to file 2 and displaying file 2's contents:\n";
			ofstream out;
			out.open("file2.txt",ios::out);     //opening file2 in write mode
			infile.open("file1.txt");           //opening file 1 in read mode
			char a;int count=0;
			while(infile.get(a))
			{
				if(infile.eof())
					break;
				while(a==' ')
				{
					count++;	
				}
				
					out<<a;
				else
					continue;		
			}
			out.close();
			infile.close();
		
				infile.open("file2.txt");
				infile>>d;
				cout<<d;  
				cout<<"\nThank you!!";
				infile.close();
		return 0;
}

#include<conio.h>
#include<iostream>
#include<string.h>
#include<fstream>
#include<stdlib.h>
#include<stdio.h>
  
const char users[3]={"Store Keeper","Manager","Maintenance Engineer"}; //types of users
class aircrafts_Management{
public:		
  storeKepper_activities(struct product p)
  {
	update_Product(p);
        delete product(p);
  }  
  Manger_activities(struct product p, struct itemcode c)
  {
    seacrch_Poduct(p,c);
  }
  
  

  void update_Product(struct Product p)
  {
    fstream exa;
    fstream temp;
    char code[25];
    exa.open("example.txt", ios::in);
    temp.open("temp.txt", ios::out);
    cin.ignore();
    cout<<"\nEnter Product Code : ";
    cin.getline(code,25);
    while (!exa.eof())
    {
        exa.getline(p.Product_code,5,'\n');
        exa.getline(p.Product_name'\n');
        exa.getline(p.expiry_date,5,'\n');
        exa.getline(p.Manufacturing_date,5,'\n');
        search_Product(p,code);
        if (strcmp(p.Product_code,code)==0)
        {
            cout<<"\n\nPlease update the selected Product";
            cout<<"\nEnter Product's ID: ";
            cin>>p.Product_code;
            cin.ignore();
            cout<<"Enter Product's Name: ";
            cin.getline(p.Product_name, 25);
            cout<<"Enter Manufacturing date: ";
            cin>>p.meg;
            cout<<"Enter Expiry date: ";
            cin>>p.expiry_date;
            cin.ignore();
            temp<<p.Product_code<<'\n'<<p.Product_name<<'\n'<<p.Manufacturing_date<<'\n'<<p.expiry_date<<'\n';
        }
        else
        {
            temp<<p.Product_code<<'\n'<<p.Product_name<<'\n'<<p.Manufacturing_date<<'\n'<<p.expiry_date<<'\n';
        }
    }
    temp.close();
    exa.close();
    exa.open("example.txt", ios::out);
    temp.open("temp.txt", ios::in);
    while (!temp.eof())
    {
        temp.getline(p.Product_code,25,'\n');
        temp.getline(p.Product_name,25,'\n');
        temp.getline(p.Manufacturing_date,25,'\n');
        temp.getline(p.expiry_date,25,'\n');
        exa<<p.Product_code<<'\n'<<p.Product_name<<'\n'<<p.Manufacturing_date<<'\n'<<p.expiry_date<<'\n';
    }
    temp.close();
    exa.close();
    remove("temp.txt");
    cout<<"Done!";
}

  void delete_Product(struct Product p)
{
    fstream exa;
    fstream temp;
    char code[25];
    exa.open("example.txt", ios::in);
    temp.open("temp.txt", ios::out);
    cin.ignore();
    cout<<"\nEnter Product Code : ";
    cin.getline(code,25);
    while (!exa.eof())
    {
        exa.getline(p.Product_code,5,'\n');
        exa.getline(p.Product_name'\n');
        exa.getline(p.expiry_date,5,'\n');
        exa.getline(p.Manufacturing_date,5,'\n');
        search_Product(p,code);
        if (strcmp(p.Product_code,code)==0)
        {
            continue;
        } else
        {
           temp<<p.Product_code<<'\n'<<p.Product_name<<'\n'<<p.Manufacturing_date<<'\n'<<p.expiry_date<<'\n';
        }
    }
    temp.close();
    exa.close();
    exa.open("example.txt", ios::out);
    temp.open("temp.txt", ios::in);
    while (!temp.eof())
    {
        temp.getline(p.Product_code,25,'\n');
        temp.getline(p.Product_name,25,'\n');
        temp.getline(p.Manufacturing_date,25,'\n');
        temp.getline(p.expiry_date,25,'\n');
        exa<<p.Product_code<<'\n'<<p.Product_name<<'\n'<<p.Manufacturing_date<<'\n'<<p.expiry_date<<'\n';
    }
    temp.close();
    exa.close();
    remove("temp.txt");
    cout<<"Done!";
}
  
search_Product(struct product p, struct itemcode c)
{ 
     int arr[10], i, n, cnt=0;
        cout<<"\n Enter Array Size : ";
        cin>>n;
        cout<<"\n Enter Array Elements : \n";
        for(i=0; i<n; i++)
        {
                cout<<" ";
                cin>>arr[i];
        }
        cout<<"\n Enter product to be Searched : ";
        cin>>product;
        for(i=0; i<n; i++)
        {
                if(arr[i]==product)
                {
                        cnt=1;
                        break;
                }
        }
        if(cnt==0)
        {
                cout<<"\n product Not Found..!!";
        }
        else
        {
                cout<<"\n product is"<<product<<;
        }
        return 0;
}     
                                                 
 };

int main()
  {
    struct product p;
    strcut itemcode c;
    storeKepper_activities(p);
    Manger_activities(p,c);
  }

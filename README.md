chapter11vituralfunction
========================



//
//  main.cpp
//  chapter11 virtual function
//
//  Created by zhangshiyu on 11/20/14.
//  Copyright (c) 2014 ZSY. All rights reserved.
//

#include <iostream>
using namespace std;

/////////
class Base
{
public:
    virtual void show()=0;     //pure virthal function
};
///////////////
class Derv1:public Base     //derived class 1
{
public:
    void show()
    { cout<<"Derv1\n";}
};
class Derv2
{
public:
    void show()
    {cout<<"Derv2\n;";}
};

int main()
{
    //Base bad;         // can't make obj from abstract class
    Base* arr[2];           //array of pointers to base class
    Derv1 dv1;
    Derv2 dv2;             //obj of derived class 2
    
    arr[0]=&dv1;     //put address of dv1 in array
          //put address of dv2 in array
    
    arr[0]->show();       //excute show() in both obj
    arr[1]->show();
    return 0;
}

polje_red.h
===========
#include <iostream>
typedef int element;
struct cetvorka{
       int a,b,c,d;
       };
struct banka{
       char ime[20];
       char prezime[30];
       int g;
       float stanje_tekuci;
       float stanje_devizni;
       cetvorka prioriteti;
       };
struct qu{
       banka elements[10000];
       element front,rear;
       
       };
typedef struct qu red;


int AddOne(element n){
                   return ((n+1)%10000);
                   
    }
void InitQ(red *Q) {
    Q->front=0;
    Q->rear=9999;
}


banka FrontQ(red *Q){
           if (AddOne(Q->rear)!=Q->front) 
                                          return Q->elements[Q->front];
           }
           
void EnQueueQ (banka covjek, red *Q) {
     Q->rear=AddOne(Q->rear);
     Q->elements[Q->rear]=covjek;
}
 
       
void DeQueueQ(red *Q) {
     if (AddOne(Q->rear)!=Q->front) Q->front=AddOne(Q->front);
}

bool IsEmptyQ(red *Q) {
if(AddOne(Q->rear)==Q->front) return true;
else return false;
}

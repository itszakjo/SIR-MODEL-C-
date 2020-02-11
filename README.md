# SIR-MODEL-C++ FOR DISESAE PREDICTION
This is an implementation of the SIR MODEL in C++ 


#include <iostream>
#include <string>

using namespace std;

int main()
{

     int x = 11; // aka 10 days / 11 -1 = 10




     double St [x] , It [x], Rt [x] ;
     double Std [x]  , Itd [x] ,  Rtd [x] ,  sum [x]  , sumd [x];



     St[0] = (double)45400 ; Rt[0] = (double) 2500 ; It[0] = (double) 2100 ;


      //Bt[0] = (double) It[0]/N ;
      // double  a = 0.0027 ;double r = 0.07 ;

      double b = 0.00001  ; double a = (double)1/(double)14 ;


      for (int t = 0 ; t <=x-1 ; t++){



              Std[t] =  - b * St[t] * It[t];
              Itd[t] = b * St[t] * It[t] - a * It[t];
              Rtd[t] = a * It[t];


              St[t+1] = Std[t] + St[t] ;
              It[t+1] = Itd[t] + It[t] ;
              Rt[t+1] = Rtd[t] + Rt[t] ;


             cout << " Std" <<t <<": " << Std[t] << " Itd"<<t<<": " << Itd[t] << " Rtd"<<t<<": " << Rtd[t];

             cout << " St" <<t <<": " << St[t] << " It"<<t<<": " << It[t] << " Rt"<<t<<": " << Rt[t];

             sum[t]  = St[t] + Rt[t] + It[t];

             sumd[t]  = Std[t] + Rtd[t] + Itd[t];


             cout<< " sum" << t << " is: " << sum[t];

             cout<< " sumd" << t << " is: " << sumd[t];

           }

}

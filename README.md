/*BY: Hector Schmidt.
Mortgage Payment Calculator program. This program
determines the monthly payments on a mortgage given
the loan number amount, the yearly interest rate, and
the number of years.
Before running this program create and save a file
loan.in to serve as input. */

#include <fstream>
#include <cmath>
#include <iomanip>
using namespace std;

int main()
{
    // input variables
float LoanAmount;
float yearlyInterest;
int numberOfYears;
ofstream outData;
ifstream inData;

//local variables
float monthlyInterest;
int numberOfPayments;
float payment;

inData.open("loan.in");
outData.open("loan.out");

//values from file
inData >> LoanAmount >> yearlyInterest >> numberOfYears;

//calculate
monthlyInterest = yearlyInterest * 0.01 / 12;
numberOfPayments = numberOfYears * 12;
payment=(LoanAmount*pow(1+monthlyInterest,numberOfPayments)*monthlyInterest)/(pow(1+monthlyInterest,numberOfPayments)-1);
// results
outData<<fixed<<setprecision(2)<<"For a loan amount of "<<LoanAmount<<"with an interest rate of "<<setprecision(4)<<yearlyInterest<<" and a "<<numberOfYears<<" year mortgage, "<<endl;
outData<<fixed<<setprecision(2)<<"your monthly payments are $"<<payment<<"."<<endl;
inData.close();
outData.close();
return 0;
}


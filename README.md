// paymentCalculator
//Calculates montly paymets.
#include<iostream>
#include<cmath>
#include<iomanip>

using namespace std;
const float Loan_Amount = 5000.00;
const float Yearly_interest = 0.0524;
const int Number_of_Years = 7;

int main ()
{
float monthlyInterest;
int numberOfPayments;
float payment;

monthlyInterest = Yearly_interest / 12;
numberOfPayments = Number_of_Years * 12;
payment = (Loan_Amount * pow(monthlyInterest + 1, numberOfPayments)
* monthlyInterest)/(pow(monthlyInterest + 1, numberOfPayments)-1);

    cout<< fixed << setprecision(2)<<"for a loan amount of "
    <<Loan_Amount << " with interest rate of "<<Yearly_interest
    <<"and a " << Number_of_Years<<"year mortgage, "<<endl;
    cout<< "your monthly payments are $"<< payment<<"."<< endl;
    return 0;
}


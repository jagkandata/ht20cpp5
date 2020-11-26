# Uppgift 1

Den här uppgiften går ut på att skapa en bank där man kan ta ut och sätta in pengar på sitt konto, men vi har delat upp programmet i flera filer. Skriv klart koden:

## main.cpp

```c++

#include <iostream>
#include "bank.hpp"

using namespace std;

int main(int argc, char *argv[]) {
    Bankkonto konto;
    konto.innehavare = "Jag";
    konto.saldo = 54321;

    char again = 'n';
    char action = '';
    while(again == 'Y' || again == 'y'){
        cout << "Do you want to deposit, withdraw or cancel?(d/w/c):";
        cin >> action;
        if(action == 'd' || action == 'D'){
            deposit(konto); // Ska presentera hur mycket pengar man har på kontot och sedan fråga hur mycket man vill sätta in.
                            // Efter att pengar satts in ska nya saldot skrivas ut.
        }elseif(action == 'w'){
            widthdraw(konto); // Ska presentera hur mycket pengar man har på kontot och sedan fråga hur mycket man vill ta ut.
                              // Det ska inte vara möjligt att ta ut mer pengar än man har på kontot.
                              // Efter att man har tagit ut pengar ska nya saldot skrivas ut.
        }else{
            cancel(); // Ska skriva ut att man avbröt samt saldot på kontot.
        }

        cout << "Do you want to try again? (Y/N)";
        cin >> again;
    }

    return 0;
}
```

## bank.hpp

```c++
#ifndef __BANK_H_
#define __BANK_H_

#include <iostream>
using namespace std;

typedef struct {
    string innehavare;
    double saldo;
}Bankkonto;

void deposit(Bankkonto&);
void withdraw(Bankkonto&);
void cancel(Bankkonto&);

#endif // __BANK_H_
```

## bank.cpp
```c++
#include "bank.hpp"

void deposit(Bankkonto& konto){
    //Skriv funktionen
}

void withdraw(Bankkonto& konto){
    //Skriv funktionen
}

void cancel(Bankkonto& konto){
    //Skriv funktionen
}
```

# Uppgift 2

Uppgift 2 går ut på att utöka det första programmet. Gör det möjligt att skapa flera konton, samt att välja vilket konto det är man vill kunna ta ut pengar från eller sätta in pengar på.

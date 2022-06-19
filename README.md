#include <iostream>
#include <math.h>

using namespace std;

int main()
{
  
	setlocale(LC_ALL, "RUSSIAN");
	system("color  F0");

	int N; //количество просуммированных элементов
	double Znam; //знаменатель слагаемого
	double Eps; //граница
	double TSum; //точное значение
	long double Diff; //разница между полученной суммой и точным значением
	long double Slag; //слагаемое
	long double Sum; //сумма элементов

	cout << "Введите Eps = ";//приглашение к вводу
	cin >> Eps;//ввод
	cout << "Eps = " << Eps << endl;//эхо-печать

	//Входной контроль
	if (Eps <= 0.0){
		cout << "Ошибка! Eps должен быть > 0" << endl;
		system("PAUSE");
		return -1;  //возврат переменной программе с ошибкой
	}//if

	TSum = 0.75; //точное значение
	N = 1; //количество просуммированных элементов
	Sum = 0.0; //сумма элементов
	Znam = 1.0; //знаменатель слагаемого
	Diff = abs(TSum - Sum);//разница между полученной суммой и точным значением
	//Сумма ряда
	while (Diff > Eps){
		N = N + 1;//количество просуммированных элементов
		Znam = (N - 1)*(N + 1);//знаменатель слагаемого
		Slag = 1 / Znam;//слагаемое
		Sum += Slag;//сумма элементов
		Diff = abs(TSum - Sum);//разница между полученной суммой и точным значением
	}//while
	//Печать результата
	cout << "N = " << N << "\nTSum = " << TSum << "\nSum = " << Sum << "\nDiff = " << Diff << endl;
	system("PAUSE");
	return 0; 
}

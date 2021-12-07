#include <iostream>
#include <cmath>
using namespace std;

int main() {
	int step = 0, salo;
	int mikka, leo;
	cout << "Микка загадывает:" << endl;
	cin >> mikka;
	cout << "Лео загадывает:" << endl;
	cin >> leo;
	string a[4]{"А", "О", "С", "Л"};
	for (int i = 0; i < 4; i++) {
		for (int j = 0; j < 4; j++) {
			for (int k = 0; k < 4; k++) {
				for (int l = 0; l < 4; l++) {
					string word = a[k]+a[l]+a[j]+a[i];
					if (a[i] != a[j] && a[i] != a[k] && a[i] != a[l] && a[j] != a[k] && a[j] != a[l] && a[k] != a[l]) {
						step++;
						cout << step << ' ' << word << endl;
					}
					if (word == "САЛО") salo = step;
				}
			}
		}
	}
	cout << "Микка - " << mikka << "; Лео - "<< leo << endl;
	if (salo == mikka) {
		cout << "Микка попал в яблочко!";
	} else if (salo == leo) {
		cout << "Лео попал в яблочко!";
	} else if (abs(salo-mikka) < abs(salo-leo)) {
		cout << "Микка был ближе всего.";
	} else if (abs(salo-mikka) > abs(salo-leo)) {
		cout << "Лео был ближе всего.";
	}
    return 0;
}

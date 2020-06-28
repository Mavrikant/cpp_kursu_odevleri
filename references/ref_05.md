#### Aşağıdaki C++ programı hakkında yorum yapınız:

+ sentaks hatası
+ tanımsız davranış
+ derleyiciye göre değişir
+ ekrana şunu yazar: 

```
#include<iostream>

void func(int& ra, const int& rb) 
{
	std::cout << rb; //0
	ra = 1;
	std::cout << rb; //1
}

int main() 
{
	int ival = 0;

	func(ival, ival);
}

```

[ödev cevabı](https://vimeo.com/433209303)

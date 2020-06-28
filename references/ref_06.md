#### Aşağıdaki C++ programı hakkında yorum yapınız:

+ sentaks hatası
+ tanımsız davranış
+ derleyiciye göre değişir
+ ekrana şunu yazar: 

```
#include <iostream>

int main()
{
    int x{ 1 }, y{ };

    const int &r1 = x > 0 ? x : y++; //geçici nesne int 1, R value expression
    const int &r2 = x > 0 ? x : ++y; //L value expression. r2=&x
    x = 5;
    std::cout << r1 << r2; // 1 5
}

```

[ödev cevabı](https://vimeo.com/433270915)

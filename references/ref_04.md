#### Aşağıdaki C++ programı hakkında yorum yapınız:

+ sentaks hatası
+ tanımsız davranış
+ derleyiciye göre değişir
+ ekrana şunu yazar: 

```
#include <iostream>

int main()
{
    int ival = 1;
    const int &r = ival > 0 ? ival : 1; //ilk değerini ival ile alan geçici nesneye referans
    ival = 5;
    std::cout << ival << r; //5 1
}
```

[ödev cevabı](https://vimeo.com/433201294)

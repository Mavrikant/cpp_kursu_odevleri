#### Sentaks hatası olan satırları belirtiniz:

```
int main()
{
    auto a; //tipi belli değil. ilk değeri yok
    int &b; // sol taraf ilk değerine ihtiyaç var
    auto c = 10; //ok
    int &d = c; //ok
    const auto &e = 20; //const int &
    int &f = ++c; //f=c
    int &g = c + 5; //PR value ilk değer olamaz
    int &&h = c % 2; //R value ref
    int func();//fonksiyon tanımı
    int &&j = func(); // sağ taraf değerine ref. ok.
    int &foo(); // referans dönüşlü fonk tanımı
    int &&m = foo(); //R value ya ref olmadığı için hata
    int ival = 10; //ok
    int &&rval = ival + 10; //temp'e referans. R value ref
    int &p = rval;//değer kategorisi L value olduğu için ok.
}
```


[ödev cevabı](https://vimeo.com/433277804)

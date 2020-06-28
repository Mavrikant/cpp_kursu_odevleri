##### Aşağıdaki her bir kod hakkında yorum yapınız:

```
int &func(int x)
{
    return x; // lokal çöp değişken. Adresi bir anlam ifade etmez.
}

int main()
{
    int y = 20;
    func(y) = 50; //Segmentation Fault
}

```


```
#include <iostream>

int main()
{
    const int x = 20;
    auto y = x; // const ifadesi düşer
    ++y;

    std::cout << y << " " << x << "\n"; // 21 20

}
```


```
#include <iostream>

int main()
{
    int x = 10;
    int &r1 = x;
    auto r2 = x; //int
    auto &r3 = r2; //int ref

    r2 += 5; //r2=15
    r3 += 20; //r2=35
    ++x;//x=11

    std::cout << r1 + r2 + r3 << "\n"; // 11+35+35= 81
}
```


```
int main()
{
    int x = 10;
    const int &cr = x;
    auto &r = cr; //const int

    ++r; //const olduğu için compiler error
}
```


```
#include <iostream>

int main()
{
    int a[] = { 0, 1, 2, 3, 4, 5 }; //A6_i
    auto r1 = a;//int *
    auto &r2 = a; // int *[6] &

    std::cout << typeid ( a).name() << "\n"; //A6_i
    std::cout << typeid (r1).name() << "\n"; //Pi
    std::cout << typeid (r2).name() << "\n"; //A6_i

    ++r2[3];
    std::cout << (r1[3] == r2[3]) << "\n"; //true
}

```


```
#include <iostream>

int main()
{
    int a[] = { 10, 20, 30, 40 };
    auto p = a; //int *
    auto &r = p;//int * &r = p
    ++r; // p dizinin 2. elemanını gösteriyor
    ++p; // p 3. elamanı gösteriyor

    std::cout << *r << "\n"; //30
}

```

```
#include <iostream>

int &func(int &r)
{
    ++r;
    return r;
}

int main()
{
    int x = 10;
    auto f = func; //function pointer.  int &(*)(int &)
    auto y = f(x); //int y=11
    auto &r = f(x); //x=12
    r += 400;//x=412
    y += 50; //y=61

    std::cout << "x = " << x << "\n"; //412

}
```


```
#include <iostream>

int main()
{
    int x = 10;
    int *ptr = &x;

    auto r1 = x; //int r1=10
    auto r2 = *ptr; //int r2= 10
    auto r3 = r2;  //inr r3=10
    auto &r4 = ptr;//r4= &x
    auto &r5 = *ptr; //r5=x

    r1 += 3; //r1=13
    r2 += 13; //r2=23
    r3 += 20;//r3=30
    *r4 += r2; //x=33
    ++r5; // x=34

    std::cout << "x = " << x << "\n"; //34

}
```

[ödev cevabı](https://vimeo.com/433275373)

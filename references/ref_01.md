#### Aşağıdaki kodda yapılan referans tanımlamalarından geçersiz olanları işaretleyin ve geçersizlik nedenlerini açıklayın:

```
int &f1();
int f2();

int main()
{
    int x = 10; //ok
    int y = 35; //ok
    const int primes[] { 2, 3, 5, 7, 11, 13, 17, 19, 23, 29 }; //ok
    int a[] { 1, 2, 4 }; //ok
    int &r1; //Refenslar istisnalar hariç ilk değer verilmeden oluşturulamazlar.  https://www.ibm.com/support/knowledgecenter/SSLTBW_2.4.0/com.ibm.zos.v2r4.cbclx01/cplr116.htm
    int &r2(++x);
    int &r3{ 10 }; // sabit geçici bir değere const int olmadan ref vermek mümkün değil
    const int &r4{ int() }; // ok. Çöp değere  referans
    const int &r5{ int{} }; // ok. Çöp değere  referans
    int &r6 = +y; //????
    int &r7 = (x, y); // ok. y adresi r7ye aktarılıyor
    int &r8 = x > 10 ? x : y; // ok
    int &r9 = f1(); //ok
    int &r10 = f2(); //no. f2 const int döndürüyor.
    int &r11 = primes[5];
    int const &r12 = *primes;
    const int &r13{ x }; //ok
    int *&r14 = a;
    int(&r15)[] = a;
    int(&r16)[3] = a;
}

```

[ödev cevabı](https://vimeo.com/362516832)

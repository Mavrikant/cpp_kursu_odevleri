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
    int &r2(++x); //Sol taraf ifadesi. x'in kendisi
    int &r3{ 10 }; // PR value. sabit geçici bir değere const int olmadan ref vermek mümkün değil
    const int &r4{ int() }; // ok. Geçici değere referans
    const int &r5{ int{} }; // ok. Geçici değere referans
    int &r6 = +y; // RValue expression. Ref olamaz.
    int &r7 = (x, y); // ok. y adresi r7ye aktarılıyor. Lvalue
    int &r8 = x > 10 ? x : y; // ok. LValue exp
    int &r9 = f1(); //ok. geri dönüş değeri referans
    int &r10 = f2(); //no. f2 const int döndürüyor. Rvalue.
    int &r11 = primes[5]; //Const int ref verilemez.
    int const &r12 = *primes; //ok
    const int &r13{ x }; //ok
    int*&r14 = a;  //int *  türünden bir ifadeye referans. Cpp'de pointer için arraysize'ı da önemli
    int(&r15)[] = a; //size da önemli
    int(&r16)[3] = a; //ok
}

```

[ödev cevabı](https://vimeo.com/362516832)

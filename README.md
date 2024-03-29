<h1 align=center> C Language Lecture Notes </h1>

<p align=center>
  <img width=170 src="./images/c_lang_logo.svg" />
</p>

## **Table of Contents**

0. Introduction to C +
1. Programming Naming Convention +
2. Variables and types +
3. Constants +
4. Operators +
5. Conditionals +
6. Loops +
7. Arrays +
8. Strings +
9. Pointers -
10. Functions -
11. Input and output -
12. Variables scope -
13. Static variables -
14. Global variables -
15. Type definitions -
16. Enumerated Types -
17. Structures -
18. Command line parameters -
19. Header files -
20. The preprocessor -
21. Conclusion -

<h2 align=center>Introduction to C</h2>

---

## C Programlama Dili Nedir?

<p style="font-weight: bold">
  AT&T Bell laboratuvarlarında, Ken Thompson ve Dennis Ritchie tarafından UNIX İşletim Sistemi'ni geliştirebilmek amacıyla B dilinden türetilmiş yapısal bir programlama dilidir. Geliştirilme tarihi 1972 olmasına rağmen yaygınlaşması Brian Kernighan ve Dennis M. Ritchie tarafından yayımlanan "C Programlama Dili" kitabından sonra hızlanmıştır. Günümüzde neredeyse tüm işletim sistemlerinin (Microsoft Windows, GNU/Linux, BSD, Minix) yapımında %95'lere varan oranda kullanılmış, hâlen daha sistem, sürücü yazılımı, işletim sistemi modülleri ve hız gereken her yerde kullanılan oldukça yaygın ve sınırları belirsiz oldukça keskin bir dildir.[kaynak belirtilmeli] Keskinliği, programcıya sonsuz özgürlüğün yanında çok büyük hatalar yapabilme olanağı sağlamasıdır.
</p>

```c
#include <stdio.h> //Programımıza stdio.h kütüphanesi ile I/O fonksiyonlarını dahil ediyoruz.

int main(void){ // "main()" programımızın ana fonksiyonudur.
                // "void" anahtar kelimesi ile fonksiyonun herhangi bir değer döndürmeyeceğini belirtiyoruz.

  printf("Hello World!"); //"printf()" stdio.h kütüphanesi içerisinde ki ekrana çıktı vermemizi sağlayan fonksiyondur.

  return 0; //Programın kapanmasını sağlarız. ("0" yani "Kapalı" anlamına gelmektedir. Bknz. "What is the meaning of 0 and 1 in computer?")
}
```

> "printf()" fonksiyonu **stdio.h** kütüphanesinin içerisinde şu şekilde tanımlanır 👇 (ileri sayfalarda aşağıda ki bilmediğiniz yapıları öğreniyor olacaksınız merak etmeyin 😉)

```c
int printf(const char *format, ...);
```

> **Not:** Fonksiyon, Bir veya birden fazla kod satırının bir araya gelmesi ile belirli işlem sonucu argüman dönmesini sağlayan bir alt programcıktır.

<h2 align=center> Programming Naming Conventions </h2>

---

Tam olarak programlamaya geçmeden önce bilmeniz gereken bir konu var. "Değişken İsimlendirme Kuralları" ve "Standartlar"

Önemli kurallar şöyle:

- Değişken isimlendirmesi yapılırken ASCII standardındaki alfanumeric karakterler ve \_ sembolü kullanılabilir (A-Z, a-z ve 0-9). (Türkçe diline özgü karakterler kullanılmaz -> ıİçÇöÖşŞüÜğĞ)
- Değişken isimleri sayı ile başlayamaz. Değişken isimleri harf yada \_ ile başlayabilir.
- Programlama diline ait kelimeler değişken olarak kullanılamaz. ( Örn: for kelimesi bir çok dilde döngü için kullanıldığı için kullanılamaz).
- Değişken isimlerinde boşluk tuşu ve özel karakterler($..) kullanılmaz(\_hariç).
  Çoğu programlama dili büyük küçük harf duyarlıdır. Değişken nasıl yazıldıysa o şekilde kullanılmalıdır.

Fonksiyonlar, Sınıflar, Methodlar ve bunun gibi yapıları isimlendirme konusunda en çok tercih edilenler şunlar:

- Camel Case
- Snake Case
- Kebap Case
- Pascal Case

## Camel Case

Camel Case, sözcük küçük harfle başlar küçük harfle biter. Anca hemen arkasına bir sözcük daha gelecekse büyük harfle başlar.

> Örnek: `firstName` ve `lastName`

## Snake Case

Snake Case, aynı "Camel Case" gibi sözcük küçük harf ile başlar ve biter. Ancak burada farklı olan şey birden fazla sözcük olduğunda sözcüklerin arasına (\_) "alt çizgi" gelir.

> Örnek: `first_name` ve `last_name`

## Kebap Case

Kebap Case, aynı "Snake Case" gibi aslında hiç bir değişiklik yok tek fark sözcüklerin arasında (\_) kullanmak yerine (-) "çizgi" kullanılması.

> Örnek: `first-name` ve `last-name`

## Pascal Case

Pascal Case, Sözcükler büyük harf ile başlar küçük harfle biter. Devamında ki sözcüklerde büyük harf ile başlayıp küçük harfle biter.

> Örnek: `FirstName` ve `LastName`

Ve son olarak öğrendiğiniz dilin kurallarını bilmek önemlidir.
Bilmemeniz programınızın çalışmayacağı anlamına gelmez ancak programınızın kaynak kodu daha anlaşılabilir ve daha kurallı olur.

Sağlıklı bir kod için yazım kurallarını bilelim lütfen 😉

<h2 align=center> Variables and Types </h2>

---

C statik olarak yazılmış bir programlama dilidir. Yani her bir değişken tanımlamamızda değişkenin tipini belirtmemiz gerekiyor. Bunun sebebi programı derlediğimiz zaman C'nin değişken tipini bilmesi gerekiyor.

> Örnek: `ìnt age;`

Tanımlama yapıldıktan sonra artık değişkenimize tipine bağlı olarak istediğimiz değeri atayabiliriz.

> Örnek: `age = 10;`

Eğer isterseniz değişken tanımlaması yapıyorken bile değer ataması yapabilirsiniz.

> Örnek: `int age = 10;`

Değişken tiplerimiz şunlardır:

- int
- char
- short
- long
- float
- double
- long double

Tamsayı tanımlaması yaparken aşağıdaki 4 türü kullanırız.

- int
- short
- long
- char

Çoğu zaman `int` kullanıyoruz fakat bazı durumlarda diğer 3 tipide kullanabiliriz.

**char** tipi çoğunlukla ASCII şemasında yer alan harfleri saklamak için kullanılır. Ancak -128'den 127'ye kadar küçük olan tamsayıları tutma içinde kullanılabilir. En az _1_ bayt alır.

**int** en az 2 bayt alır. **short** en az 2 bayt alır. **long** en az 4 bayt alır.

## Unsigned integers

Yukarıdaki tüm veri türleri için, aralığı negatif bir sayı yerine 0'dan başlamak için başına `unsigned` anahtar kelimesini ekleyebiliriz.

- `unsigned char` 0 ile 255 arasında olur.
- `unsigned int` 0 ile 65,535 arasında olur.
- `unsigned short` 0 ile 65,535 arasında olur.
- `unsigned long` 0 ile 4,294,967,295 arasında olur.

## Floating point numbers

Kayan nokta türleri, tamsayıların yapabileceğinden çok daha büyük bir değer kümesini temsil edebilir ve tamsayıların yapamayacağı bir şey olan kesirleri de temsil edebilir.

Aşağıda ki türler:

- `float`
- `double`
- `long double`

Ondalıklı sayıları temsil etmek için kullanılır. Hepsi hem pozitif hem de negatif sayıları temsil edebilir.

<h2 align=center> Constants </h2>

---

Eğer değişkenimizin sabit yani değiştirilemez olmasını istiyorsak tanımlama yaparken ek olarak ilk kısıma `const` anahtar kelimesini eklememiz gerekir.

> Örnek: `const int year = 2023;`

sabit tanımlamanın bir başka yolu ise şöyledir:

> Örnek: `#define year 2023;`

<h2 align=center> Operators </h2>

---

C veriler üzerinde işlem yapabilmemiz için kullanabileceğimiz çok çeşitli operatörler sunar.

- arithmetic operators (Aritmetik operatörler)
- comparison operators (Karşılaştırma operatörleri)
- logical operators (Mantıksal operatörler)
- compound assignment operators (Birleşik atama operatörleri)
- bitwise operators (Daha sonra bakılacak.)
- pointer operators (Daha sonra bakılacak.)
- structure operators (Daha sonra bakılacak.)
- miscellaneous operators (Daha sonra bakılacak.)

## Aritmetik operatörler

0. Atama operatörü (=) 👉 `a = b`
1. Toplama operatörü (+) 👉 `a + b`
2. Çıkarma operatörü (-) 👉 `a - b`
3. Çarpma operatörü (*) 👉 `a * b`
4. Bölme operatörü (/) 👉 `a / b`
5. Mod alma operatörü (%) 👉 `a % b`

## Karşılaştırma operatörleri

0. Eşit operatörü (==) 👉 `a == b`
1. Eşit değil operatörü (!=) 👉 `a != b`
2. Büyüktür operatörü (>) 👉 `a > b`
3. Küçüktür operatörü (<) 👉 `a < b`
4. Büyüktür ve eşittir operatörü 👉 `a >= b`
5. Küçüktür ve eşittir operatörü 👉 `a <= b`

## Mantıksal operatörler

0. Değil operatörü (!) 👉 `!a`
1. Ve operatörü (&&) 👉 `a && b`
2. Veya operatörü (||) 👉 `a || b`

## Birleşik atama işlemleri

0. Ekleyip atama operatörü (+=) 👉 `a += b`
1. Çıkarıp atama operatörü (-=) 👉 `a -= b`
2. Çarpıp atama operatörü (*=) 👉 `a *= b`
3. Bölüp atama operatörü (/=) 👉 `a /= b`
4. Mod alıp atama operatörü (%=) 👉 `a %= b`

> Note: Operatörleri kullanırken mesela bir matematiksel işlem yaparken işlem önceliğine kesinlikle dikkat etmelisiniz!

## Ternary operatörü

if/else koşulunun aynısıdır fakat daha kısadır.

<koşul> ? <eğer işlemi> : <değilse işlemi>

```c
  a ? b : c
```

## sizeof

sizeof fonksiyonu verdiğiniz değişkenin veya türün boyutunu geri döndürür.

```c
#include <stdio.h>

int main(void){
  int age = 37;
  printf("%ld\n", sizeof(age));
  printf("%ld", sizeof(int));
  return 0;
}
```

<h2 align=center> Conditionals </h2>

---

Herhangi bir programlama dili, programcılara seçim yapma yeteneği sağlar. Verileri kontrol etmek ve bu verilerin durumuna göre seçimler yapmak istiyoruz.

C bize bunu yapmak için 2 yol sunar.

1. if/else
2. switch

## if/else

Bir `if` koşulu ile bir şeyin doğru olup olmadığını kontrol edebilir ve ardından süslü parantez içerisindeki işlemi gerçekleştirebilir.

```c
  int a = 1;

  if(a == 1){
    /* do something */
  }
```

Eğer koşul yanlış çıkar ise `else` bloğu kullanabiliriz.

```c 
  int a = 1;
  
  if(a == 2){
    /* do something */
  } else {
    /* do something else */
  }
```

Dikka etmeniz gereken bir husus koşul içerisinde `==` yerine `=` kullanmmayınız aksi takdirde koşul her zaman doğru olacaktır. Ya da değişkenimize 0 atadağımızı düşünelim. (0 = false) eğer böyle bir hata yaparsak aşağıdaki gibi `if` koşulu hiç bir zaman çalışmayacaktır.

```c
  int a = 0;

  if(a = 0){
    /* never invoked */
  }
```

Ayrıca birden çok `if` bloğunu bir araya getirerek kullanabiliriz. Nasıl yani?? Aşağıya bakın 👇

```c
  int a = 1;

  if(a == 2){
    /* do something */
  } else if (a == 1){
    /* do something else */
  } else {
    /* do something else again */
  }
```

## switch

Belki bir değişkenin tam değerini kontrol etmeniz gerektiğinde birden çok `if/else` bloğu kullanmak durumunda kalacaksınız ve bu sizin için gereksiz kod kirliliği olabilir. İşte tam bu sorun için `switch/case` yapısını kullanabilirsiniz.

Koşul olarak bir değişken veya beklediğiniz her değer için bir `case` bloğu açmanız gerekiyor.

```c
  int a = 1;

  switch(a){
    case 0: 
      /* do something */
      break;
    case 1:
      /* do something else */
      break;
    case 2:
      /* do something else */
      break;
  }
```

Bir `case` bloğu karşılandıktan sonra diğer bloğun çalışmaması için `break` anahtar kelimesini kullanmamız gerekiyor. Aksi takdirde diğer bloklarda sırasıyla çalışacaktır. (break = kırmak)

Ve `switch` koşulumuzun sonunda eğer varsayılan olarak yani her ne olursa olsun çalışacak bir blok istiyorsak `default` bloğunu kullanabiliriz.

```c
  int a = 1;

  switch(a){
    case 0:
      /* do something */
      break;
    case 1:
      /* do something else */
      break;
    case 2:
      /* do something else */
      break;
    default:
      /* do something finally*/
      break;
  }
```

<h2 align=center> Loops </h2>

---

C bize bir işlemi döngü içerisine almak için üç yol sunar:

1. For Loops
2. While Loops
3. Do While Loops

## For Döngüsü

En çok kullanılan döngü `for` döngüsüdür. 

Kullanımı aşağıdaki gibidir:

```c
  for(int i = 0; i <= 10; i++) {
    /* instructions to be repeated */
  }
```

**İlk öncelikle `int i = 0;` ile başlangıç değerimizi tanımlarız.** _(Tabii ki bu değişken tanımlama işlemini dışarıdada yapabilirsiniz. Daha sonra geleceğim bu konuya..)_ **`i <= 10` değerimiz 10'dan küçük veya eşit değilse devam eder. `i++` ile değerimizi `1` arttırırız.**

## While Döngüsü

`while` döngüsü `for` döngüsünden bir tık daha kolaydır.

```c
  while(i < 10){
    /* do something */
  }
```

Eğer ki `i` değeri arttırılmazsa sonsuz döngü oluşur. Ve program düzgün çalışmaz.

Doğru olan `while` döngü yapısı:

```c
  int i = 0;

  while(i < 10){
    /* do something */

    i++;
  }
```

## Do While Döngüsü

While döngülerine alternatif olarak ve önemli bir farkı olan yapı olan `do while` döngüsü bir işlemi öncelikle yapıp daha sonra tekrarlamasını isteyebilirsiniz.

```c
  int i = 0;

  do {
    /* do something */

    i++;
  } while (i < 10);
```

`/* do something */` bloğu koşul kontrolü yapılmadan önce en az 1 kere çalıştırılır. Ve `i` değeri `10` olana kadar işlem tekrarlanacak.

## Break kullanarak döngüyü sonlandırmak

C içerisindeki tüm döngüleri sonlandırmak yada çıkmak için `break` anahtar kelimesini kullanabiliriz.

```c
  for(int i = 0; i <= 10; i++){
    if(i == 4 && someVariable == 10){
      break;
    }
  }
```

```c
  int i = 0;

  while(1){
    /* do something */

    i++;
    if(i == 10) break;  
  }
```

<h2 align=center> Arrays </h2>

---

`array` yani dizi birden çok veriyi saklamamızı sağlayan yapılardır.

Dizideki her değer, C'de aynı tür olmalıdır.

```c
  int prices[5];
```

```c
  const int SIZE = 5;
  int prices[SIZE];
```

Her zaman dizinin boyutunu belirtmelisiniz. C dinamik dizin yapısı kullanmaz.

Bir dizinin içerisine şu şekilde atama yapabiliriz:

```c
  int prices[5] = {1, 2, 3, 4, 5};
```

Tanımlamadan sonra şu şekildede atama yapabiliriz:

```c
  int prices[5];

  prices[0] = 1;
  prices[1] = 2;
  prices[2] = 3;
  prices[3] = 4;
  prices[4] = 5;
```

Ancak bu atama işlemi uzun süreceğinden pratik bir yöntem olarak şu şekildede yapabilirsiniz:

```c
  int prices[5];

  for(int i = 0; i < 5; i++){
    prices[i] = i + 1;
  }
```

Dizi içerisindeki değerleri görmek için `index` değerini `[]` içerisine yazarak görebilirsiniz.

```c
  prices[0] /* array item value 1 */
  prices[1] /* array item value 2 */
```

> Note: Diziler her zaman 0'dan başlar. Yani boyutu 5 olan bir dizinin index değerleri şu şekildedir: 0,1,2,3,4

<h2 align=center> Strings </h2>

---

C'de dizeler özel bir dizi türüdür: Bir dize, karakter değerlerinden oluşur.

```c
  char name[7];
```

Dizeleri normal bir dizi gibi tanımlayabilirsiniz:

```c
  char name[5] = {"F", "l", "a", "s", "h"};
```

Veya daha iyi bir şekilde tanımlanabilir:

```c
  char name[5] = "Flash";
```

`%s` kullanılarak dizi yazdırılabilir:

```c
  char name[6] = "Flash";

  printf("%s", name);
```

Dizenin uzunluğunun 5 olduğunu fark etmiş olmanız gerekiyor. ama "neden dizinin uzunluğunu 6 yaptık?" diye soruyor olabilirsiniz. Çünkü bunun sebebi `string` yapımız sonlandırılırken `0` ile sonlandırılıyor yani fazladan bir boşluk daha bırakmamız gerekiyor.

Dize tanımlanırken bu önemli bir konudur.

C tarafından sağlanan önemli bir standart modül vardır: `string.h`

Bu modül önemlidir. Dize oluştururken alt düzey ayrıntılardan kurtarır ve bir dizi kolaylık sağlar.

Modül'ü programımızın en üst satırına ekleyebiliriz:

```c
#include <string.h>
```

Modül'ü eklediğinizde programa şu fonksiyonlar dahil olur:

- `strcpy` 👉 diziyi başka bir dizgenin üzerine kopyalamamızı sağlar.
- `strcat` 👉 diziyi başka bir diziye eklememizi sağlar.
- `strcmp` 👉 iki dizgeyi karşılaştırmamızı sağlar.
- `strncmp` 👉 iki dizge ilk karakterlerini karşılaştırmamızı sağlar.
- `strlen` 👉 bir dizgenin uzunluğunu hesaplamamızı sağlar.

ve çok daha fazlası var.

**Konuların devamı hazırlanıyor..**

<!-- <h2 align=center> Pointers </h2>

---

İşaretciler C'nin en kafa karıştırıcı/zorlayıcı kısımlarından biridir. Özellikle programlama konusunda yeniyseniz. aynı zamanda Python ve JavaScript gibi üst düzey programlama dillerinden geliyorsanız.

İşaretci, değişken içeren bir bellek bloğunun adresidir.

Bir değişkenin bellek adresini almak istersek eğer `&` opereratörünü kullanabiliriz.

```c
  int age = 24;

  printf("%p", &age);
```

Değişkenin adres değerini yazdırmak için `%p` biçimini kullanırız.

Adresi başka bir değişkene atayabiliriz.

```c
  int age = 24;

  int *ageAdress = &age;
``` -->

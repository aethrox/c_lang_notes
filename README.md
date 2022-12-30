<h1 align=center> C Language Lecture Notes </h1>

<p align=center>
  <img width=170 src="./images/c_lang_logo.svg" />
</p>

## **Table of Contents**

0. Introduction to C
1. Programming Naming Convention
2. Variables and types
3. Constants
4. Operators
5. Conditionals
6. Loops
7. Arrays
8. Strings
9. Pointers
10. Functions
11. Input and output
12. Variables scope
13. Static variables
14. Global variables
15. Type definitions
16. Enumerated Types
17. Structures
18. Command line parameters
19. Header files
20. The preprocessor
21. Conclusion

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

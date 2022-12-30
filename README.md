<h1 align=center> C Language Lecture Notes </h1>

<p align=center>
  <img width=170 src="./images/c_lang_logo.svg" />
</p>

## **Table of Contents**

1. Introduction to C
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

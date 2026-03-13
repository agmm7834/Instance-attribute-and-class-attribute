## Savol 1



Instance attribute va class attribute o'rtasidagi asosiy farq nima?



- [A] Instance attribute tezroq ishlaydi, class attribute sekinroq  

- [B] Instance attribute har bir obyektga alohida tegishli; class attribute esa barcha obyektlar uchun umumiy  

- [C] Class attribute faqat `__init__` ichida ishlatiladi  

- [D] Instance attribute o'zgartirib bo'lmaydi  



> **To'g'ri javob:** B  

> **Tushuntirish:** Asosiy farq shundaki, instance attribute har bir obyektga xos mustaqil qiymat saqlaydi. Class attribute esa class darajasida e'lon qilinib, barcha instansiyalar tomonidan umumiy ishlatiladi.



---



## Savol 2



Quyidagi kodda qaysi atribut class attribute, qaysi biri instance attribute?



```python

class Uchuvchi:

    kompaniya = "Uzbekistan Airways"



    def __init__(self, ism, soat):

        self.ism = ism

        self.soat = soat

```



- [A] `kompaniya` — instance, `ism` va `soat` — class  

- [B] Hammasi class attribute  

- [C] `kompaniya` — class, `ism` va `soat` — instance  

- [D] Hammasi instance attribute  



> **To'g'ri javob:** C  

> **Tushuntirish:** `kompaniya` class tanasida, metodlardan tashqarida e'lon qilingan — class attribute. `self.ism` va `self.soat` esa `__init__` ichida `self` orqali e'lon qilingan — instance attributelar.



---



## Savol 3



Quyidagi kodning natijasi nima?



```python

class Mashina:

    tur = "Elektr"



    def __init__(self, model):

        self.model = model



m1 = Mashina("Tesla")

m2 = Mashina("BYD")

print(m1.tur, m2.tur, Mashina.tur)

```



- [A] `Elektr Elektr Elektr`  

- [B] `Tesla BYD Elektr`  

- [C] `Elektr Elektr None`  

- [D] Xato beradi  



> **To'g'ri javob:** A  

> **Tushuntirish:** `tur` — class attribute bo'lib, barcha instansiyalar va class nomi orqali bir xil qiymatni qaytaradi. `m1.tur`, `m2.tur`, `Mashina.tur` — hammasi `"Elektr"`.



---



## Savol 4



Class attribute instansiya orqali o'zgartirilganda nima sodir bo'ladi?



- [A] Class attribute barcha instansiyalar uchun o'zgaradi  

- [B] Xato beradi  

- [C] Faqat o'sha instansiya uchun yangi instance attribute yaratiladi, class attribute o'zgarmaydi  

- [D] Barcha instansiyalar o'chib ketadi  



> **To'g'ri javob:** C  

> **Tushuntirish:** `obyekt.class_attr = yangi_qiymat` deyilganda Python class attributeni o'zgartirmaydi — buning o'rniga faqat shu obyektga tegishli instance attribute yaratadi. Boshqa obyektlar class attributeni ko'rishda davom etadi.



---



## Savol 5



Quyidagi kodning natijasi nima?



```python

class Kitob:

    nashriyot = "O'qituvchi"



k1 = Kitob()

k2 = Kitob()

k1.nashriyot = "Sharq"

print(k1.nashriyot)

print(k2.nashriyot)

print(Kitob.nashriyot)

```



- [A] `Sharq`, `Sharq`, `Sharq`  

- [B] `Sharq`, `O'qituvchi`, `O'qituvchi`  

- [C] `O'qituvchi`, `O'qituvchi`, `O'qituvchi`  

- [D] `Sharq`, `Sharq`, `O'qituvchi`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `k1.nashriyot = "Sharq"` — `k1` uchun instance attribute yaratildi. `k2` da instance attribute yo'q, shuning uchun class attributeni `"O'qituvchi"` ko'radi. `Kitob.nashriyot` ham o'zgarmagan.



---



## Savol 6



`ClassName.atribut = yangi_qiymat` va `obyekt.atribut = yangi_qiymat` orasidagi farq nima?



- [A] Ikkalasi bir xil natija beradi  

- [B] `ClassName.atribut = yangi_qiymat` class attributeni o'zgartiradi; `obyekt.atribut = yangi_qiymat` esa faqat o'sha obyekt uchun instance attribute yaratadi  

- [C] `obyekt.atribut = yangi_qiymat` class attributeni o'zgartiradi  

- [D] Ikkalasi ham xato beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** Bu ikki usul tamoman farqli ishlaydi. `ClassName.atribut = yangi_qiymat` haqiqatan class attributeni o'zgartiradi va barcha instansiyalarga ta'sir qiladi. `obyekt.atribut = yangi_qiymat` esa faqat o'sha obyekt uchun instance attribute yaratadi.



---



## Savol 7



Quyidagi kodning natijasi nima?



```python

class Narx:

    soliq = 15



n1 = Narx()

n2 = Narx()

Narx.soliq = 20

print(n1.soliq, n2.soliq)

```



- [A] `15 15`  

- [B] `20 15`  

- [C] `15 20`  

- [D] `20 20`  



> **To'g'ri javob:** D  

> **Tushuntirish:** `Narx.soliq = 20` class attributeni o'zgartirdi. `n1` va `n2` da instance attribute yo'q, shuning uchun ikkalasi ham yangilangan class attributeni ko'radi. Natija: `20 20`.



---



## Savol 8



Quyidagi kodning natijasi nima?



```python

class Telefon:

    ishlab_chiqaruvchi = "Samsung"



t1 = Telefon()

t1.ishlab_chiqaruvchi = "Apple"

Telefon.ishlab_chiqaruvchi = "Xiaomi"

print(t1.ishlab_chiqaruvchi)

print(Telefon.ishlab_chiqaruvchi)

```



- [A] `Xiaomi`, `Xiaomi`  

- [B] `Apple`, `Xiaomi`  

- [C] `Apple`, `Apple`  

- [D] `Samsung`, `Xiaomi`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `t1.ishlab_chiqaruvchi = "Apple"` — `t1` uchun instance attribute yaratildi. Keyin `Telefon.ishlab_chiqaruvchi = "Xiaomi"` class attributeni o'zgartirdi. Lekin `t1` da instance attribute mavjud bo'lgani uchun u `"Apple"` ni ko'radi. `Telefon.ishlab_chiqaruvchi` → `"Xiaomi"`.



---



## Savol 9



Quyidagi kodda `t1.__dict__` va `Telefon.__dict__` qanday farqlanadi?



```python

class Telefon:

    brend = "Nokia"



    def __init__(self, model):

        self.model = model



t1 = Telefon("3310")

```



- [A] Ikkalasi bir xil natija beradi  

- [B] `t1.__dict__` faqat instance attributelarni (`model`), `Telefon.__dict__` class attributelar va metodlarni ko'rsatadi  

- [C] `t1.__dict__` class attributelarni, `Telefon.__dict__` instance attributelarni ko'rsatadi  

- [D] Ikkalasi ham `None` qaytaradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** `t1.__dict__` → `{'model': '3310'}` faqat instance attributelarni ko'rsatadi. `Telefon.__dict__` esa `brend`, `__init__` va boshqa class darajasidagi elementlarni o'z ichiga olgan `mappingproxy` ni qaytaradi.



---



## Savol 10



Quyidagi kodning natijasi nima?



```python

class Talaba:

    ball = 50



t1 = Talaba()

t2 = Talaba()

t1.ball = 90

t2.ball = 70

Talaba.ball = 60

print(t1.ball, t2.ball, Talaba.ball)

```



- [A] `60 60 60`  

- [B] `90 70 50`  

- [C] `90 70 60`  

- [D] `60 70 60`  



> **To'g'ri javob:** C  

> **Tushuntirish:** `t1.ball = 90` va `t2.ball = 70` — ikkala instansiya uchun instance attributelar yaratildi. Keyinchalik `Talaba.ball = 60` class attributeni o'zgartirdi, lekin `t1` va `t2` ning o'z instance attributelari ustunlik qiladi. Natija: `90 70 60`.



---



## Savol 11



Quyidagi kodning natijasi nima?



```python

class Avtomobil:

    eshik_soni = 4



    def __init__(self, rang):

        self.rang = rang



a = Avtomobil("qizil")

print("eshik_soni" in a.__dict__)

print("rang" in a.__dict__)

```



- [A] `True`, `False`  

- [B] `False`, `False`  

- [C] `True`, `True`  

- [D] `False`, `True`  



> **To'g'ri javob:** D  

> **Tushuntirish:** `a.__dict__` faqat instance attributelarni saqlaydi. `rang` — instance attribute, shuning uchun `True`. `eshik_soni` — class attribute, `a.__dict__` da yo'q, shuning uchun `False`.



---



## Savol 12



Instance attribute va class attribute qaysi tartibda qidiriladi?



- [A] Avval class attribute, keyin instance attribute  

- [B] Avval instance attribute, topilmasa class attribute, undan keyin meros zanjiri  

- [C] Faqat instance attribute qidiriladi  

- [D] Ikkalasi bir vaqtda qidiriladi  



> **To'g'ri javob:** B  

> **Tushuntirish:** Python attribute qidirishda MRO (Method Resolution Order) tartibiga amal qiladi: avval instance `__dict__` dan qidiradi, topilmasa class `__dict__` ga o'tadi, undan keyin meros zanjiri bo'yicha yuqoriga ko'tariladi.



---



## Savol 13



Quyidagi kodning natijasi nima?



```python

class Sensor:

    umumiy_son = 0



    def __init__(self, nom):

        self.nom = nom

        Sensor.umumiy_son += 1



s1 = Sensor("Harorat")

s2 = Sensor("Bosim")

s3 = Sensor("Namlik")

del s2

print(Sensor.umumiy_son)

```



- [A] `2`  

- [B] `3`  

- [C] `1`  

- [D] `0`  



> **To'g'ri javob:** B  

> **Tushuntirish:** 3 ta obyekt yaratildi, har birida `Sensor.umumiy_son += 1` bajarildi. `del s2` faqat `s2` o'zgaruvchisini o'chiradi, lekin `umumiy_son` kamaymaydi. Natija: `3`.



---



## Savol 14



Quyidagi kodning natijasi nima?



```python

class Shakl:

    rangi = "yashil"



    def __init__(self, hajm):

        self.hajm = hajm



s1 = Shakl(10)

s1.rangi = "qizil"

del s1.rangi

print(s1.rangi)

```



- [A] `None`  

- [B] `qizil`  

- [C] `yashil`  

- [D] `AttributeError`  



> **To'g'ri javob:** C  

> **Tushuntirish:** `s1.rangi = "qizil"` — instance attribute yaratildi. `del s1.rangi` — shu instance attribute o'chirildi. Endi `s1.rangi` ga murojaat qilinganda instance attribute yo'q, Python class attribute `"yashil"` ni qaytaradi.



---



## Savol 15



Quyidagi kodning natijasi nima?



```python

class Xona:

    maydon = 20



    def __init__(self, nomi):

        self.nomi = nomi



x1 = Xona("Mehmonxona")

x2 = Xona("Yotoqxona")

x1.maydon = 35

print(x1.maydon, x2.maydon, Xona.maydon)

```



- [A] `35 35 35`  

- [B] `35 20 35`  

- [C] `35 20 20`  

- [D] `20 20 20`  



> **To'g'ri javob:** C  

> **Tushuntirish:** `x1.maydon = 35` — faqat `x1` uchun instance attribute yaratildi. `x2` da instance attribute yo'q → class attribute `20`. `Xona.maydon` ham o'zgarmagan `20`. Natija: `35 20 20`.



---



## Savol 16



Mutable (o'zgaruvchan) class attribute bilan ishlashda qanday xavf bor?



- [A] Hech qanday xavf yo'q  

- [B] Mutable class attribute (list, dict) ga element qo'shilsa, barcha instansiyalar o'zgarishni ko'radi — bu kutilmagan natijalarga olib kelishi mumkin  

- [C] Mutable class attribute faqat o'chirib bo'lmaydi  

- [D] Mutable class attribute faqat bitta instansiyada ishlaydi  



> **To'g'ri javob:** B  

> **Tushuntirish:** Agar class attribute list yoki dict kabi mutable ob'yekt bo'lsa va unga element qo'shilsa (`.append()`, `.update()` orqali), bu barcha instansiyalarga ta'sir qiladi. Bu OOP dagi eng keng tarqalgan xatolardan biri.



---



## Savol 17



Quyidagi kodning natijasi nima?



```python

class Sinf:

    talabalar = []



    def qosh(self, ism):

        self.talabalar.append(ism)



s1 = Sinf()

s2 = Sinf()

s1.qosh("Ali")

s2.qosh("Vali")

print(s1.talabalar)

```



- [A] `["Ali"]`  

- [B] `["Vali"]`  

- [C] `["Ali", "Vali"]`  

- [D] `[]`  



> **To'g'ri javob:** C  

> **Tushuntirish:** `talabalar = []` — mutable class attribute. `s1.qosh("Ali")` va `s2.qosh("Vali")` ikkalasi ham bitta umumiy ro'yxatga qo'shadi. `s1.talabalar` → `["Ali", "Vali"]`. Bu klassik Python tuzoqi!



---



## Savol 18



Oldingi xatoni qanday to'g'rilash mumkin?



- [A] `talabalar = ()` deb tuple qilish  

- [B] `self.talabalar = []` ni `__init__` ichida e'lon qilib, har bir instansiya uchun alohida ro'yxat yaratish  

- [C] `@classmethod` ishlatish  

- [D] `talabalar = None` deb belgilash  



> **To'g'ri javob:** B  

> **Tushuntirish:** To'g'ri yechim — `self.talabalar = []` ni `__init__` ichiga ko'chirish. Shunda har bir instansiya uchun alohida bo'sh ro'yxat yaratiladi va bir instansiyaga qo'shilgan element boshqalariga ta'sir qilmaydi.



---



## Savol 19



Quyidagi kodning natijasi nima?



```python

class Bank:

    foiz = 12



    def __init__(self, egasi, balans):

        self.egasi = egasi

        self.balans = balans



    def daromad(self):

        return self.balans * Bank.foiz / 100



b1 = Bank("Jasur", 1000000)

b2 = Bank("Sarvar", 500000)

Bank.foiz = 15

print(b1.daromad(), b2.daromad())

```



- [A] `120000.0` va `60000.0`  

- [B] `150000.0` va `75000.0`  

- [C] `120000.0` va `75000.0`  

- [D] Xato beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** `Bank.foiz = 15` class attributeni o'zgartirdi. `daromad()` metodi `Bank.foiz` ni ishlatadi. `b1.daromad()` → `1000000 * 15 / 100 = 150000.0`, `b2.daromad()` → `500000 * 15 / 100 = 75000.0`.



---



## Savol 20



Quyidagi kodning natijasi nima?



```python

class Kurs:

    chegirma = 0



    def __init__(self, nomi, narx):

        self.nomi = nomi

        self.narx = narx



    def chegirmali_narx(self):

        return self.narx * (1 - self.chegirma / 100)



python_kursi = Kurs("Python", 500000)

python_kursi.chegirma = 20

java_kursi = Kurs("Java", 600000)



print(python_kursi.chegirmali_narx())

print(java_kursi.chegirmali_narx())

```



- [A] `400000.0` va `480000.0`  

- [B] `500000.0` va `600000.0`  

- [C] `400000.0` va `600000.0`  

- [D] Xato beradi  



> **To'g'ri javob:** C  

> **Tushuntirish:** `python_kursi.chegirma = 20` — instance attribute, faqat shu obyektga tegishli. `java_kursi` da instance attribute yo'q → class attribute `0` ishlatiladi. `python_kursi` → `500000 * 0.8 = 400000.0`, `java_kursi` → `600000 * 1.0 = 600000.0`.



---



## Savol 21



`hasattr()` orqali class va instance attributelarni qanday farqlash mumkin?



- [A] `hasattr()` faqat instance attributelarni tekshiradi  

- [B] `hasattr()` faqat class attributelarni tekshiradi  

- [C] `hasattr()` ikkalasini ham topadi; farqlash uchun `atribut in obyekt.__dict__` (instance) va `atribut in ClassName.__dict__` (class) ishlatiladi  

- [D] `hasattr()` orqali farqlash mumkin emas  



> **To'g'ri javob:** C  

> **Tushuntirish:** `hasattr(obyekt, 'attr')` ham instance, ham class attributelarni topadi. Aniq farqlash uchun `'attr' in obyekt.__dict__` (faqat instance), `'attr' in ClassName.__dict__` (faqat class darajasida) tekshiruvlaridan foydalanish kerak.



---



## Savol 22



Quyidagi kodning natijasi nima?



```python

class Planeta:

    galaktika = "Somon yo'li"



    def __init__(self, nom, diametr):

        self.nom = nom

        self.diametr = diametr



yer = Planeta("Yer", 12742)

print("galaktika" in yer.__dict__)

print("galaktika" in Planeta.__dict__)

print("nom" in yer.__dict__)

```



- [A] `True`, `True`, `True`  

- [B] `False`, `True`, `True`  

- [C] `True`, `False`, `False`  

- [D] `False`, `False`, `True`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `galaktika` — class attribute, `yer.__dict__` da yo'q (`False`), `Planeta.__dict__` da bor (`True`). `nom` — instance attribute, `yer.__dict__` da bor (`True`).



---



## Savol 23



Quyidagi kodning natijasi nima?



```python

class Kompyuter:

    os = "Windows"



    def __init__(self, model):

        self.model = model

        self.os = "Linux"



pc = Kompyuter("Dell")

print(pc.os)

print(Kompyuter.os)

```



- [A] `Windows`, `Windows`  

- [B] `Linux`, `Windows`  

- [C] `Windows`, `Linux`  

- [D] `Linux`, `Linux`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `__init__` ichida `self.os = "Linux"` — instance attribute yaratildi. `pc.os` da avval instance attribute qidiriladi → `"Linux"`. `Kompyuter.os` class attribute → `"Windows"` o'zgarmagan.



---



## Savol 24



Quyidagi kodning natijasi nima?



```python

class Mahsulot:

    kategoriya = "Oziq-ovqat"

    soni = 0



    def __init__(self, nomi):

        self.nomi = nomi

        Mahsulot.soni += 1



m1 = Mahsulot("Non")

m2 = Mahsulot("Sut")

m1.kategoriya = "Nonvoylik"

print(m1.kategoriya, m2.kategoriya)

print(Mahsulot.soni)

```



- [A] `Oziq-ovqat Oziq-ovqat`, `2`  

- [B] `Nonvoylik Oziq-ovqat`, `2`  

- [C] `Nonvoylik Nonvoylik`, `1`  

- [D] `Oziq-ovqat Oziq-ovqat`, `1`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `m1.kategoriya = "Nonvoylik"` faqat `m1` uchun instance attribute yaratdi. `m2.kategoriya` class attributeni ko'radi: `"Oziq-ovqat"`. `Mahsulot.soni` esa ikkita obyekt yaratilgani uchun `2`.



---



## Savol 25



Meros olishda class attribute qanday meros olinadi?



- [A] Meros olinmaydi, farzand class alohida e'lon qilishi kerak  

- [B] Farzand class ota classning class attributelarini avtomatik meros oladi va ularga murojaat qila oladi  

- [C] Faqat `super()` orqali meros olinadi  

- [D] Faqat `@classmethod` orqali meros olinadi  



> **To'g'ri javob:** B  

> **Tushuntirish:** Farzand class ota classning class attributelarini to'liq meros oladi. Farzand o'z attributesini e'lon qilmasa, Python MRO bo'yicha ota classning attributesidan foydalanadi.



---



## Savol 26



Quyidagi kodning natijasi nima?



```python

class Ota:

    til = "O'zbek"



class Farzand(Ota):

    pass



class Nabira(Farzand):

    til = "Ingliz"



print(Farzand.til)

print(Nabira.til)

```



- [A] `O'zbek`, `O'zbek`  

- [B] `Ingliz`, `Ingliz`  

- [C] `O'zbek`, `Ingliz`  

- [D] Xato beradi  



> **To'g'ri javob:** C  

> **Tushuntirish:** `Farzand` o'z `til` attributesini e'lon qilmagan → `Ota.til` → `"O'zbek"` meros olinadi. `Nabira` esa `til = "Ingliz"` deb o'zini e'lon qilgan → `"Ingliz"`.



---



## Savol 27



Quyidagi kodning natijasi nima?



```python

class Hayvon:

    ovqat = "O't"

    soni = 0



    def __init__(self, ism):

        self.ism = ism

        Hayvon.soni += 1



class It(Hayvon):

    ovqat = "Go'sht"



class Sigir(Hayvon):

    pass



i = It("Rex")

s = Sigir("Buzoq")

print(It.ovqat, Sigir.ovqat)

print(Hayvon.soni)

```



- [A] `Go'sht O't`, `1`  

- [B] `O't O't`, `2`  

- [C] `Go'sht O't`, `2`  

- [D] `Go'sht Go'sht`, `2`  



> **To'g'ri javob:** C  

> **Tushuntirish:** `It.ovqat = "Go'sht"` o'zining class attributesi. `Sigir` o'z `ovqat` ini e'lon qilmagan → `Hayvon.ovqat` → `"O't"`. `Hayvon.soni` esa `It` va `Sigir` dan bittadan yaratilgani uchun `2`.



---



## Savol 28



Quyidagi kodning natijasi nima?



```python

class Hisoblagich:

    qiymat = 0



    def oshir(self):

        self.qiymat += 1



h1 = Hisoblagich()

h2 = Hisoblagich()

h1.oshir()

h1.oshir()

h2.oshir()

print(h1.qiymat, h2.qiymat, Hisoblagich.qiymat)

```



- [A] `2 1 3`  

- [B] `2 1 0`  

- [C] `3 3 3`  

- [D] `0 0 0`  



> **To'g'ri javob:** B  

> **Tushuntirish:** `self.qiymat += 1` aslida `self.qiymat = self.qiymat + 1` ga teng. Bu birinchi marta chaqirilganda instance attribute yaratadi. `h1.qiymat = 2`, `h2.qiymat = 1`, `Hisoblagich.qiymat = 0` (o'zgarmagan). Natija: `2 1 0`.



---



## Savol 29



`@classmethod` va instance method class/instance attributelariga murojaatda qanday farqlanadi?



- [A] Ikkalasi ham faqat instance attributelarni ko'radi  

- [B] `@classmethod` (`cls` orqali) class attributelariga, instance method (`self` orqali) ham instance, ham class attributelariga murojaat qila oladi  

- [C] Instance method faqat instance attributelarni ko'radi  

- [D] `@classmethod` faqat instance attributelarni o'zgartira oladi  



> **To'g'ri javob:** B  

> **Tushuntirish:** `@classmethod` `cls` parametri orqali class attributelariga murojaat qiladi. Instance method `self` orqali avval instance attributelarni, topilmasa class attributelarni ko'radi. `@classmethod` instance attributelariga bevosita kirish imkoniga ega emas.



---



## Savol 30



Quyidagi kodning natijasi nima?



```python

class Fabrika:

    mahsulot_soni = 0



    def __init__(self, nom):

        self.nom = nom



    @classmethod

    def yangi_mahsulot(cls):

        cls.mahsulot_soni += 1

        return cls(f"Mahsulot-{cls.mahsulot_soni}")



m1 = Fabrika.yangi_mahsulot()

m2 = Fabrika.yangi_mahsulot()

m3 = Fabrika.yangi_mahsulot()

print(m2.nom, Fabrika.mahsulot_soni)

```



- [A] `Mahsulot-1`, `3`  

- [B] `Mahsulot-2`, `3`  

- [C] `Mahsulot-3`, `3`  

- [D] Xato beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** `yangi_mahsulot()` har chaqirilganda `mahsulot_soni` oshiriladi va yangi obyekt yaratiladi. `m1.nom = "Mahsulot-1"`, `m2.nom = "Mahsulot-2"`, `m3.nom = "Mahsulot-3"`. `Fabrika.mahsulot_soni = 3`. Natija: `Mahsulot-2`, `3`.



---



## Savol 31



Quyidagi kodning natijasi nima?



```python

class Config:

    debug = False

    versiya = "1.0"



    def __init__(self, nomi):

        self.nomi = nomi



c1 = Config("App1")

c2 = Config("App2")

c1.debug = True

Config.versiya = "2.0"



print(c1.debug, c2.debug)

print(c1.versiya, c2.versiya)

```



- [A] `True False`, `2.0 2.0`  

- [B] `True True`, `2.0 2.0`  

- [C] `True False`, `1.0 1.0`  

- [D] `False False`, `2.0 2.0`  



> **To'g'ri javob:** A  

> **Tushuntirish:** `c1.debug = True` — faqat `c1` uchun instance attribute. `c2.debug` → class attribute `False`. `Config.versiya = "2.0"` class attributeni o'zgartirdi → `c1.versiya` va `c2.versiya` ikkalasi ham `"2.0"`.



---



## Savol 32



Quyidagi kodda xato bormi va natija nima?



```python

class Doston:

    muallif = "Navoiy"



    def __init__(self, nomi):

        self.nomi = nomi



d = Doston("Farhod va Shirin")

print(d.muallif)

print(d.nomi)

print(d.chop_etilgan_yil)

```



- [A] Xato yo'q, hamma narsa chiqariladi  

- [B] `Navoiy` va `Farhod va Shirin` chiqadi, keyin `AttributeError`  

- [C] Birinchi qatordan xato beradi  

- [D] Faqat `AttributeError` beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** `d.muallif` → `"Navoiy"` (class attribute). `d.nomi` → `"Farhod va Shirin"` (instance attribute). Lekin `d.chop_etilgan_yil` e'lon qilinmagan, shuning uchun `AttributeError` yuzaga keladi.



---



## Savol 33



Quyidagi kodning natijasi nima?



```python

class Ob_havo:

    birlik = "Celsius"



    def __init__(self, harorat):

        self.harorat = harorat



    def ko_rsat(self):

        return f"{self.harorat} {self.birlik}"



toshkent = Ob_havo(32)

london = Ob_havo(18)

london.birlik = "Fahrenheit"

london.harorat = 64



print(toshkent.ko_rsat())

print(london.ko_rsat())

```



- [A] `32 Celsius`, `64 Celsius`  

- [B] `32 Fahrenheit`, `64 Fahrenheit`  

- [C] `32 Celsius`, `64 Fahrenheit`  

- [D] Xato beradi  



> **To'g'ri javob:** C  

> **Tushuntirish:** `london.birlik = "Fahrenheit"` — faqat `london` uchun instance attribute yaratildi. `toshkent` class attribute `"Celsius"` ni ko'radi. `toshkent.ko_rsat()` → `"32 Celsius"`, `london.ko_rsat()` → `"64 Fahrenheit"`.



---



## Savol 34



Quyidagi ikkita yondashuvdan qaysi biri to'g'ri va nima uchun?



```python

# Yondashuv A

class OylikA:

    soliq_foizi = 12

    def hisobla(self, maosh):

        return maosh * (1 - OylikA.soliq_foizi / 100)



# Yondashuv B

class OylikB:

    def __init__(self, soliq_foizi=12):

        self.soliq_foizi = soliq_foizi

    def hisobla(self, maosh):

        return maosh * (1 - self.soliq_foizi / 100)

```



- [A] A yondashuvi to'g'ri, chunki soliq foizi har doim bir xil  

- [B] B yondashuvi to'g'ri, chunki har bir instansiya o'z soliq foiziga ega bo'lishi mumkin  

- [C] Ikkalasi ham xato  

- [D] Ikkalasi ham bir xil natija beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** B yondashuvi moslashuvchanroq — har bir instansiya o'z `soliq_foizi` ga ega bo'lishi mumkin. A da esa `soliq_foizi` umumiy class attribute va barcha instansiyalar uchun bir xil bo'ladi. Real holatda soliq foizi har bir xodim uchun farqli bo'lishi mumkin.



---



## Savol 35



Quyidagi kod qaysi holatda to'g'ri ishlaydi va nima uchun?



```python

# Holat A: Class attribute sifatida

class TalabalarA:

    royxat = []

    def qosh(self, ism):

        self.royxat.append(ism)



# Holat B: Instance attribute sifatida

class TalabalarB:

    def __init__(self):

        self.royxat = []

    def qosh(self, ism):

        self.royxat.append(ism)



a1, a2 = TalabalarA(), TalabalarA()

b1, b2 = TalabalarB(), TalabalarB()

a1.qosh("Ali"); a2.qosh("Vali")

b1.qosh("Ali"); b2.qosh("Vali")

print(a1.royxat, a2.royxat)

print(b1.royxat, b2.royxat)

```



- [A] Ikkalasi ham bir xil natija beradi  

- [B] A: `['Ali', 'Vali'] ['Ali', 'Vali']`, B: `['Ali'] ['Vali']` — B to'g'ri ishlaydi  

- [C] A: `['Ali'] ['Vali']`, B: `['Ali', 'Vali'] ['Ali', 'Vali']`  

- [D] Ikkalasi ham xato beradi  



> **To'g'ri javob:** B  

> **Tushuntirish:** A da `royxat` — mutable class attribute. `a1` va `a2` bitta ro'yxatni ulashadi → ikkalasida `['Ali', 'Vali']`. B da `self.royxat = []` har instansiya uchun alohida ro'yxat yaratadi → `b1`: `['Ali']`, `b2`: `['Vali']`. **B to'g'ri yondashuv!**



---

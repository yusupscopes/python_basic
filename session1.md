# Session 1: Python Dasar

## Print
Syntax print digunakan untuk mencetak suatu output ke terminal
```python
print("Hi Python!")
# Output: Hi Python!
```

## Variabel
Variabel adalah cara kita menyimpan sebuah nilai ke dalam suatu huruf atau kata agar bisa kita pakai secara berulang. Aturan penulisan variabel di python yaitu menggunakan alfanumerik dan bisa menggunakan *underscore* (\_).
```python
_py1 = "Hi Python!"
print(_py1)
# Output: Hi Python!
```

## Tipe Data
Beberapa tipe data yang ada di python adalah Numbers, String, List, Tuple, Dictionary.
```python
#String
w = "Belajar Python"
x = '5'

#Number
y = 10.5
z = 9

# untuk cek tipe data
type(y)
# Output: <class 'float'>
```

### String
Menggabungkan string (concatenate) di python.
```python
x = 'belajar'
print(x + " python")
# Output: belajar python

y = 'python'
print(x + " " + y)
# Output: belajar python
```
Escape karakter khusus menggunakan backslash (\).
```python
print('hari ini hari jum\'at \n ini di baris kedua')
# Output: hari ini hari jum'at
#         ini di baris kedua
```
Beberapa method string di python.
```python
x = 'belajarpython'
x.capitalize()
# Output: Belajarpython

x.replace('belajar', 'kenalan')
# Output: kenalanpython
```

### Angka
Mengoperasikan tipe data angka di python.
```python
x = 10
y = 20
print(x*y)
# Output: 200

max(x, y, 50, 70)
# Output: 70

round(7.89)
# Output: 8

import math
math.pi
# Output: 3.1415xxxxxxxxx
```
Menggabungkan angka dengan string bersamaan (berbeda tipe data) bisa menggunakan tanda koma (,)
```python
harga = 5000
print("total belanja ", harga)
# Output: total belanja 5000

# konversi int ke string
str(harga)

# konversi dari string ke int
int(harga)
```

### Boolean
Tipe data yang nilai nya cuma ada 2, yaitu __*True*__ dan __*False*__.
```python
angka1 = 20
angka2 = 40
print(angka1 < angka2)
# Output: True

text = 'belajarpython'
print(text.isalnum())
# Output: True
```

## Komentar
```python
# ini komentar satu baris

"""
ini komentar beberapa baris
ini komentar juga
begitu juga dengan ini
"""
```

## Input
```python
nama = input("Siapa nama kamu? ")
umur = input("berapa umurmu? ")
print("salam kenal! boss " + nama + ", kamu sudah " + umur + " tahun")
```

## Percabangan
Cara kita menentukan kondisi
### If dan Else
```python
angka1 = 20
angka2 = 40

if angka1 == angka2:
    print('benar angka1 dan angka2 sama besar')
else:
    print('salah!')
# Output: salah!
```

### If, Elif, dan Else
```python
uang  = input('kamu punya uang berapa? ')
utang = 10000

if int(uang) < utang:
    print('wah maaf masih belum cukup')
elif int(uang) == utang:
    print('terimakasih sudah bayar!')
else:
    print('wah uangnya lebih bos')
```

## Operator
Operator logika di python.
```python
"""
and or not
&   |  !=
"""

if (2 > 1) & (3 < 5):
    print('anda benar!')
else:
    print('anda salah!')
# Output: anda benar!
```

## Perulangan
### While loop
```python
count = 1

while count < 5:
    print('belajar python')
    count = count + 1
else:
    print("akhir dari loop, countnya adalah", count)

# nested loop pada while
a = 1
while a < 5:
    b = 0
    while b < a:
        print('*', end='')
        b = b + 1
    print()
    a = a + 1
```

### For in loop
```python
text  = 'python'
orang = ['yusup', 'maulana', 'aris']

for nama in orang:
    print('nama-namanya adalah ', nama)

# nested loop pada for
for a in range(1,5):
    for b in range(1,5):
        c = a * b
        print(c, end=" ")
    print()
```

## Lists []
Kumpulan beberapa value di dalam satu variabel (kalo di bahasa program lain array).
Pada lists ini kita bisa mengakses, menambah, mengedit, dan menghapus elemen-elemen di dalamnya.
```python
random = [3, 'text', 'huruf', 10.5]
print(random[2])
# Output: huruf

# cara menambahkan elemen ke dalam lists
random.append('yusup')

# untuk mengedit elemen di dalam lists
random[3] = 9.5

# untuk menghapus elemen di dalam lists
del random[3]
```

## Tuples ()
Tuples adalah list yang sifatnya immutable (nggak bisa di modifikasi).
```python
random1 = (3, 'text', 'huruf', 10.5)
# convert tuples ke dalam bentuk lists
print(list(random1))

random = [3, 'text', 'huruf', 10.5]
# convert lists ke dalam bentuk tuples
print(tuple(random))
```

## Dictionary {}
Pasangan key:value (array associative).
```python
bio = {'name':'yusup', 'age':'18', 'hobby':'read'}

# cara mengakses datanya
for key, value in bio.items():
    print(key + " - " + value)
# Output: name - yusup
#         age  - 18
#         hobby - read

# menambahkan elemen baru ke dalam dictionary
bio['dream'] = 'author'

# mengedit elemen berdasarkan key
bio['age'] = 20

# menghapus elemen
del bio['age']

print(bio['name'])
# Output: yusup
```

```python
# Dictionary bersarang
data = { 1:{'name':'yusup', 'age':'21', 'hobby':'sing'},
         2:{'name':'maulana', 'age':'12', 'hobby':'read'}
       }
print(data[2]['name'])
# Output: maulana

# cara mengakses data dictionary yang bersarang dengan loop
for key, value in data.items():
    print("\nKeynya: ", key)
    for key2 in value:
        print(key2 + "-", value[key2])
```

## Sets
Sets adalah item yang nggak punya urutan. Kita nggak bisa mengakses dengan nomor index ataupun dengan key dan di dalam nya nggak boleh ada duplicate. Sets ini bisa kita manfaatkan untuk operasi himpunan seperti: union, intersection, difference, dan lain-lain.
```python
angka1 = {1,2,3,4,5}
angka2 = {4,5,6,7,8}
print(angka1 - angka2)
# Output: {1,2,3}
```

```python
orang = {'yusup', 'maulana', 'bro', 'bosqu', 'yusup'}
orang.add('alex')
orang.remove('bro')
print(orang)
# Output: {'yusup', 'maulana', 'bosqu', 'alex'}
```

## Function
Function adalah blok atau beberapa baris kode yang bisa dipakai berulang-ulang.
```python
def cetak(text = 'default'):
    print('=============')
    print(text)
    print('=============')

cetak('hi, everyone!')
cetak()
# Output: hi, everyone!
# Output: default
```

```python
def hitung(a, b):
    print('jumlah dari a dan b adalah ', a + b)

hitung(10, 10)
hitung(200, 300)
# Output: jumlah dari a dan b adalah 20
# Output: jumlah dari a dan b adalah 500
```
Return pada fungsi berguna untuk mengembalikan sebuah nilai.
```python
def hitung(a, b):
    return a + b

hasil1 = hitung(20, 30)
print(hitung(hasil1, 50))
# Output: 100
```

## Module
## Scope variabel
## Exception handling
## Latihan

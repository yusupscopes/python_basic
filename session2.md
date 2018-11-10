# Session 2: Python I/O

## Membaca dan Menulis File
Untuk bermain dengan file, pada python kita bisa menggunakan built-in function open().
```python
# Membaca file
file = open('file.txt', 'r')
text = file.read()
print(text)
# Output: Apapun isi file.txt!

# Menulis file
file = open('file.txt', 'w')
file.write('Halo Halo Pangandaran')
# Output: File file.txt akan berisi text Halo Halo Pangandaran
```
### Membaca dan menulis bersamaan
```python
file = open('file.txt', 'a+')
file.write('\nHalo Halo Bogor')

# untuk mengembalikan pointer ke posisi semula
file.seek(0)
text = file.read()
print(text)
```
### Membuat daftar belanja
```python
file = open('list.txt', 'a+')

def add_to_list(text):
    file.write('\n' + text)
    file.seek(0)
    text = file.read()
    print(text)
    ask_user()

def ask_user():
    add_to_list(input('Mau beli apa aja? '))

ask_user()
```

## Membaca File CSV
```python
import csv

rows = []
with open('file.csv', 'r') as csvfile:
    csvreader = csv.DictReader(csvfile)
    # for row in csvreader:
    #     rows.append(row)
    rows = list(csvreader)
    print('total baris ', csvreader.line_num)

for row in rows[:5]:
    print(row['first_name'] + ' - ' + row['email'])
```

## Menulis File CSV
```python
import csv

rows = [
    {'nama' : 'jack lee', 'skill': 'tendangan maud', 'power': 200 }
    {'nama' : 'jet chan', 'skill': 'pikulan maud', 'power': 250 }
]

with open('write.csv', 'a') as csvfile:
    fields = ['nama', 'skill', 'power']
    writer = csv.DictWriter(csvfile, fieldnames = fields)

    writer.writeheader()
    writer.writerows(rows)
```

## Menulis dan Membaca File JSON
```python
# menulis file json
import json

data = {}
data['member'] = [
    {'name':'jacklee','skill':'nafas naga'},
    {'name':'goku','skill': 'tendangan maud'},
    {'name':'trunks','skill':'pukulan beruang'}
]

with open('file.txt', 'w') as memberfile:
    json.dump(data, memberfile)
```
```python
# membaca file json
import json

with open('file.txt', 'r') as memberfile:
    data = json.load(memberfile)

    for member in data['member']:
        print('namanya adalah '+ member['name'] + ' punya skill: ' + member['skill'])
```

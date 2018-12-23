# Session 3: Object Oriented Programming

## Class

```python
# Mendefinisikan class
class Player:
    name = ''

    def getName(self, name):
        self.name = name
        return self.name

# Membuat objek dari class Player
pemain = Player()
print(pemain.getName('Oziil'))
# Output: Oziil
```

### Method __init__() / Constructor pada bahasa pemrograman lain.
```python
class Player:
    name  = ''
    speed = ''

    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def getName(self):
        return self.name
    
    def getSpeed(self):
        return self.speed

player = Player('Belerin', '90')
print(player.getName())
# Output: Belerin
```

### Inheritance
```python
class Player:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def getName(self):
        return self.name
    
    def getSpeed(self):
        return self.speed

# Inheritance dari class Player
class ArgentinaPlayer(Player):
    def setAge(self, age):
        self.age = age
        return self.age

class FrancePlayer(Player):
    def setAge(self, age):
        self.age = age
        return self.age

player = ArgentinaPlayer("Dybala", "87")
player2 = FrancePlayer("Giroud", "81")

print(player2.getName() + " umurnya " + player2.setAge("32"))
# Output: Giroud umurnya 32
```

### Override method parent
```python
class Player:
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed

    def getName(self):
        return self.name
    
    def getSpeed(self):
        return self.speed
    
    def getSkill(self):
        return 'normal'

# Inheritance dari class Player
class ArgentinaPlayer(Player):
    def getSkill(self):
        return 'cepat'
    

class ThailandPlayer(Player):
    pass

player = ArgentinaPlayer('Dybala', '86')
print(player.getName() + " skillnya " + player.getSkill())

player2 = ThailandPlayer('Tore', '81')
print(player2.getName() + " skillnya " + player2.getSkill())

# Output: Dybala skillnya cepat    
# Output: Tore skillnya normal
```

### Memanggil method parent dengan keyword super
```python
class Player:
    def __init__(self, name):
        self.name = name

    def getName(self):
        return self.name
        
    def getSkill(self):
        return 'normal'

# Inheritance dari class Player
class ArgentinaPlayer(Player):
    def __init__(self, name):
        # Player.__init__(self, name)
        super().__init__(name)
        print('hello argentina!')
    
    def getSkill(self):
        return 'cepat'

player = ArgentinaPlayer('Dybala')
print(player.getName() + " skillnya " + player.getSkill())
# Output: hello argentina!
#         Dybala skillnya cepat
```

### Private / Protected
```python
class Player:
    def __init__(self, name):
        self.name = name
        self.__age = '23' # __age adalah variabel private / protected

    def getName(self):
        return self.name
    
    def getAge(self):
        return self.__age

# Inheritance dari class Player
class ArgentinaPlayer(Player):
    pass

player = ArgentinaPlayer('Dybala')
# mengganti nilai variabel private __age secara langsung (tanpa method)
# player._Player__age = '25'
print(player.getAge())
# Output: 23
```

### Static method dan Class method
```python
class Player:
    job = 'pemain bola'

    def __init__(self, name):
        self.name = name
    
    def getName(self):
        return self.name

    @staticmethod
    def retiredIn(age):
        return str(40 - age)
    
    @classmethod
        def generalInfo(cls, age):
            return cls.job + ' ini akan pensiun dalam ' + cls.retiredIn(age) + ' tahun'

# player = Player('Giroud')
# print(player.getName())

# print('Pensiun dalam ' + Player.retiredIn(32) + ' tahun')
print(Player.generalInfo(31))
# Output: pemain bola ini akan pensiun dalam 9 tahun
```

### Property dan setter
```python
class Player:
    def __init__(self, name, age):
        self.name = name
        self.age  = age
    
    @property
    def infoPlayer(self):
        return self.name + ' adalah ' + self.age
    
    @infoPlayer.setter
        def infoPlayer(self, data):
            name, age = data.split(' ')
            self.name = name
            self.age  = age

player = Player('Giroud', '31')
# print(player.infoPlayer())
player.infoPlayer = 'OlivierGiroud 32'
print(player.infoPlayer)
# Output: OlivierGiroud adalah 32
```
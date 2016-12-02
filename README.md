# learn_python

## FooBar
```python
cont = 0
for i in xrange(1,1000):
    if i < 1000:
        if i%3 == 0 or i%5 == 0:
            cont = cont + i
            print i
print cont    
```

## Fibonacci
```python
nLimit = 4000000
counter = 0
list = [0,1]
i = 1

while list[i] < nLimit:
    i = i+1
    list.append(list[i-1] + list[i-2])

    if list[i] > nLimit:
        list.pop()
        break
    
for i in list:
    if i%2 == 0:
        counter = counter  + i

print list
print counter
```

## Largest Prime Factor
```python
import math
number = 600851475143
Max = int(math.floor(math.sqrt(number)))
list = xrange(2,Max+1)
marked = [0]*len(list)
primes = []
factors = []

for i in xrange(0,len(list)):
    if marked[i] == 0:
        for j in range(i**2,len(list)):
            if list[j]%list[i] == 0:
                marked[j] = 1
                
for i in xrange(0,len(list)):
    if marked[i] == 0:
        primes.append(list[i])

#print marked  
#print primes
        
marked = [0]*len(primes)

for i in xrange(0,len(primes)):
    if number%primes[i] == 0:
        marked[i] = 1;
        
for i in xrange(0,len(primes)):
    if marked[i] == 1:
        factors.append(primes[i])
        

#print marked
print factors
```

## Palindrome
```python
import math
max_number = 999

def is_pali(number):
    s = str(number)
    s_rev = s[::-1]
    if s == s_rev:
        return True
    
largest = 0
current = 0
for i in xrange(max_number,100,-1):
    for j in xrange(max_number,100,-1):
        number = i*j
        #print number
        if (is_pali(number)):
            if number >  largest:
                largest = number
                print (i,j,number)
```

## Inefficient smaller divisors
```python
#numbers = 5
#list = range(5,numbers+1)
list = [2,3,5,7,8,9,11,13,16,17,19,20]
marked = [0]*len(list)
loops = 1
iterator = 1
#iterator = 12252240
#iterator = 232792560
while (sum(marked) < len(marked)):

    
    for i in xrange(len(list)):
        
        if ( iterator % list[i] == 0 ):
            marked[i] = 1
        else:
            marked[i] = 0
            
    #print iterator, marked    
    
    iterator = iterator + 1

    #loops = loops + 1
    #if loops > 3000:
    #    break
       
print iterator-1
```

##Difference of squares
```python
number = 100
list = range(1,number + 1)
acum = 0

for i in xrange(number+1):
    acum = acum + i**2
    
square_of_sum = (number*(number+1)/2)**2
print acum
print square_of_sum
print square_of_sum - acum
```

## 10001st Prime
```python
lista = range(2,500000)
marked = [0]*len(lista)
prime = [2]
resto = []

for j in range(10000):
    #print lista
    #print marked
    
    for i in xrange(len(lista)):
        if lista[i] % prime[-1] == 0:
            marked[i] = 1
    #print marked
    
    resto = []
    for i in xrange(len(marked)):
        if marked[i] == 0:
            resto.append(lista[i])
    
    lista = resto
    marked = [0]*len(lista)
    #print resto
        
    prime.append(resto[0])     

print prime[-1]
```

## Largest product in a series
```python

long_number = """73167176531330624919225119674426574742355349194934
96983520312774506326239578318016984801869478851843 
85861560789112949495459501737958331952853208805511 
12540698747158523863050715693290963295227443043557
66896648950445244523161731856403098711121722383113
62229893423380308135336276614282806444486645238749
30358907296290491560440772390713810515859307960866
70172427121883998797908792274921901699720888093776
65727333001053367881220235421809751254540594752243
52584907711670556013604839586446706324415722155397
53697817977846174064955149290862569321978468622482
83972241375657056057490261407972968652414535100474
82166370484403199890008895243450658541227588666881
16427171479924442928230863465674813919123162824586
17866458359124566529476545682848912883142607690042
24219022671055626321111109370544217506941658960408
07198403850962455444362981230987879927244284909188
84580156166097919133875499200524063689912560717606
05886116467109405077541002256983155200055935729725
71636269561882670428252483600823257530420752963450"""

max = 0

long_number = long_number.replace(" ","")
long_number = long_number.replace("\n","")
#print long_number

n = len(long_number)

for i in xrange(n-13+1):
    num = long_number[i:13+i]
    if num.find("0") == -1:
        acum = 1
        for i in xrange(13):
            acum = int(num[i])*acum

        if acum > max:
            max = acum
            print "MaxString = %s  Factorial = %d" % (num,acum)
```

##Efficient Eratosthenes
```python
import math

max = 2000000
numbers = range(0,max+1)

marked = [1] *( max +1 )
#print numbers
#print marked

for i in xrange(2, int(math.floor(math.sqrt(max))) + 1):
    if marked[i] == 1:
        
        cont = 0
        current = 0
        while (current <= max):
            marked[i**2 + cont*i] = 0
            cont = cont + 1
            current = i**2 + cont*i


cont = 0
for j in xrange(len(marked)):
    if marked[j] == 1:
        cont = cont + numbers[j]

#print marked
print cont -1 
```

## Power Digits Sum [16]
```python
n = 2**1000

n_as_string = str(n)

cont = 0
for i in xrange(len(n_as_string)):
    cont = cont + int(n_as_string[i])

print cont
```

## Factorial Digits Sum [20]
```python
n = 100

cont = 1
for i in range(n, 0, -1):
    cont =  cont*i

number_as_string = str(cont)

cont = 0
for i in xrange(len(number_as_string)):
    cont = cont + int(number_as_string[i])

print cont
```

## 1000-digit Fibonacci Number [25]
```python
l = 1000
fib = [1,1]

k = 2
#
while len(str(fib[-1])) < l:
    x = fib[k-1] + fib[k-2]
    fib.append(x)
    k = k + 1

print k, fib[k-1]
```

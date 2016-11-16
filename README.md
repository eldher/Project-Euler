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

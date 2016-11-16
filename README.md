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
'''python
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
'''

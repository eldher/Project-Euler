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

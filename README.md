# SWE_2021_41_2024_2_week_6
___
## Week 4 Assignment
* My Repository Link
>[week 4 repository](https://github.com/hjii159/SWE_2021_41_2024_2_week_4)
* Problem
> **Happy Number** \
> Write an algorithm to determine if a number n is happy.
>
>A happy number is a number defined by the following process:
>
>Starting with any positive integer, replace the number by the sum of the squares of its digits.
>Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
>Those numbers for which this process ends in 1 are happy.
>Return true if n is a happy number, and false if not.
>
* My Code
```python
def isHappy(n):
  t = n
  s = set()
  while t != 1 and not t in s:
    s.add(t)
    sum = 0
    while t > 10:
      x = t % 10
      #print(x)
      t = t//10
      #print(t)
      sum += x*x
    t = sum
    #print("new t:", t)
  #print(s)
  return t == 1

#print(isHappy(2)) # >>> False
#print(isHappy(19)) # >>> True
#print(isHappy(23587514)) # >>> True
```
* Desciption of my code

## Week 5 Assignment <Docker>

> ```command
> docker exec <container-name> cat /etc/os-release
> ```
> ```command
> docker exec <container-name> git --version
> ```
> ```command
> docker exec <container-name> python3 --version
> ```
> ```command
> docker inspect --format="{{ .HostConfig.Binds }}" <container-name>
> ```

# SWE_2021_41_2024_2_week_6

## Week 4 Assignment
* My Repository Link
>[week 4 repository](https://github.com/hjii159/SWE_2021_41_2024_2_week_4)

* Problem
> **Happy Number** \
> Write an algorithm to determine if a number n is happy.
>
> A happy number is a number defined by the following process:
>
> Starting with any positive integer, replace the number by the sum of the squares of its digits. \
> Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. \
> Those numbers for which this process ends in 1 are happy. \
> Return true if n is a happy number, and false if not. 

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

My code repeats the process of adding squares of all digits of the input number. \
If a number, which is the sum of squares of digits, is repeated in a non-1 number, **it will never reach 1**. \
So, put the numbers in the list to confirm that the same number is not repeated.


## Week 5 Assignment <Docker>

> ```command
> $ docker exec <container-name> cat /etc/os-release
> PRETTY_NAME="Ubuntu 24.04.1 LTS"
> NAME="Ubuntu"
> VERSION_ID="24.04"
> VERSION="24.04.1 LTS (Noble Numbat)"
> VERSION_CODENAME=noble
> ID=ubuntu
> ID_LIKE=debian
> HOME_URL="https://www.ubuntu.com/"
> SUPPORT_URL="https://help.ubuntu.com/"
> BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
> PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
> UBUNTU_CODENAME=noble
> LOGO=ubuntu-logo
> ```
> > **exec** : Commands that allow specific commands to be executed in the container \
> > **cat /etc/os-release** : Command to check the os version on Linux \
> > My container's OS is Ubuntu 24.04.
> 
> ```command
> $ docker exec <container-name> git --version
> git version 2.43.0
> ```
> > **git --version** : Command to check the version of git in the contatiner \
> > It is also used to check if git is installed in the container.
> ```command
> $ docker exec <container-name> python3 --version
> Python 3.12.3
> ```
> > **python3 --version** : Command to check the version of python in the contatiner \
> > It is also used to check if python3 is installed in the container.
> ```command
> $ docker inspect --format="{{ .HostConfig.Binds }}" <container-name>
> [/home/hjii/2024/ossp:/mnt/container_dir]
> ```
> > **inspect --format="{{ .HostConfig.Binds }}"** : Commands to check the mount information for that container on the host \
> > (Data may be stored by connecting the directory of the host server and the directory of the container.) \
> > In my ouput, host directory is </home/hjii/2024/ossp> and connected container directory is </mnt/container_dir>.

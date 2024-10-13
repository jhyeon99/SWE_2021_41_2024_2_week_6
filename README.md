# SWE_2021_41_2024_2_week_6

## **Week 4 Assignment**

[Week 4](https://github.com/jhyeon99/SWE_2021_41_2024_2_week_4/tree/main)

```python
def isHappy(n):
  num = n
  # (max digit of n) 10 * (max squares of one digits number) 81 = 810
  # so, range 1000 is safe
  visit = [False for _ in range(1000)]
  while num > 1:
    num = sum(int(digit)**2 for digit in str(num))
    if visit[num]:
      break
    visit[num] = True
  if num == 1:
    return True
  else:
    return False 
```

This code verifies that the given number is Happy Number.

A happy number is a number defined by the following process:
* Starting with any positive integer, replace the number by the sum of the squares of its digits.
* Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
* Those numbers for which this process ends in 1 are happy.

Check the cycle with 1000 bool variables and see if there is a Happy number. The maximum value of the sum of squares of each ten-digit number is 810, so the out of index does not occur.

## **Week 5 Assignment**

>```bash
>docker exec ossp_container cat /etc/os-release
>```
>This command executes the cat /etc/os-release command inside a running container to display information about the operating system installed in the container.

>```bash
>docker exec ossp_container git --version
>```
>This command checks the version of Git installed in the specified container.

>```bash
>docker exec ossp_container python3 --version
>```
>This command checks the version of Python 3 installed in the specified container.

>```bash
>docker inspect --format="{{ .HostConfig.Binds }}" <container_name>
>```
>This command inspects a container and outputs the bind mounts (or volumes) associated with it.

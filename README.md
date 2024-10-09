# SWE_2021_41_2024_2_week_6

## Week 4 Assignment 
> Introduction to Python.
> Write python code that determines whether or not a given integer is happy

### My submission
<code>
def isHappy(n):

  prev = []
  prev.append(n)

  while(n != 1):
    next = 0
    temp = 0
    while(n > 0):
      temp = n % 10
      n -= temp
      n = n / 10
      next += temp * temp
    if next in prev:
      print(prev)
      return False
    else:
      n = next;
      prev.append(n);

  print(prev)
  return True
</code>

- Keep track of what n was with the list prev
- For every loop, calculate the next number using the variable temp
- If n becomes 1, break out of the while loop and return True
- If n is already in prev, this number is an unhappy number that will cycle numbers in prev. Return False.

[Link to Git Repository](https://github.com/jiyooniboon/SWE_2021_41_2024_2_week_4)


## Week 5 Assignment

> Introduction to Docker.
> Set up an environment for a container with Linux OS, git, and python. Should also have a bound mount.

### My submission

<code> docker exec ossp-container cat /etc/os-release </code>
Prints information on the OS used inside the container. 
<code> docker exec ossp-container git —version </code>
Prints the version of git installed in the container. 
<code> docker exec ossp-container python --version </code>
Prints the version of python installed in the container.
<code> docker inspect -format="{{ .HostConfig.Binds }}" ossp-container </code>
Prints the bind mounts associated with the container, in this format: <code>host_path:container_path</code>.

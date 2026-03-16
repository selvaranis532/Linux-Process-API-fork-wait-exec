# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to create new process using Linux API system calls fork() and getpid() , getppid() and to print process ID and parent Process ID using Linux API system calls

```
#include <stdio.h>
#include <unistd.h>

int main()
{
    fork();

    printf("Process ID: %d\n", getpid());
    printf("Parent Process ID: %d\n", getppid());

    return 0;
}



```

## OUTPUT


<img width="787" height="236" alt="Screenshot 2026-03-15 135651" src="https://github.com/user-attachments/assets/bcaa9f8a-8969-4d31-a4fe-13f986b188e8" />







## C Program to execute Linux system commands using Linux API system calls exec() , exit() , wait() family

```
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main()
{
    pid_t pid;

    pid = fork();

    if(pid == 0)
    {
        printf("Child process executing ls command\n");
        execl("/bin/ls","ls",NULL);
    }
    else
    {
        wait(NULL);
        printf("Parent process finished\n");
    }

    return 0;
}

```

## OUTPUT

<img width="742" height="251" alt="Screenshot 2026-03-15 135808" src="https://github.com/user-attachments/assets/58cd0474-aaa8-44ed-afe0-bf54a35c15e2" />




# RESULT:
The programs are executed successfully.

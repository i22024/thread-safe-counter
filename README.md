Windows 10   WSL2  

# thread-safe-counter

Using time command,

Mutex performance

![image](https://user-images.githubusercontent.com/83895507/121439053-1a796800-c9c0-11eb-84a6-66023d24681d.png)

Semaphore  performance

![image](https://user-images.githubusercontent.com/83895507/121439108-3b41bd80-c9c0-11eb-977a-d51692c7d4a1.png)






Mutex does not have a longer running time than Semaphore because it simply locks and unlocks an object so that two threads cannot use it at the same time.
If a semaphore is used, the shared resource can be used by the process according to the semaphore value obtained through the function, and if another process is being used, the CPU is waiting quietly.
A process using a semaphore must check the semaphore value and change it while using the resource, so that other semaphore users wait.
The semaphore value is also continuously changed, resulting in many code lines during iteration, and the CPU's waiting time becomes longer in proportion to the number of iterations.
Therefore, I think that this difference in time occurred because the CPU spends more time waiting than the Mutex.   

# Build and run
```bash
docker run --rm -it -v $(pwd)/app:/usr/src/app -w /usr/src/app gcc bash
# Build and run the code
g++ -pthread main.cpp && chmod +x a.out && ./a.out
```


# Note

- Critical section needs to meet these conditions.
  - **Mutual Exclusion**: Only one process can be in the critical section at any time.
  - **Progress**: No process is forced to wait for an available resource.
    - If no process is executing in the critical section and other processes are waiting outside the critical section, then only those processes that are not executing in their remainder section can participate in deciding which will enter the critical section next, and the selection can not be postponed indefinitely.
  - **Bounded Waiting**: A limit is placed on the number of times a process can request to enter the critical section.
- Critical section's basic structure
    ```c
    do {
        // entry section
        critical section
        // exit section
        remainder section
    } while (true);
    ```

# References

- https://www.geeksforgeeks.org/petersons-algorithm-in-process-synchronization/
- https://www.geeksforgeeks.org/introduction-of-process-synchronization/
  
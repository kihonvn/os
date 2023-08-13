# Multithreading

Writing a multithreading program is more tricky than one that doesn't use threads.

Each thread in a multithreading program has its own stack and, thus, execution point. However, threads share the same heap with the main program.
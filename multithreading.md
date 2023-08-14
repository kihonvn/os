# Multithreading

Likewise dealing with processes, OS also uses context switch in multithreading model.

Writing a multithreading program is trickier than one that doesn't use threads.

Each thread in a multithreading program has its own stack and, thus, execution point. However, threads share the same heap with the main program.
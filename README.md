# minitalk

A client/server program that transmits a string between two processes using only UNIX signals (`SIGUSR1`/`SIGUSR2`), one bit at a time. The bonus version adds an acknowledgment mechanism and captures the sender's PID via `sigaction`'s `siginfo_t`.

## Concepts covered
- UNIX signals as an inter-process communication (IPC) mechanism
- Bit-by-bit encoding/decoding of a string over a signal channel
- Bonus: ACK signal back to the client, `siginfo_t`-based sender identification

## Build & run
```sh
make        # builds client and server (mandatory part)
make bonus  # builds client_bonus and server_bonus
```
```sh
./server            # prints its PID
./client <PID> <message>
```

---
Part of the 42 School curriculum.

# 0x05. Processes and Signals

This project introduces Linux process management and signal handling.  
You’ll learn how to identify processes, read PIDs, kill or terminate processes, filter them by name, and work with infinite loops.  
All scripts follow ALX requirements and use `#!/usr/bin/env bash`.

---

## Files

| File Name | Description |
|----------|-------------|
| `0-what-is-my-pid` | Displays the PID of the running script |
| `1-list_your_processes` | Lists all running processes in a user-friendly, hierarchical format |
| `2-show_your_bash_pid` | Filters process list and displays only lines containing the word “bash” |
| `3-show_your_bash_pid_made_easy` | Displays only PIDs and names of processes whose name contains “bash” (without using `ps`) |
| `4-to_infinity_and_beyond` | Runs an infinite loop printing “To infinity and beyond” every 2 seconds |
| `5-dont_stop_me_now` | Stops the `4-to_infinity_and_beyond` process using `kill` |
| `6-stop_me_if_you_can` | Stops the `4-to_infinity_and_beyond` process without using `kill` or `killall` |

---

## Project Description

This project helps you understand how Linux systems handle processes.  
You’ll learn about:

- Process IDs (PIDs)  
- Foreground vs background processes  
- Listing processes using different tools  
- Infinite loops and controlling script execution  
- Sending signals to processes  
- Stopping and managing processes from the terminal  

By practicing these tasks, you gain real system-admin skills that apply everywhere: servers, DevOps tools, cloud environments, and debugging.

---

## How to Use the Scripts

All scripts must start with:

```bash
#!/usr/bin/env bash
# Description of what the script does

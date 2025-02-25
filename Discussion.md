
# Log Extraction Solution (C++) – FarMart Tech Campus Recruitment 2025

## 📄 Problem Statement

This project aims to efficiently extract log entries from a large log file (~1 TB) based on a user-specified date. Each log entry begins with a timestamp, followed by a log level and a descriptive message.

### Example Log Format:
```
2024-12-01 14:23:45 INFO User logged in
2024-12-01 14:24:10 ERROR Failed to connect to the database
2024-12-02 09:15:30 WARN Disk space running low
```

## 🎯 Objective

- Extract all log entries corresponding to a specific date provided as a command-line argument.
- Save the extracted logs into a separate output file located in the `output/` directory.
- Optimize the solution for both speed and efficient memory usage.

## ⚙️ Solution Approach

- The program reads the log file **line by line** to minimize memory consumption.
- Each line is compared against the provided date.
- If the date matches, the log entry is written directly to an output file.
- Automatically creates the `output/` directory if it doesn’t already exist, ensuring compatibility with both Windows and Linux systems.

## 🛠️ How to Run

### Prerequisites
- A C++ compiler (e.g., `g++` on Linux/macOS or `MSVC` on Windows)

### Compilation Command:
```bash
g++ -o extract_logs src/extract_logs.cpp
```

### Execution Command:
```bash
./extract_logs <path_to_log_file> <YYYY-MM-DD>
```

#### Example Usage:
```bash
./extract_logs logs/large_log.txt 2024-12-01
```

### Expected Output:
- A file named `output/output_2024-12-01.txt` containing all log entries for the specified date.

## 📑 Project Structure

```
├── src/
│   └── extract_logs.cpp       # Main C++ script for log extraction
├── output/                    # Directory for storing extracted logs
├── Discussion.md              # Detailed solution discussion and alternative approaches
├── README.md                  # Project documentation (this file)
```

## 📝 Discussion.md Overview

### 🔍 Solutions Considered:

1. **Memory-intensive approach:**  
   - Loading the entire log file into memory.  
   - Discarded due to inefficiency with large files.

2. **Line-by-line processing (Final Solution):**  
   - Efficient memory usage and faster execution.  
   - Reads and processes the log file incrementally, avoiding memory bottlenecks.

### ✅ Final Solution Highlights:
- Reads the log file incrementally, processing entries in real-time.
- Writes matching entries directly to the output file to minimize memory overhead.
- Automatically handles output directory creation on both Windows and Linux platforms.

### 📋 Execution Steps:
1. Compile the code using a C++ compiler.
2. Run the executable with the specified log file path and date.
3. The output log file will be generated automatically in the `output/` directory.

**👨‍💻 Developed by:** Ayush Sehgal  
**📅 Date:** February 25, 2025  
**📧 Contact:** [ayushks.cs.21@nitj.ac.in]

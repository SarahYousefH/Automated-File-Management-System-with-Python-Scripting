
# 📁 Automated File Management System

This project automates various file and directory management tasks using Python scripting. It supports custom command sequences, configured via JSON, and logs results in either CSV or log formats. The system implements the **Factory Design Pattern** to maintain flexibility and scalability. Comprehensive logging is provided for debugging and operation tracking.

## ✨ Features
- 🔄 **Move Last File**: Moves the most recent file from one directory to another.
- 🗂 **File Categorization**: Categorizes files into "large" and "small" based on a threshold size.
- 🧮 **File Counting**: Counts the number of files in a directory.
- 🗑 **File Deletion**: Deletes a specific file from a directory.
- ✏️ **File Renaming**: Renames a file in a given directory.
- 📜 **Directory Listing**: Lists all files and directories.
- 🔠 **File Sorting**: Sorts files by name, date, or size.

## 🛠️ Configuration
This system is highly configurable through a `config.json` file, allowing you to customize:
- `Threshold_size`: Defines the size limit for file categorization.
- `Max_commands`: The maximum number of commands allowed per script.
- `Max_log_files`: Specifies how many log files are retained before the oldest are deleted.
- `Same_dir`: Whether passed and failed logs are saved in the same directory.
- `Output`: Selects between "csv" or "log" formats for the results.

### Example `config.json`
```json
{
  "Threshold_size": "10KB",
  "Max_commands": 5,
  "Max_log_files": 7,
  "Same_dir": false,
  "Output": "csv"
}
```

## 🚀 How to Use
To execute the system, use the following command:

```bash
python script_executor.py -i input_script -o output_folder_name
```

- `-i input_script`: Specifies the path to the script file containing the commands.
- `-o output_folder_name`: Specifies the path to the output log or CSV file.

### Example Script (`script.txt`)
```txt
Mv_last source_directory destination_directory
Count directory
Delete file_to_delete directory
Categorize directory
```

## 🏗️ Design Patterns
This project utilizes the **Factory Design Pattern** to manage command creation, ensuring clean and modular code. Each command (e.g., Move, Delete, Categorize) is implemented as a class, and the factory handles the creation of these command objects.

## 📋 Logging
We use Python’s `logging` module to track the execution of commands. Logs can be output in either CSV or plain text formats.

- **CSV**: Lists each command and its result (pass/fail).
- **Log**: Provides a detailed breakdown of each command's execution.

### Example Logging Command:
```bash
python script_executor.py -i script.txt -o outputFile
```

Logs are stored in `output.log` (or as CSV if configured). Logs contain information about each command, success or failure status, and are managed to prevent excessive log file buildup.

## 🔬 Test Cases
Our system has been thoroughly tested, including:
1. Moving files from one directory to another.
2. Counting the number of files in directories.
3. Deleting and renaming files.
4. Categorizing files based on size.

## 🔧 Future Ideas
- 🔐 **File Encryption**: Implement file encryption for added security.
- 🗜 **File Compression**: Support automatic compression of large files.

## 👥 Contributors
 **Sarah Hassouneh**  and  **Asmaa Abed Al-Rahman Fares**

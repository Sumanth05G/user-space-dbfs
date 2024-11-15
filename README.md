# Table File Operations

This project provides a library and a set of executables for working with file-based tables. It allows creating, deleting, and managing table files, rows, and columns, along with user-accessible functions for reading and writing records. The project ensures that all functions and binaries can be used system-wide, just like standard utilities.

---

## Features

### Library Functions
1. **Table File Operations**
   - **Create**: `int create_string_table_file(char *filename, int num_rows, int num_columns, int record_size);`
   - **Delete**: `int delete_string_table_file(char *filename);`

2. **Row and Column Management**
   - **Create Row**: `int create_row(char *filename, char *row_name);`
   - **Delete Row**: `int delete_row(char *filename, char *row_name);`
   - **Create Column**: `int create_column(char *filename, char *column_name);`
   - **Delete Column**: `int delete_column(char *filename, char *column_name);`

3. **Open, Read, and Write Records**
   - **Open**: `struct File_ID open_string_table_file(char *filename, char *row_name, char *column_name);`
   - **Read**: `void* read_table(struct File_ID fid);`
   - **Write**: `int write_table(struct File_ID fid, void *buffer, size_t size);`

### Executable Binaries
Six executables are provided:
- `create_table_file`: Create a table file.
- `delete_table_file`: Delete a table file.
- `create_row`: Add a new row to the table file.
- `delete_row`: Remove a row from the table file.
- `create_column`: Add a new column to the table file.
- `delete_column`: Remove a column from the table file.

---

## Setup Process

### 1. Building the Static Library
To allow global usage of `#include <table_file.h>` in any program, we build a static library and place it in the system's library path.

#### Steps:
1. **Compile `table_file.c` to an object file**:
   ```bash
   gcc -c table_file.c -o table_file.o

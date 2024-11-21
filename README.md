
# File Processing Utility

A robust, asynchronous file processing utility designed for handling large text files efficiently by reading and writing data in chunks. This project uses modern .NET features and includes comprehensive unit tests to ensure reliability.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Modules](#modules)
6. [Testing](#testing)
7. [Examples](#examples)
8. [Contributors](#contributors)
9. [License](#license)

---

## Introduction

This project provides a utility for processing files asynchronously. It reads data from a source file in manageable chunks and writes it to a destination file. The project aims to handle large files efficiently without excessive memory consumption. Key functionality includes reading and writing operations, error handling, and test coverage for edge cases like empty files or non-existent source files.(Depending on data types, a rough estimate is 4-5 seconds per 1gb)

---

## Features

- **Asynchronous Processing**: Handles large files without blocking the main thread.
- **Chunked Reading and Writing**: Processes data in chunks to optimize memory usage.
- **Error Handling**: Gracefully handles scenarios like non-existent or empty files.
- **Unit Testing**: Comprehensive test coverage for all modules.
- **Extensible Design**: Modular architecture for easy integration and enhancements.

```

## Installation

### Prerequisites
- [.NET SDK](https://dotnet.microsoft.com/download) (6.0 or later)
```
```
### Build Project
```bash
dotnet build
```

### Run Tests
```bash
dotnet test
```

---

## Usage

### Running the Main Program
1. Place the source file (`data.csv`) in the root directory.
2. Run the program to process the file and create `letters_copy.csv`:
   ```bash
   dotnet run
   ```

### Code Snippet
Example usage in `Main_Procces_File`:
```csharp
string sourceFile = "data.csv";
string destinationFile = "letters_copy.csv";
await Procces_Files.ProcessFileAsync(sourceFile, destinationFile);
```

---

## Modules

### 1. `Procces_File_1`
Handles the overall file processing workflow:
- Reads data using `Read_Data_1`.
- Writes data using `Write_Data_1`.

### 2. `Read_Data_1`
Provides functionality to read files in chunks:
- Reads data in 8 MB chunks using a buffer for efficiency.

### 3. `Write_Data_1`
Handles writing chunks of data to a file:
- Writes data to a file asynchronously.

---

## Testing

The project includes extensive unit tests for all modules. Tests are implemented using the `Microsoft.VisualStudio.TestTools.UnitTesting` framework.

### Test Coverage
- **File Processing**:
  - Transfer of data from source to destination.
  - Handling of empty and non-existent files.
- **Reading**:
  - Chunk handling for small, large, and empty files.
- **Writing**:
  - Correct writing of chunks to a new file.
  - Overwriting of existing files.

### Run Tests
```bash
dotnet test
```

---

## Examples

### Processing a File
```csharp
await Procces_Files.ProcessFileAsync("source.csv", "destination.csv");
```

### Reading a File in Chunks
```csharp
var reader = new Read_Data();
await foreach (var chunk in reader.ReadChunksAsync("source.csv"))
{
    Console.WriteLine(chunk);
}
```

### Writing Data in Chunks
```csharp
var writer = new Write_Data();
await writer.WriteChunksAsync("destination.csv", chunks);
```

---

## Contributors

- **Fiordi Toska** - Project Developer
- Contributions welcome! Feel free to submit a pull request or raise an issue.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

# Code Collector

*This README was written by ChatGPT, provided the collected code, generated by the Code Collector tool.*

## Table of Contents

- [Roadmap](#roadmap)
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Sample Output](#sample-output)
- [Dependencies](#dependencies)
- [Contributing](#contributing)

## Roadmap

- [ ] Coming up with a cool name
- [x] Initial prototype
- [ ] Windows support
- [ ] Advanced format collecting (e.g., pdf, pptx, etc.)
- [ ] Additional output formats (e.g., JSON, XML)
- [ ] System-wide configuration
- [ ] Directory specific configuration
- [ ] Ignore file
- [ ] Output size optimization (e.g., collapsing functions, code blocks, etc.)
- [ ] !!! Continuous code collection (watch mode) !!!
- [ ] Interactive CLI mode
- [ ] Packaging for Linux distributions

And more...

## Overview

**Code Collector** is a Rust-based tool designed to collect and organize source code files from specified directories. It offers flexible configuration options to include or exclude specific paths or file formats.

The collected data is then written to a single .txt file, making it easy to supply to virtually any LLM or process in any other way.

## Features

- **Flexible Path Configuration:** Specify multiple directories to scan for code files.
- **Format Filtering:** Collect files based on specified formats/extensions.
- **Ignore Paths:** Exclude certain directories or files from the collection process.
- **Output Options:** Write the collected data to a specified output file.

## Installation

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install)

### Steps

1. **Clone the Repository:**

   ```sh
   git clone https://github.com/iwannabeacookie/CodeCollectoR
   ```

2. **Navigate to the Project Directory:**

   ```sh
   cd CodeCollectoR
   ```

3. **Install the Project:**

    ```sh
    cargo install --path .
    ```

4. **Configure PATH (if needed):**

   Ensure that the Cargo installation directory is in your system's PATH. The default installation directory is `$HOME/.cargo/bin`.

   ```sh
    echo $PATH | grep ".cargo/bin"
   ```

   If no output provided, proceed with the following steps.

   Edit your shell profile file (e.g., `~/.bashrc`, `~/.zshrc`, `~/.profile`) and add the following line:

   ```sh
    export PATH="$HOME/.cargo/bin:$PATH"
   ```

    Changes will take effect after you restart your terminal or run `source ~/.bashrc` (or the corresponding file).

## Usage

**Code Collector** can be configured via command-line arguments to specify paths, file formats, ignored directories, and the output file.

### Command-Line Arguments

- `-p, --paths <PATHS>`: Space-separated list of directories to scan.
- `-f, --formats <FORMATS>`: Space-separated list of file formats/extensions to include (e.g., `rs,py,js`).
- `-i, --ignore-paths <IGNORE_PATHS>`: Space-separated list of paths to exclude from scanning.
- `-o, --output <OUTPUT_FILE>`: Path to the output file where collected data will be written.

### Example

```sh
./code_collector \
  --paths ./src ./lib \
  --formats rs py \
  --ignore-paths ./src/tests ./lib/exclude \
  --output collected_code.txt
```

This command will:

- Scan the `./src` and `./lib` directories.
- Include only `.rs` and `.py` files.
- Ignore the `./src/tests` and `./lib/exclude` directories.
- Write the collected data to `collected_code.txt`.

## Sample Output

Upon successful execution, the application will display a confirmation message:

```
Code collection completed. Output written to collected_code.txt
```

The `collected_code.txt` file will contain the structured data of the collected code files based on the specified configurations.

## Contributing

Contributions are welcome! If you have suggestions for improvements, bug fixes, or new features, please open an issue or submit a pull request.

### Steps to Contribute

1. **Fork the Repository**

2. **Create a New Branch**

   ```sh
   git checkout -b feature/YourFeature
   ```

3. **Commit Your Changes**

   ```sh
   git commit -m "Add some feature"
   ```

4. **Push to the Branch**

   ```sh
   git push origin feature/YourFeature
   ```

5. **Open a Pull Request**

---

*Thank you for using Code Collector! If you have any questions or need assistance, feel free to reach out.*

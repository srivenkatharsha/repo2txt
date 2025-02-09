# repo2txt

## Overview
`repo2txt` is a Python tool designed to streamline the preparation of codebase training data for GPT-style models (LLMs). It is particularly useful for passing an entire codebase to a GPT model. This script automates the process of compiling project or repository assets into a single, structured text file or Word document. The output includes a hierarchical representation of the directory structure along with the contents of each file, providing a comprehensive view of the codebase.

## Features
- **Directory/File Tree**: Generates a detailed overview of the repository's directory and file structure.
- **File Contents**: Includes the content of each file, offering a comprehensive view into the code or text within the repository.
- **Output Formats**: Supports output in both `.txt` and `.docx` formats.
- **Customizable Ignoring Mechanism**: Provides options to ignore specific file types, individual files, and directories, allowing for a tailored documentation process.
- **Command-Line Flexibility**: Various command-line arguments are available to customize the script's output according to the user's needs.
- **Estimated token count**: Provides an estimated token count for the generated .txt (or .docx) file. Uses **o200k_base** encoding.

## Usage

<!-- clone the repository instruction-->
To use `repo2txt`, clone the repository to your local machine using the following command in your terminal:

```bash
git clone https://github.com/srivenkatharsha/repo2txt.git
```

Before running repo2txt, ensure you have the necessary dependencies installed.  You can install them using pip:

```bash
pip install -r requirements.txt
```

navigate to the repo2txt directory:

```bash
cd repo2txt/src/repo2txt
```

Run the script from the command line by specifying the path to the repository and the desired output file name. For example:

```bash
python repo2txt.py -r [path_to_repo] -o [output_file_name]
```

Replace `[path_to_repo]` with the path to your repository and `[output_file_name]` with your desired output file name (including the `.txt` or `.docx` extension).

By default, if no path is specified, the script operates in the current directory. Similarly, if no output file name is provided, it defaults to `output.txt`.

### Optional Command-Line Arguments:

- `-r`, `--repo_path`: Specify the path to the repository. Defaults to the current directory if not specified.
- `-o`, `--output_file`: Name for the output file. Defaults to "output.txt".
- `--ignore-files`: List of file names to ignore (e.g., `--ignore-files file1.txt file2.txt`). Specify 'none' to ignore no files.
- `--ignore-types`: List of file extensions to ignore (e.g., `--ignore-types .log .tmp`). Defaults to a predefined list in `config.json`. Specify 'none' to ignore no types.
- `--exclude-dir`: List of directory names to exclude (e.g., `--exclude-dir dir1 dir2`). Specify 'none' to exclude no directories.
- `--ignore-settings`: Flag to ignore common settings files.
- `--include-dir`: Include only a specific directory and its contents (e.g., `--include-dir src`).

### Examples

1. **Documenting a Repository to a Text File**:
   ```bash
   python repo2txt.py -r /path/to/repository -o output.txt
   ```

2. **Documenting with Exclusions**:
   ```bash
   python repo2txt.py -r /path/to/repository -o output.docx --ignore-types .log .tmp --exclude-dir tests
   ```

## Contributing
Contributions to enhance `repo2txt` are always welcome. Feel free to fork the repository, make your improvements, and submit a pull request.


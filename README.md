# 📦 File Bundler CLI

A powerful, custom-built Command Line Interface (CLI) application developed in **C# / .NET**. 
This tool allows developers to effortlessly analyze, filter, sort, and bundle multiple source code files from various directories into a single consolidated file. It is especially useful for code sharing, backups, or preparing code contexts for AI models.

---

## ✨ Features

* **Multi-Language Support:** Filter files by specific extensions (e.g., `cs`, `py`, `html`) or select `all` standard code files.
* **Smart Filtering:** Automatically ignores compiled folders and binaries (`bin`, `debug`, `obj`, `publish`).
* **Custom Sorting:** Order the bundled files alphabetically by file name or group them by file extension.
* **Code Formatting:** Option to remove empty lines from the source code to keep the bundled file compact.
* **Documentation:** Automatically append the Author's name and original Source File names as comments inside the bundled file.
* **Interactive Wizard:** Includes a `create-rsp` command that guides users interactively to generate a response file (`.rsp`) for easy execution.

---

## 📥 Installation & Setup

### Prerequisites
* [.NET 8.0 SDK](https://dotnet.microsoft.com/download) (or later) installed on your machine.

### Installation Steps
1. **Clone the repository to your local machine:**
    git clone https://github.com/saraKatzen/File-Bundler-CLI.git

2. **Navigate to the project directory:**
    cd File-Bundler-CLI

3. **Build the project:**
    dotnet build

---

## 🚀 Getting Started

If you are running the tool directly from the source code using the .NET CLI, use `dotnet run --` before the commands. (If you published it as an executable, you can use `cli_sara` directly).

### 1. The `bundle` Command
Packages your code based on specified arguments.

**Syntax:**
    dotnet run -- bundle [options]

**Options:**
| Option | Alias | Description | Required |
| :--- | :--- | :--- | :--- |
| `--output` | `-o` | The path and name of the output bundle file. | Yes |
| `--language` | `-l` | Code languages to include (e.g., `cs,py,js`) or `all`. | Yes |
| `--note` | `-n` | Adds the original file name as a comment above its code. | No |
| `--sort` | `-s` | Sort order: `name` (alphabetical) or `type` (extension). | No |
| `--author` | `-a` | Adds the specified author name at the top of the file. | No |
| `--remove-empty-lines` | `-r` | Removes empty lines from the bundled code. | No |

**Example Usage:**
    dotnet run -- bundle --language cs,html --output ./my-bundle.txt --note --sort type --remove-empty-lines --author "Sara Katzen"

### 2. The `create-rsp` Command (Interactive Mode)
If you prefer not to type long commands, you can use the interactive wizard to generate a Response File (`options.rsp`).

**Run the wizard:**
    dotnet run -- create-rsp

Follow the prompts on the screen to select your languages, output path, and preferences. Once the `options.rsp` file is generated, you can execute the bundle simply by running:
    dotnet run -- @options.rsp

---

## 🛠️ Built With
* **C# / .NET 8.0**
* **System.CommandLine** library for robust CLI parsing.


# ChatBash

ChatBash is a Bash script that interacts with OpenAI's GPT models to generate and execute shell commands based on user input. It ensures that dangerous commands are identified and prompts the user for confirmation before execution.

## Prerequisites

Before using ChatBash, make sure you have the following installed on your system:

- **Bash** (Tested on Bash 4.4+)
- **curl**
- **jq**

### Installing Dependencies

You can install the required dependencies using the following command:

```bash
sudo apt-get update && sudo apt-get install -y curl jq
```

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/trackzero/chatbash.git
   cd chatbash
   ```

2. **Set up your OpenAI API Key:**

   Export your OpenAI API key as an environment variable:

   ```bash
   export OPENAI_API_KEY="your-api-key-here"
   ```

   Alternatively, you can add the above line to your `.bashrc` or `.bash_profile` to persist the environment variable across sessions.

3. **Make the script executable:**

   ```bash
   chmod +x chatbash
   ```

## Usage

Run the script with a description of what you want to accomplish:

```bash
./chatbash "Description of the task you want to accomplish"
```

Alternatively, you can run the script without any arguments, and it will prompt you for a description:

```bash
./chatbash
```

The script will generate shell commands based on the provided description using OpenAI's GPT4o model. It will then display the commands and ask for your confirmation before executing them.

### Example

```bash
./chatbash.sh "List all files in the current directory and count them"
```
### but why does it....
Fine, you want to make it executable as a regular shell command? 

```bash
sudo ln -s ~/chatbash/chatbash /usr/local/bin/chatbash  #adjust source directory as appropriate.
```


## Safety Features

- The script checks for potentially dangerous commands (e.g., `rm -rf`, `mkfs`, etc.) and warns the user before executing them.
- It prompts the user for confirmation before executing any commands.
- I'm pretty lazy when it comes to error checking and safety features so there's probably a lot I missed. Use at your own risk. Make backups first. You're on your own if you break something.  And for the love of whatever gods you prefer, do not run this on prod systems.

## Example use

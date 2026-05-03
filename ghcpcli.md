# GitHub Copilot CLI Installation Guide

## What is GitHub Copilot CLI?

GitHub Copilot CLI is a tool that helps you write code faster. You can use it in your terminal to get code suggestions and help with programming tasks.

---

## Step 1: Install Node.js

GitHub Copilot CLI needs Node.js to work. Node.js is a program that lets you run JavaScript code on your computer.

### How to install Node.js:

1. Open PowerShell (search for "PowerShell" on your computer)
2. Type this command and press Enter:
   ```powershell
   winget install OpenJS.NodeJS
   ```
3. When it asks "Do you agree to all the source agreements terms?", type `Y` and press Enter
4. **A Windows dialog will pop up asking for permission** - Click "Yes" to allow installation
5. Wait for the installation to finish

### Check if Node.js is installed:

After installation, open a new terminal and type:
```powershell
node --version
npm --version
```

You should see version numbers like:
- v25.9.0 (for Node.js)
- 11.12.1 (for npm)

---

## Step 2: Install GitHub Copilot CLI

Now that Node.js is ready, you can install GitHub Copilot CLI.

### How to install:

1. Open PowerShell or Command Prompt
2. Type this command and press Enter:
   ```powershell
   npm install -g @github/copilot
   ```
3. Wait for it to finish (it should say "changed 2 packages in 13s")

---

## Step 3: Check if it's installed correctly

To make sure GitHub Copilot CLI is installed, type:
```powershell
npm list -g @github/copilot
```

You should see something like:
```
C:\Users\Admin\AppData\Roaming\npm
└── @github/copilot@1.0.40
```

---

## Step 4: Using GitHub Copilot CLI

### Option 1: Using Command Prompt (Easiest)

Open Command Prompt and type:
```cmd
copilot --help
```

This will show you all the commands you can use.

### Option 2: Using PowerShell

If you use PowerShell, you might need to use this command:
```powershell
PowerShell -ExecutionPolicy Bypass -Command "copilot --help"
```

---

## How to Use GitHub Copilot CLI - Complete Guide

**Important Note:** All Copilot CLI commands use the `-i` flag for interactive mode. The command and your question go together in one string.

**Format:** `copilot -i "command your question here"`

---

### Step 1: First Time Setup - Login to GitHub

Before you can use Copilot, you need to connect it to your GitHub account.

**Command:**
```cmd
copilot -i "auth"
```

**What happens:**
1. A browser window opens automatically
2. You see a GitHub login page
3. Click "Authorize github" button
4. GitHub will show you a code (example: ABC-DEF-GHI)
5. Copy that code
6. Go back to your terminal and paste the code
7. Press Enter
8. Done! You're logged in

**Alternative commands:**
```cmd
copilot -i "Authenticate to GitHub"
```

**If you get an error, try:**
```cmd
copilot --help
```

---

### Step 2: Get Help and Explanations

If you have code that you don't understand, Copilot can explain it to you.

**Command:**
```cmd
copilot -i "explain function add(a, b) { return a + b; }"
```

**What Copilot does:**
- Reads your code
- Explains what it does in simple words
- Tells you what each part means

**Real example output:**
```
This is a function called "add" that:
1. Takes two parameters: a and b
2. Adds them together
3. Returns the result
```

---

### Step 3: Get Code Suggestions

You can ask Copilot to write code for you or suggest improvements.

**Command:**
```cmd
copilot -i "suggestion write a function to check if a number is even"
```

**What Copilot does:**
- Understands your request
- Writes code for you
- Gives you code that works

---

### Step 4: Get Code Examples

You can ask for examples of how to do something.

**Command:**
```cmd
copilot -i "example how to read a file in python"
```

**What Copilot does:**
- Shows you example code
- Explains how it works
- You can copy and use it in your project

---

## Common Commands

### Get help - Show all available commands
```cmd
copilot --help
```

### Check version - See which version you have
```cmd
copilot --version
```

### Login - Connect to your GitHub account
```cmd
copilot -i "auth"
```

**Alternative:**
```cmd
copilot -i "Authenticate to GitHub"
```

### Get explanation - Understand what code does
```cmd
copilot -i "explain your code here"
```

**Example:**
```cmd
copilot -i "explain const x = 5; console.log(x * 2);"
```

---

### Get suggestions - Ask Copilot to write code
```cmd
copilot -i "suggestion write a function to find the largest number in an array"
```

### Get examples - See code examples
```cmd
copilot -i "example how to create a simple Python web server"
```

---

## Real-World Examples

### Example 1: Understanding Complex Code

**Code you don't understand:**
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
```

**Command to understand it:**
```cmd
copilot -i "explain def fibonacci(n): if n <= 1: return n return fibonacci(n-1) + fibonacci(n-2)"
```

**Copilot explains:**
```
This is a function that calculates Fibonacci numbers.
Fibonacci is a sequence where each number is the sum of the two numbers before it.
Example: 1, 1, 2, 3, 5, 8, 13...

How it works:
1. If n is 0 or 1, return n directly
2. Otherwise, add the previous two Fibonacci numbers
3. This creates the Fibonacci sequence
```

---

### Example 2: Ask for Code to Do Something

**What you want:**
"I need code that converts temperature from Celsius to Fahrenheit"

**Command:**
```cmd
copilot -i "suggestion write code to convert celsius to fahrenheit"
```

**Copilot gives you:**
```python
def celsius_to_fahrenheit(celsius):
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

# Example usage:
celsius_temp = 25
fahrenheit_temp = celsius_to_fahrenheit(celsius_temp)
print(f"{celsius_temp}°C = {fahrenheit_temp}°F")
```

---

### Example 3: Learn How to Do Something

**What you want to learn:**
"How to read data from a file in Python"

**Command:**
```cmd
copilot -i "example how to read a file in python"
```

**Copilot shows you:**
```python
# Simple way to read a file
with open("myfile.txt", "r") as file:
    content = file.read()
    print(content)

# Read line by line
with open("myfile.txt", "r") as file:
    for line in file:
        print(line)

# Read all lines as a list
with open("myfile.txt", "r") as file:
    lines = file.readlines()
```

---

## Tips for Using Copilot CLI

### Tip 1: Be Specific with Your Questions
❌ **Bad:** `copilot -i "suggestion write code"`
✅ **Good:** `copilot -i "suggestion write a function to sort an array from smallest to largest number"`

### Tip 2: Include Examples
❌ **Bad:** `copilot -i "explain my code"`
✅ **Good:** `copilot -i "explain function getMax(arr) { return Math.max(...arr); }"`

### Tip 3: Ask for Help When Stuck
```cmd
copilot -i "suggestion I have an error in my code. How do I fix it?"
```

### Tip 4: Get Different Suggestions
If you don't like the first answer, ask again:
```cmd
copilot -i "suggestion another way to check if a number is prime"
```

---

## Common Use Cases

### For Beginners:
- Ask Copilot to **explain** code you found online
- Ask for **examples** of how to do things
- Get **suggestions** for simple tasks

### For Experienced Programmers:
- Get code **patterns** for complex problems
- **Explain** unfamiliar code
- **Optimize** existing code

### For Learning:
```cmd
copilot -i "example how to create a simple calculator in javascript"
copilot -i "explain what does this code do?"
copilot -i "suggestion write better code for this problem"
```

---

## Keyboard Shortcuts in Terminal

### If Copilot is slow to respond:
Press `Ctrl + C` to stop and try again

### To clear the terminal:
```cmd
cls
```

### To go back to previous commands:
Press **Up Arrow** key

---

## What You Can Ask Copilot

✅ **YES - Copilot can help with:**
- Explaining code
- Writing new code
- Finding bugs
- Suggesting improvements
- Teaching programming concepts
- Providing code examples
- Answering how-to questions

❌ **NO - Copilot cannot:**
- Browse the internet
- Access your files (unless you show the code)
- Remember previous conversations
- Write extremely complex AI code (but can help!)
- Replace a programming teacher completely

---

## Troubleshooting

### Problem: "Invalid command format" error
**Solution**: Use the `-i` flag and combine the command with your question in one string.
❌ Wrong: `copilot example "how to create a calculator"`
✅ Right: `copilot -i "example how to create a calculator"`

### Problem: "git is not recognized"
**Solution**: Git is not installed or not in the system PATH. Install Git from https://git-scm.com/

### Problem: "node is not recognized"
**Solution**: Node.js PATH is not set. Open a **new terminal window** (close and reopen PowerShell/Command Prompt)

### Problem: PowerShell won't run copilot command
**Solution**: Use Command Prompt instead of PowerShell, or use:
```powershell
PowerShell -ExecutionPolicy Bypass -Command "copilot [command]"
```

---

## What You Installed

| Tool | Version | Purpose |
|------|---------|---------|
| Node.js | v25.9.0 | Runs JavaScript programs |
| npm | v11.12.1 | Package manager (installs tools) |
| GitHub Copilot CLI | v1.0.40 | AI coding assistant in terminal |

---

## Next Steps

1. Authenticate with GitHub: `copilot -i "auth"`
2. Start using: `copilot --help` to see all commands
3. Read the official docs: https://github.com/github/copilot-cli

---

## Notes

- All tools are **free to download and install**
- You need an active **GitHub account** to use Copilot CLI
- It works on Windows, Mac, and Linux
- You can always update it with: `npm install -g @github/copilot@latest`

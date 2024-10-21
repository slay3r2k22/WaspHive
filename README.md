# **Wasp-hive Documentation: The Future of Discord Bot Development**

Welcome to **Wasp-hive**, a streamlined, beginner-friendly programming language built specifically for creating and managing Discord bots. Designed to be easier than Python, Wasp-hive simplifies bot creation while offering powerful features like automatic slash command creation, logging, and built-in package management. This guide will take you through all the core aspects of Wasp-hive, from installation to advanced bot features.

## **Table of Contents**

1. [Introduction to Wasp-hive](#introduction)
2. [Installation and Setup](#installation)
3. [Basic Concepts](#basic-concepts)
4. [Creating a Discord Bot](#creating-a-discord-bot)
5. [Commands and Slash Functions](#commands-and-slash-functions)
6. [Logging and Console Output](#logging-and-console-output)
7. [Wasp-hive Packages](#packages)
8. [Custom Starter and Bot Management](#custom-starter)
9. [Full Example](#full-example)
10. [Advanced Features](#advanced-features)

---

## **1. Introduction to Wasp-hive** <a name="introduction"></a>

Wasp-hive is a language built with simplicity and efficiency in mind. Whether you're a novice or an experienced developer, Wasp-hive removes the complexities of traditional bot creation. Unlike Python or JavaScript, Wasp-hive is purpose-built for Discord bots, ensuring that all commands, packages, and functions are optimized for bot development.

### **Key Features:**

- **Simplified Syntax:** No complex setup, just clear and easy-to-read commands.
- **Built-in Discord Support:** Create bots without needing to rely on external libraries.
- **Slash Commands:** Automatic creation and management of slash commands with simple keywords.
- **Logging:** Integrated logging system to track bot activity and errors.
- **Package Management:** Easily import Wasp-hive packages for additional functionality.

---

## **2. Installation and Setup** <a name="installation"></a>

Before writing your first Wasp-hive bot, you'll need to install the language and set up your environment.

### **Installing Wasp-hive**

1. **Download Wasp-hive**: The official Wasp-hive installer can be found [here](https://yourlink.com).
2. **Run the Installer**:
   - For Windows: Double-click the installer and follow the on-screen instructions.
   - For Linux/Mac: Open a terminal and run:
     ```bash
     sudo bash wasphive-installer.sh
     ```
3. **Verify Installation**: After installation, open a terminal or command prompt and type:
   ```bash
   wasphive --version
   ```
   This will display the installed version of Wasp-hive.

### **Setting Up Your Bot**

1. **Create a Bot Script**:
   Create a new file with the `.wh` extension, such as `mybot.wh`. This file will contain all the code for your bot.

2. **Get Your Discord Bot Token**:
   Go to the [Discord Developer Portal](https://discord.com/developers/applications), create a new bot, and grab the bot token. You'll use this token to authenticate your bot.

---

## **3. Basic Concepts** <a name="basic-concepts"></a>

Wasp-hive has a simple syntax designed to be easy for everyone to use. Here's a quick look at the basic concepts:

### **Bot Initialization**
To create a bot, you simply initialize it using the following command:

```wh
bot = discord-wh.bot(token: "YOUR_BOT_TOKEN")
```

### **Slash Commands**
Slash commands are fundamental in Discord bot development. In Wasp-hive, they are created like this:

```wh
slash-make: "/hello"
slash-func:
    console: "Command executed by {command.user}"
slash-return: "Hello, {command.user}!"
```

---

## **4. Creating a Discord Bot** <a name="creating-a-discord-bot"></a>

Now, let’s create a simple bot using Wasp-hive.

### **Step 1: Initialize the Bot**

In your `.wh` script file, initialize the bot with your token:

```wh
bot = discord-wh.bot(token: "YOUR_BOT_TOKEN")
```

### **Step 2: Add a Start Log**

You can log the bot’s startup with a simple command:

```wh
start-bot-log: "{bot.username}#{bot.discriminator} is now running!"
```

### **Step 3: Start the Bot**

To start the bot, simply use the `start-bot` command. This automatically connects the bot to Discord and reloads all commands.

```wh
start-bot
```

---

## **5. Commands and Slash Functions** <a name="commands-and-slash-functions"></a>

### **Creating Slash Commands**

To create a slash command, use the `slash-make` keyword, define the command logic in `slash-func`, and return a message using `slash-return`.

```wh
slash-make: "/greet"
slash-func:
    console: "{command.user} triggered the greet command."
slash-return: "Hello, {command.user}! Welcome to the server!"
```

### **Command Functions**
The command function can include multiple operations, from logging to calculations:

```wh
slash-make: "/roll"
slash-func:
    result = rand.random_number(1, 6)
    console: "{command.user} rolled a dice and got " + result
slash-return: "{command.user}, you rolled a " + result
```

### **Error Handling**

You can also add custom error messages if the command fails:

```wh
slash-error: "Something went wrong, please try again."
```

---

## **6. Logging and Console Output** <a name="logging-and-console-output"></a>

### **Console Logs**
Use `console` to log messages directly to the terminal where the bot is running:

```wh
console: "Bot has been started."
```

### **Custom Startup Logs**
Log a message when the bot starts, showing its username and discriminator:

```wh
start-bot-log: "{bot.username}#{bot.discriminator} has started successfully."
```

---

## **7. Wasp-hive Packages** <a name="packages"></a>

### **Package Management**

Wasp-hive has built-in package management using the `wasp-pull` keyword. You can import multiple packages by separating them with commas.

```wh
wasp-pull: discord-wh, rand, whtube
```

### **Available Packages**

- **discord-wh**: Used for creating and managing Discord bots.
- **rand**: Provides random number generation, like rolling dice or selecting random items.
- **whtube**: A video downloader package, similar to yt-dl but integrated into Wasp-hive.

---

## **8. Custom Starter and Bot Management** <a name="custom-starter"></a>

### **Starting the Bot**
Wasp-hive’s `start-bot` keyword simplifies the process of starting and running your bot. Just use the following in your script:

```wh
start-bot
```

### **Custom Console Logs**
For custom console logs, use the `console` keyword, which allows you to print specific messages to the console for debugging:

```wh
console: "This is a custom log message."
```

---

## **9. Full Example** <a name="full-example"></a>

Here’s a full Wasp-hive script to demonstrate how a bot works:

```wh
wasp-pull: discord-wh, rand

bot = discord-wh.bot(token: "YOUR_BOT_TOKEN")

start-bot-log: "{bot.username}#{bot.discriminator} is now running!"

slash-make: "/hello"
slash-func:
    console: "Command executed by {command.user}"
slash-return: "Hello, {command.user}!"

slash-make: "/roll"
slash-func:
    result = rand.random_number(1, 6)
    console: "{command.user} rolled a dice and got " + result
slash-return: "{command.user}, you rolled a " + result

start-bot
```

---

## **10. Advanced Features** <a name="advanced-features"></a>

### **User Management**

Wasp-hive includes built-in functions for retrieving information about the user who triggered the command:

```wh
slash-func:
    console: "Command triggered by {command.user}"
```

### **Handling Multiple Commands**

You can create multiple commands within a single bot script. Each command is handled independently but can share resources like random number generation or custom logs.

---

### **Conclusion**

Wasp-hive is designed to make bot creation accessible to everyone, with a clear and easy-to-understand syntax. Whether you’re building your first bot or managing a large-scale bot project, Wasp-hive has the tools and features to simplify your development process.

Now, it’s your turn to start building amazing bots with Wasp-hive!

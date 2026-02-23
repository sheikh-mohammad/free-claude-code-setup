# 🚀 How to Install Claude Code Using 9Router (Free Setup)

This guide explains how to install and configure Claude Code using 9Router to use free AI providers.

## 📌 Step 1: Install 9Router Globally

First, open Command Prompt (CMD) as root/global.

Run the following command:

```bash
npm install -g 9router
```

This will install 9Router globally on your system.

## 📌 Step 2: Run 9Router

After installation, run:

```bash
9router
```

You will see options like:

- Web UI
- Terminal UI
- Hide to Tray

9Router will start a local server (localhost URL will appear in terminal).

## 📌 Step 3: Open Dashboard in Browser

1. Copy the localhost URL shown in terminal.
2. Paste it into your browser.
3. Enter the default password:

```bash
123456
```

You will now see the 9Router dashboard.

## 📌 Step 4: Connect Free Provider

1. Go to Providers (left sidebar).
2. Click Add Connection.
3. **Choose a free provider**: iFlow AI.
4. Login using Google account.
5. Authorize the connection.

Once connected, the provider status should show:

```
Active
Connected
```

## 📌 Step 5: Verify Provider in Terminal UI

Go back to CMD (where 9Router is running):

1. Select Terminal UI
2. Go to Provider
3. Press Enter on your connected provider
4. Check that status shows:

```
Active
```

If active, everything is working correctly ✅

## 📌 Step 6: Create API Key

Now:

1. Go to API Endpoint
2. Click Create Key
3. Give it any name (default is fine)
4. Copy the generated API key

⚠️ This key is required for Claude Code to work.

## 📌 Step 7: Configure Claude Code Model

1. Go to CLI Tools (left sidebar)
2. Click Claude Port
3. **Select all models:** Qwen3 Coder Plus model
4. Click Save / Apply

You should see:

```
Settings applied successfully
```

### ⚠️ Important

DO NOT close the dashboard browser.

DO NOT close the CMD where 9Router is running.

If you close it, Claude Code will stop working.

## 📌 Step 8: Run Claude Code

Open a new CMD window.

Type:

```bash
claude
```

If setup is correct:

The selected model `if/qwen3-coder-plus` will appear.

You can type:

hello

If Claude replies successfully, setup is complete 🎉

### 🔁 If Limit Ends

If usage limit ends:

#### Option 1: Create New API Key

- Delete old key
- Create new key
- Use it again

#### Option 2: Change Model

- Go to CLI Tools → Claude Port
- Select another free model
- Save & Apply

### ✅ Setup Complete

You have successfully configured:

- 9Router
- Free AI Provider
- API Key
- Claude Code CLI

Now you can use Claude Code for free through 9Router.

---

---

## 🔄 Optional: Run 9Router in Background (Hide to Tray)

When you start 9Router, you will see this option:

- Web UI  
- Terminal UI  
- **Hide to Tray**

If you select **Hide to Tray**, 9Router will:

- Run in the background  
- Minimize to the system tray  
- Keep Claude Code working without keeping the terminal open  
- Start automatically when your system boots (if enabled)

### 📍 Where is the System Tray?

The **System Tray** is located:

- On **Windows** → Bottom-right corner of the screen (near the clock, Wi-Fi, battery, and volume icons).  
- You may need to click the small **up arrow (^)** to see hidden icons.  

You will see the 9Router icon there when it is running in the background.

> 💡 Recommended for users who frequently use Claude Code and want it running all the time.

## ⭐ Support

If this guide helped you, consider starring the repository on GitHub 😊

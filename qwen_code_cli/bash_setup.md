# How to Use Claude Code with Qwen models for Free on Bash

This installation guide can be followed in Bash, WSL, Git Bash and as well as in Mac OS.

## Prerequisites
- Qwen CLI installed and authenticated
- Node.js v18+ installed

---

### Step 1: Install Required Packages

Open bash terminal and run the following command to install the Qwen Code, Claude Code, and the Claude Code Router:

```bash
npm install -g @qwen-code/qwen-code@latest @anthropic-ai/claude-code @musistudio/claude-code-router
```

### **Step 2: Create the Folders**

Paste this into bash terminal:

```bash
mkdir -p ~/.claude-code-router ~/.claude
```

---

### **Step 3: Create the Config File**

Paste this command to create and populate the config file:

```bash
cat > ~/.claude-code-router/config.json << 'EOF'
{  
  "LOG": true,  
  "LOG_LEVEL": "info",  
  "HOST": "127.0.0.1",  
  "PORT": 3456,  
  "API_TIMEOUT_MS": 600000,  
  "Providers": [  
    {  
      "name": "qwen",  
      "api_base_url": "https://portal.qwen.ai/v1/chat/completions",  
      "api_key": "$QWEN_API_KEY",  
      "models": [  
        "qwen3-coder-plus",  
        "qwen3-coder-plus",  
        "qwen3-coder-plus"  
      ]  
    }  
  ],  
  "Router": {  
    "default": "qwen,qwen3-coder-plus",  
    "background": "qwen,qwen3-coder-plus",  
    "think": "qwen,qwen3-coder-plus",  
    "longContext": "qwen,qwen3-coder-plus",  
    "longContextThreshold": 60000,  
    "webSearch": "qwen,qwen3-coder-plus"  
  }  
}
EOF
```

### Step 4: Extract Your Access Token

Open `C:\Users\PC_USER\.qwen\oauth_creds.json`:

```bash
cat ~/.qwen/oauth_creds.json
```

It should look something like this
```json
{
  "access_token": "YOUR_QWEN_ACCESS_TOKEN_HERE",
  "token_type": "Bearer",
  "refresh_token": "$QWEN_API_KEY",
  "resource_url": "portal.qwen.ai",
  "expiry_date": 1764876220290
}
```
Copy the `access_token` value:

Paste your qwen access token from oauth_creds.json file by replacing with **YOUR_QWEN_ACCESS_TOKEN_HERE**

```bash
echo 'export QWEN_API_KEY="YOUR_QWEN_ACCESS_TOKEN_HERE"' >> ~/.bashrc
source ~/.bashrc
```

> **Check Your Shell**
> Run `echo $SHELL` to see your shell. If it shows `/bin/zsh`, use ~/.zshrc instead of ~/.bashrc. If it shows `/usr/bin/bash`, stay with defualt (specified above)

like this:

```bash
   echo 'export QWEN_API_KEY="YOUR_QWEN_ACCESS_TOKEN_HERE"' >> ~/.zshrc
   source ~/.zshrc
   ```

### Step 5: Start Using

Restart the router server:

```bash
ccr restart
```

Run Claude Code with Qwen models: 

```bash
ccr code
```

Test with:

```
> hi
```

---

## Token Refresh (When you get 401 errors)

Your OAuth token expires. Refresh it by:
1. Delete the oauth_creds.json file by running this command:
  
    ```bash
    rm ~/.qwen/oauth_creds.json
    ```

2. Update the `api_key` in your config.json with the new access_token:
   
   ```bash
   echo 'export QWEN_API_KEY="YOUR_QWEN_ACCESS_TOKEN_HERE"' >> ~/.bashrc
   source ~/.bashrc
   ```

   or

   ```bash
   echo 'export QWEN_API_KEY="YOUR_QWEN_ACCESS_TOKEN_HERE"' >> ~/.zshrc
   source ~/.zshrc
   ```
   
4. Restart: `ccr restart`

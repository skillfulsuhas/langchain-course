# 🔧 LangSmith Setup Guide

## What is LangSmith?

LangSmith is a powerful monitoring and debugging platform for LangChain applications. It provides:

- 📊 **Tracing**: See every step of your LangChain execution
- 🐛 **Debugging**: Identify issues in your chains
- 📈 **Analytics**: Track performance, costs, and usage
- 🧪 **Testing**: Evaluate and compare different prompts/models

## Why Use LangSmith?

When learning LangChain, LangSmith helps you:
1. **Understand** what's happening inside your chains
2. **Debug** when things don't work as expected
3. **Optimize** your prompts and model choices
4. **Track** your learning progress

## How to Set Up LangSmith (Step-by-Step)

### Step 1: Create a LangSmith Account
1. Go to https://smith.langchain.com
2. Sign up with your email or GitHub account
3. Verify your email

### Step 2: Create a Project
1. Once logged in, click **"New Project"**
2. Name it something like `langchain-course` or `learning-langchain`
3. Click **Create**

### Step 3: Get Your API Key
1. Click on your profile icon (top right)
2. Go to **Settings** → **API Keys**
3. Click **"Create API Key"**
4. Give it a name like `local-development`
5. **Copy the API key** (you won't see it again!)

### Step 4: Update Your .env File
Open your `.env` file and update these lines:

```bash
# Enable LangSmith tracing
LANGCHAIN_TRACING_V2=true

# LangSmith endpoint (use this for global endpoint)
LANGCHAIN_ENDPOINT=https://api.smith.langchain.com

# Your LangSmith API key (paste the key you copied)
LANGCHAIN_API_KEY=lsv2_pt_xxxxxxxxxxxxxxxxxxxxx

# Your project name (must match the project you created)
LANGCHAIN_PROJECT=langchain-course
```

### Step 5: Test It!
Run your script:
```bash
uv run python main.py
```

Then go to https://smith.langchain.com and check your project - you should see the trace!

## Current Status

✅ **LangSmith is currently DISABLED** in your .env file  
This means your code will run fine, but won't send traces to LangSmith.

To enable it, follow the steps above and change:
```bash
LANGCHAIN_TRACING_V2=false  # Change this to true
```

## Troubleshooting

### Error: 403 Forbidden
- Your API key is invalid or expired
- The project doesn't exist
- You don't have permissions for the project

**Solution**: Generate a new API key and make sure the project name matches exactly.

### Error: Connection timeout
- Check your internet connection
- LangSmith might be down (check status.langchain.com)

### No traces appearing
- Make sure `LANGCHAIN_TRACING_V2=true`
- Check that your API key is correct
- Verify the project name matches exactly (case-sensitive!)

## Do You Need LangSmith for Learning?

**No!** LangSmith is optional. Your code works perfectly without it.

**However**, it's **highly recommended** for learning because:
- You can see exactly what's happening in your chains
- It helps you understand LangChain concepts better
- It's free for personal/learning use
- It's a valuable skill for production applications

## Free Tier Limits

LangSmith offers a generous free tier:
- 5,000 traces per month
- 1 project
- 7 days of data retention

Perfect for learning! 🎓
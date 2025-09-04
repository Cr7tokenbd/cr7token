# 🚀 CR7 Token Bot - Railway Deployment Guide

## 📋 **Deployment Steps**

### **1. Prepare Your Project**
- ✅ All files are ready in your project directory
- ✅ `requirements.txt` has been simplified for easier deployment
- ✅ `.env` file contains your sensitive information

### **2. Deploy to Railway**

**Option A: Deploy from GitHub**
1. Push your code to GitHub repository
2. Connect Railway to your GitHub repository
3. Railway will automatically detect Python and install dependencies

**Option B: Deploy from Local Files**
1. Install Railway CLI: `npm install -g @railway/cli`
2. Login: `railway login`
3. Initialize: `railway init`
4. Deploy: `railway up`

### **3. Environment Variables Setup**

In Railway dashboard, add these environment variables:

```env
# Telegram Configuration
TELEGRAM_BOT_TOKEN=your_telegram_bot_token_here
TELEGRAM_GROUP_ID=your_telegram_group_id_here

# Solana Configuration
SOLANA_RPC=https://api.mainnet-beta.solana.com
TOKEN_MINT=your_token_mint_address_here

# Wallet Configuration (PRIVATE KEY - KEEP SECURE!)
WALLET_PRIVATE_KEY=your_private_key_array_here

# Token Distribution Settings
TOKENS_PER_SOL=7000
MINIMUM_BUY_SOL=0.2
DISTRIBUTION_RATIO=1.0
MIN_DISTRIBUTION=1400
MAX_DISTRIBUTION=1000000
AIRDROP_AMOUNT=1000

# Buy Button and Presale
BUY_BUTTON_LINK=https://raydium.io/swap/?inputMint=sol&outputMint=YOUR_TOKEN_MINT
PRESALE_END_DATE=2025-09-06 23:59:59
PRESALE_TIMEZONE=UTC
```

### **4. Railway Configuration**

**Nixpacks Configuration (automatic):**
- Railway will automatically detect Python project
- Install dependencies from `requirements.txt`
- Start with `python main.py`

**Manual Configuration (if needed):**
Create `nixpacks.toml`:
```toml
[phases.setup]
nixPkgs = ["python3", "pip"]

[phases.install]
cmds = ["pip install -r requirements.txt"]

[start]
cmd = "python main.py"
```

### **5. Deployment Features**

**✅ Simplified Dependencies:**
- Removed complex Solana SDK dependencies
- Only essential packages for core functionality
- Faster deployment and startup

**✅ Environment Variables:**
- All sensitive data in environment variables
- Secure configuration management
- Easy to update without redeployment

**✅ Core Functionality:**
- Real-time Solana transaction monitoring
- Professional Telegram alerts
- Token distribution simulation
- Presale countdown timer

### **6. Post-Deployment**

**Monitor Logs:**
```bash
railway logs
```

**Check Status:**
- Bot should start automatically
- Check Railway dashboard for deployment status
- Monitor logs for any errors

**Test Functionality:**
- Send test message to Telegram group
- Verify bot is responding
- Check transaction monitoring

### **7. Troubleshooting**

**Common Issues:**

1. **Dependencies Error:**
   - Check `requirements.txt` format
   - Ensure all packages are available on PyPI

2. **Environment Variables:**
   - Verify all required variables are set
   - Check variable names match exactly

3. **Telegram Bot:**
   - Ensure bot token is correct
   - Verify bot is added to group with admin permissions

4. **Solana RPC:**
   - Check RPC URL is accessible
   - Consider using paid RPC for better reliability

### **8. Production Tips**

**✅ Security:**
- Never commit `.env` file to repository
- Use Railway's environment variables
- Regularly rotate sensitive keys

**✅ Monitoring:**
- Set up Railway monitoring
- Monitor bot logs regularly
- Check wallet balance

**✅ Scaling:**
- Railway auto-scales based on usage
- Monitor resource usage
- Upgrade plan if needed

### **9. Support**

**Railway Documentation:**
- [Railway Docs](https://docs.railway.app/)
- [Python Deployment](https://docs.railway.app/guides/python)

**Bot Support:**
- Check logs for error messages
- Verify configuration settings
- Test with small amounts first

---

## 🎉 **Ready for Production!**

Your CR7 Token Bot is now ready for Railway deployment with:
- ✅ Simplified dependencies
- ✅ Environment variable configuration
- ✅ Professional monitoring
- ✅ Secure deployment

**Happy Deploying!** 🚀

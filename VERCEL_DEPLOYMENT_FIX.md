# Vercel Deployment Guide - Queen Koba Frontend

## 🚨 Fix for 404 Error

The 404 error occurs because Vercel doesn't know how to handle React Router routes. I've added the necessary configuration files:

✅ `frontend/vercel.json` - Vercel SPA configuration  
✅ `frontend/public/_redirects` - Fallback routing

## 🚀 Deploy to Vercel

### Option 1: Deploy via Vercel Dashboard (Recommended)

1. Go to https://vercel.com/new
2. Import your repository: `Rotz-kirwa/queen-frontend-backend`
3. Configure the project:
   - **Framework Preset**: Vite
   - **Root Directory**: `frontend`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`

4. Add Environment Variables:
   - `VITE_API_URL` = `https://your-backend-url.com` (or your backend URL)

5. Click **Deploy**

### Option 2: Deploy via Vercel CLI

```bash
# Install Vercel CLI
npm install -g vercel

# Navigate to frontend
cd frontend

# Deploy
vercel

# Follow the prompts:
# - Set up and deploy? Yes
# - Which scope? Your account
# - Link to existing project? No
# - Project name? queen-koba-frontend
# - Directory? ./
# - Override settings? No

# Deploy to production
vercel --prod
```

## ⚙️ Vercel Configuration Explained

### vercel.json
```json
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

This tells Vercel to serve `index.html` for all routes, allowing React Router to handle routing.

### _redirects
```
/*    /index.html   200
```

This is a fallback for platforms like Netlify that use `_redirects` file.

## 🔧 Environment Variables

Make sure to set these in Vercel dashboard:

```
VITE_API_URL=https://your-backend-url.com
```

**Important**: Don't include trailing slash in API URL.

## 📝 Deployment Checklist

Before deploying:

- ✅ Ensure backend is deployed and accessible
- ✅ Update `VITE_API_URL` to point to production backend
- ✅ Test all routes locally with `npm run build && npm run preview`
- ✅ Verify `vercel.json` exists in frontend folder
- ✅ Verify `_redirects` exists in frontend/public folder

## 🐛 Troubleshooting

### Still Getting 404?

1. **Check Root Directory**: Make sure Vercel is set to `frontend` as root directory
2. **Rebuild**: Trigger a new deployment in Vercel dashboard
3. **Check Build Logs**: Look for errors in Vercel deployment logs
4. **Verify Files**: Ensure `vercel.json` and `_redirects` are in the repository

### Routes Not Working?

1. **Clear Cache**: Clear browser cache and hard refresh (Ctrl+Shift+R)
2. **Check vercel.json**: Ensure it's in the `frontend` folder, not root
3. **Redeploy**: Sometimes Vercel needs a fresh deployment

### API Calls Failing?

1. **CORS**: Ensure backend has CORS enabled for your Vercel domain
2. **Environment Variables**: Check `VITE_API_URL` is set correctly
3. **HTTPS**: Make sure backend URL uses HTTPS in production

## 🎯 Expected Result

After deployment, all these routes should work:
- ✅ `/` - Home page
- ✅ `/shop` - Shop page
- ✅ `/login` - Login page
- ✅ `/signup` - Signup page
- ✅ `/contact` - Contact page
- ✅ `/story` - Story page
- ✅ `/checkout` - Checkout page

## 📞 Need Help?

If you're still experiencing issues:
1. Check Vercel deployment logs
2. Verify the configuration files are in the correct location
3. Ensure you're deploying from the `main` branch
4. Contact: info@queenkoba.com

---

**The configuration files have been added and pushed to GitHub. Redeploy on Vercel to fix the 404 error!**

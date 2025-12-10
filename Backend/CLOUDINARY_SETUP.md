# Cloudinary Setup Guide

## Why Cloudinary?
Images uploaded to serverless platforms (Vercel, Render) don't persist because the filesystem is ephemeral. Cloudinary provides cloud storage for images.

## Setup Steps

### 1. Create Cloudinary Account
1. Go to https://cloudinary.com/
2. Sign up for a free account
3. After login, you'll see your dashboard

### 2. Get Your Credentials
On the Cloudinary Dashboard, you'll find:
- **Cloud Name**
- **API Key**
- **API Secret**

### 3. Add Environment Variables

#### For Local Development (.env file):
```env
CLOUDINARY_CLOUD_NAME=your_cloud_name_here
CLOUDINARY_API_KEY=your_api_key_here
CLOUDINARY_API_SECRET=your_api_secret_here
```

#### For Render/Vercel Deployment:
Add these environment variables in your hosting platform:

**Render:**
1. Go to your service dashboard
2. Environment → Add Environment Variable
3. Add all three variables

**Vercel:**
1. Go to your project settings
2. Settings → Environment Variables
3. Add all three variables

### 4. Image Upload Features
- ✅ Automatic resize to 450×350
- ✅ Quality optimization
- ✅ Cloud storage (persistent)
- ✅ CDN delivery (fast loading)
- ✅ Folder organization (`flipr-portfolio`)

### 5. Free Tier Limits
- 25 GB storage
- 25 GB monthly bandwidth
- 25,000 transformations/month

This is more than enough for most projects!

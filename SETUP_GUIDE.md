# 🚀 Quick Setup Guide

Follow these steps to get your full-stack application running locally.

## Step 1: Install Dependencies

### Backend
```bash
cd Backend
npm install
```

### Frontend (in a new terminal)
```bash
cd Frontend
npm install
```

## Step 2: Configure Environment Variables

### Backend Configuration
1. Navigate to `Backend/` directory
2. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```
3. Edit `.env` and add your MongoDB connection string:
   ```env
   PORT=5000
   MONGO_URI=mongodb+srv://your_username:your_password@cluster.mongodb.net/company-landing
   JWT_SECRET=your_super_secret_random_string_here
   NODE_ENV=development
   CLIENT_URL=http://localhost:5173
   ```

### Get MongoDB Connection String:
1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a free account and cluster
3. Click "Connect" → "Connect your application"
4. Copy the connection string
5. Replace `<password>` with your database user password

## Step 3: Start the Servers

### Start Backend (Port 5000)
```bash
cd Backend
npm run dev
```

You should see:
```
✅ MongoDB connected successfully
🚀 Server running on port 5000
```

### Start Frontend (Port 5173) - New Terminal
```bash
cd Frontend
npm run dev
```

You should see:
```
VITE ready in XXX ms
➜  Local:   http://localhost:5173/
```

## Step 4: Access the Application

### Landing Page
Open browser: **http://localhost:5173**

You should see:
- Hero section with contact form
- Why Choose Us features
- About section
- Our Projects (empty initially)
- Happy Clients (empty initially)
- Newsletter subscription

### Admin Dashboard
Navigate to: **http://localhost:5173/admin**

**Login credentials:**
- Password: `admin123`

**Admin Features:**
1. **Add Project Tab**: Upload project with image, name, description
2. **Add Client Tab**: Upload client testimonial with photo
3. **Contact Submissions Tab**: View all contact form entries
4. **Newsletter Subscribers Tab**: View all email subscribers

## Step 5: Test the Application

### Test Contact Form (Landing Page)
1. Fill out the "Get a Free Consultation" form in hero section
2. Click Submit
3. Go to Admin Dashboard → Contact Submissions tab
4. Verify your submission appears

### Test Newsletter (Landing Page)
1. Scroll to newsletter section
2. Enter email and click Subscribe
3. Go to Admin Dashboard → Newsletter Subscribers tab
4. Verify email appears

### Test Project Creation (Admin)
1. Go to Admin Dashboard
2. Click "Add Project" tab
3. Upload an image (will auto-resize to 450×350)
4. Enter project name and description
5. Click "Create Project"
6. Go back to landing page and refresh
7. Project should appear in "Our Projects" section

### Test Client Creation (Admin)
1. Go to Admin Dashboard
2. Click "Add Client" tab
3. Upload client photo
4. Enter name, designation, testimonial
5. Click "Create Client Testimonial"
6. Go back to landing page and refresh
7. Testimonial should appear in "Happy Clients" section

## Common Issues & Solutions

### Issue: "Cannot connect to MongoDB"
**Solution:** 
- Check your `MONGO_URI` in `.env`
- Ensure your IP is whitelisted in MongoDB Atlas
- Verify database user credentials

### Issue: "CORS Error"
**Solution:**
- Ensure `CLIENT_URL` in backend `.env` is `http://localhost:5173`
- Restart backend server after changing `.env`

### Issue: Images not loading
**Solution:**
- Check that `Backend/uploads/` directory exists
- Verify backend is serving static files from `/uploads`
- Check browser console for 404 errors

### Issue: "Module not found"
**Solution:**
- Delete `node_modules/` and run `npm install` again
- Clear npm cache: `npm cache clean --force`

## Next Steps

### Development
- Customize colors in `Frontend/tailwind.config.js`
- Modify image dimensions in `Backend/middlewares/imageProcessor.js`
- Add more sections to landing page
- Enhance admin authentication

### Deployment
See `README.md` for deployment instructions to:
- **Backend**: Render, Railway, or Heroku
- **Frontend**: Vercel or Netlify
- **Database**: MongoDB Atlas (already cloud-hosted)

## Need Help?

- Check the main `README.md` for detailed documentation
- Review `.github/copilot-instructions.md` for architecture details
- Open an issue on GitHub for bugs or questions

---

**🎉 Congratulations!** Your full-stack application is now running locally.

Start building amazing features! 🚀

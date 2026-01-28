# StyleSync - iOS PWA Deployment Guide

## What is StyleSync?

StyleSync is an AI-powered wardrobe assistant that helps you create professional outfit recommendations based on your wardrobe, weather conditions, and style inspirations. It uses Google's Gemini AI for intelligent suggestions and image generation.

## Features

- **Wardrobe Management**: Add, view, and organize your clothing items by category
- **AI Image Generation**: Generate product photos of your clothes using Gemini AI
- **Style Inspiration**: Save images and links that represent your style preferences
- **Smart Outfit Generator**: Get AI-powered outfit recommendations based on weather and your personal style
- **Works Offline**: Your wardrobe data is stored locally on your device

---

## Deploying as an iOS App (Personal Use)

Since this is a Progressive Web App (PWA), you have several **free** options to deploy it:

### Option 1: GitHub Pages (Recommended - Free)

1. **Create a GitHub account** if you don't have one at [github.com](https://github.com)

2. **Create a new repository**:
   - Click "New repository"
   - Name it `stylesync` (or anything you prefer)
   - Make it **Public** (required for free GitHub Pages)
   - Click "Create repository"

3. **Upload the files**:
   - Click "uploading an existing file"
   - Drag and drop ALL files from the `stylesync-pwa` folder:
     - `index.html`
     - `manifest.json`
     - `apple-touch-icon.png`
     - `icon-192.png`
     - `icon-512.png`
   - Click "Commit changes"

4. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Under "Source", select "Deploy from a branch"
   - Select "main" branch and "/ (root)" folder
   - Click Save
   - Wait 1-2 minutes for deployment

5. **Your app will be live at**: `https://YOUR-USERNAME.github.io/stylesync/`

### Option 2: Netlify (Free)

1. Go to [netlify.com](https://netlify.com) and sign up
2. Click "Add new site" → "Deploy manually"
3. Drag and drop the entire `stylesync-pwa` folder
4. Your site will be live instantly at a random URL like `https://random-name-123.netlify.app`
5. You can customize the URL in site settings

### Option 3: Vercel (Free)

1. Go to [vercel.com](https://vercel.com) and sign up with GitHub
2. Click "Add New Project"
3. Import your GitHub repository (after uploading to GitHub)
4. Click "Deploy"
5. Your app will be live at `https://your-project.vercel.app`

---

## Installing on Your iPhone

Once deployed, open the URL in Safari on your iPhone:

1. **Open Safari** and go to your deployed URL
2. **Tap the Share button** (square with arrow pointing up)
3. **Scroll down and tap "Add to Home Screen"**
4. **Name it "StyleSync"** and tap "Add"
5. **The app icon will appear on your home screen!**

When you open it from the home screen, it will run in full-screen mode like a native app.

---

## Setting Up Gemini API Key

The app requires a Google Gemini API key for AI features:

1. Go to [Google AI Studio](https://aistudio.google.com/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy the API key
5. In StyleSync, tap the **Settings** icon (gear) in the bottom nav
6. Paste your API key and save

**Note**: The free tier gives you generous usage limits for personal use.

---

## Troubleshooting

### "Add to Home Screen" option not showing
- Make sure you're using **Safari** (not Chrome or other browsers)
- The option only appears in Safari on iOS

### AI features not working
- Check that your API key is entered correctly in Settings
- Make sure you have an internet connection
- The free Gemini API has rate limits - wait a minute and try again

### App not updating
- iOS caches PWAs aggressively
- Delete the app from home screen and re-add it
- Or clear Safari website data for your domain

### Images not loading
- Large images may take time to load
- Generated images are stored as base64 in localStorage
- If storage is full, try deleting some wardrobe items

---

## Technical Details

- **Framework**: React 19 (loaded via ESM)
- **Styling**: Tailwind CSS (via CDN)
- **AI**: Google Gemini API (1.5 Flash for text, 2.0 Flash for images)
- **Storage**: localStorage (persists on device)
- **Icons**: Lucide React

---

## Privacy

- All wardrobe data stays on YOUR device in localStorage
- Images are stored locally as base64 strings
- API calls to Gemini only include your wardrobe metadata and prompts
- No server-side storage or tracking

---

Enjoy your personal AI stylist! 👔✨

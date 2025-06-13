# Interactive 360° Product Carousel

A professional-grade interactive carousel featuring 360° product rotation, similar to the Gucci silk scarves showcase.

## 🚀 Features

- **360° Product Rotation** - Drag to rotate products in any direction
- **Touch/Swipe Support** - Mobile-friendly navigation
- **Keyboard Navigation** - Arrow keys to navigate between products
- **Responsive Design** - Works on desktop, tablet, and mobile
- **Smooth Animations** - Professional transitions and effects
- **Multiple Products** - Easy to add more products to the carousel

## 📁 Folder Structure

To use with your HiggsField videos, create this folder structure:

```
noa/
├── index.html
├── README.md
└── images/
    ├── product1/
    │   ├── ezgif-frame-001.jpg
    │   ├── ezgif-frame-002.jpg
    │   ├── ezgif-frame-003.jpg
    │   └── ... (up to ezgif-frame-108.jpg)
    ├── product2/
    │   ├── ezgif-frame-001.jpg
    │   ├── ezgif-frame-002.jpg
    │   └── ... (up to ezgif-frame-108.jpg)
    └── product3/
        ├── ezgif-frame-001.jpg
        ├── ezgif-frame-002.jpg
        └── ... (up to ezgif-frame-108.jpg)
```

## 🎬 How to Extract Frames from HiggsField Videos

### Method 1: Online Tool (Easiest)
1. Go to **ezgif.com/video-to-jpg**
2. Upload your HiggsField rotation video
3. Set "Extract every" to extract 30-40 frames
4. Download the ZIP file
5. Frames will be named `ezgif-frame-001.jpg`, `ezgif-frame-002.jpg`, etc. (keep this naming)
6. Place in appropriate product folder

### Method 2: FFmpeg (Advanced)
```bash
# Extract 36 frames evenly distributed
ffmpeg -i your_higgsfield_video.mp4 -vf "select=not(mod(n\,2))" -vsync vfr frame-%d.jpg

# Files will be automatically named in ezgif format
```

## 🛠️ Setup Instructions

1. **Clone/Download** this project
2. **Extract frames** from your HiggsField videos
3. **Organize frames** into the folder structure above
4. **Open index.html** in a web browser
5. **Test interaction** - drag products to rotate!

## ✨ Customization

### Add More Products
To add a 4th product, simply:

1. Create `images/product4/` folder with frames
2. Add a new product slide in the HTML:

```html
<div class="product-slide">
    <div class="product-viewer">
        <div 
            class="cloudimage-360"
            data-folder="images/product4/"
            data-filename="ezgif-frame-{index}.jpg"
            data-amount="108">
        </div>
    </div>
    <div class="product-info">
        <h2 class="product-title">Your Product Name</h2>
        <p class="product-description">Your product description</p>
    </div>
</div>
```

3. Update `totalSlides` in JavaScript from 3 to 4

### Adjust Frame Count
If your videos have different frame counts, update the `data-amount` attribute:
- 108 frames: `data-amount="108"` (current setting)
- 72 frames: `data-amount="72"`
- 144 frames: `data-amount="144"`

### Change Rotation Speed
Adjust these attributes for different rotation behaviors:
- `data-speed="80"` - Auto-rotation speed (if enabled)
- `data-drag-speed="150"` - Mouse/touch drag sensitivity

## 🎨 Styling

The carousel uses modern CSS with:
- Gradient backgrounds
- Smooth animations
- Box shadows
- Responsive design
- Mobile-optimized touch controls

Modify the CSS in the `<style>` section to match your brand colors and styling preferences.

## 📱 Browser Compatibility

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 🤝 Usage Tips

1. **Image Quality**: Use high-resolution frames (at least 800x800px) for best results
2. **File Size**: Optimize images to balance quality and loading speed
3. **Frame Count**: 24-36 frames provide smooth rotation without excessive file sizes
4. **Mobile Testing**: Always test on mobile devices for touch responsiveness

## 🔧 Troubleshooting

**Images not loading?**
- Check file paths and names match exactly
- Ensure images are in correct folders
- Verify frame numbering starts from 1

**360° rotation not working?**
- Make sure the JS library loaded correctly
- Check browser console for errors
- Verify `data-amount` matches your actual frame count

**Carousel navigation issues?**
- Update `totalSlides` to match number of products
- Check that all HTML structure is properly closed

## 📄 License

Free to use for personal and commercial projects.
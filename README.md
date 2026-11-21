# kb-photo-resizer
Free online image compressor &amp; resizer to reduce photo and signature file sizes to exact KB targets.
# KB Photo Resizer — Online Image Compressor & Size Reducer

**KB Photo Resizer** is a fast, browser-based image optimization tool designed to resize and compress photos to exact file sizes (in KB or MB) without noticeable quality loss.

🔗 **Official Tool:** [KB Photo Resizer](https://kbphotoresizer.com)

## Key Features
- **Exact Target File Size:** Compress images to specific thresholds (e.g., 20KB, 50KB, 100KB) for online forms, government portals, and exam applications.
- **Dimension & DPI Control:** Adjust width, height, and aspect ratio alongside file weight.
- **Privacy-First Processing:** Fast conversion with support for JPG, PNG, and WebP formats.

## Common Use Cases
- **Exam & Job Application Portals:** Meet strict signature and passport-photo upload limits.
- **Web Performance:** Reduce hero image and thumbnail weights to improve Core Web Vitals.

## Example: Client-Side Canvas Compression Logic
For developers looking at how browser-based size reduction works under the hood:

\`\`\`javascript
function compressImage(file, maxWidth, quality = 0.8) {
  const img = new Image();
  img.src = URL.createObjectURL(file);
  img.onload = () => {
    const canvas = document.createElement('canvas');
    const scale = maxWidth / img.width;
    canvas.width = maxWidth;
    canvas.height = img.height * scale;
    const ctx = canvas.getContext('2d');
    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
    canvas.toBlob((blob) => console.log('Compressed size (KB):', Math.round(blob.size / 1024)), 'image/jpeg', quality);
  };
}
\`\`\`

## Links
- Main Website: [https://kbphotoresizer.com](https://kbphotoresizer.com)

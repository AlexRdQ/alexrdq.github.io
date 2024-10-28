Panorama Viewer
This is a simple panorama viewer based on Pannellum, allowing you to display 360° panoramic images hosted externally. The viewer loads panoramas automatically and supports optional preview images.

Usage
Access the viewer through your GitHub Pages URL, passing the required parameters via the URL.

URL Parameters
panorama (required): The direct URL of the panoramic image you want to display.
preview (optional): The URL of a preview image to display while the panorama loads.
Examples
Basic Usage
Display a panorama without a preview image:

ruby
Copy code
https://yourusername.github.io/your-repository-name/?panorama=PANORAMA_URL
With Preview Image
Display a panorama with a preview image:

ruby
Copy code
https://yourusername.github.io/your-repository-name/?panorama=PANORAMA_URL&preview=PREVIEW_URL
Replace PANORAMA_URL and PREVIEW_URL with the actual URLs of your images.

Example URLs
Without preview:

ruby
Copy code
https://yourusername.github.io/panorama-viewer/?panorama=https://example.com/panorama.jpg
With preview:

ruby
Copy code
https://yourusername.github.io/panorama-viewer/?panorama=https://example.com/panorama.jpg&preview=https://example.com/preview.jpg
Features
Automatic Loading: The panorama loads automatically without user interaction.
Preview Image Support: Optionally display a low-resolution preview image while the full panorama loads.
External Image Support: Load images hosted on external servers via HTTPS.
Requirements
HTTPS URLs: The panorama and preview image URLs must use HTTPS.
CORS Enabled: The server hosting the images must allow Cross-Origin Resource Sharing (CORS).
Equirectangular Images: Panoramic images should be in equirectangular format (2:1 aspect ratio).
Customization
You can customize the viewer by editing the index.html file and adjusting the configuration options within the pannellum.viewer initialization.

Configuration Options
Located within the <script> tag in index.html:

javascript
Copy code
const config = {
    "type": "equirectangular",
    "panorama": panoramaUrl,
    "autoLoad": true,
    // Add or modify options below
    // "title": "Panorama Title",
    // "author": "Author Name",
    // "autoRotate": 2,
    // "showControls": false,
};
Refer to the Pannellum Documentation for a full list of configuration options.

Troubleshooting
Images Not Loading: Check the browser console for errors. Common issues include CORS restrictions and incorrect image URLs.
Mixed Content Errors: Ensure all image URLs use HTTPS to avoid security warnings.
CORS Errors: If you receive CORS errors, make sure the server hosting the images has appropriate CORS headers set (e.g., Access-Control-Allow-Origin: *).
Hosting on GitHub Pages
Clone or download this repository to your local machine.
Modify the index.html file if necessary.
Commit and push the files to your GitHub repository.
Enable GitHub Pages in your repository settings:
Go to Settings > Pages.
Select the main branch and root directory (/) for the source.
Save and access your site at https://yourusername.github.io/your-repository-name/.
License
This project uses Pannellum, which is licensed under the MIT License. Your usage should comply with the terms of that license.

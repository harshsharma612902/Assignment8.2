The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto-Responsive Image Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="gallery-header">
        <h1>Photo Gallery</h1>
        <p>An auto-responsive grid gallery that adapts dynamically to your screen size.</p>
    </header>

    <!-- Steps 2 & 3: Gallery Container -->
    <main class="gallery-container">
        
        <!-- Step 1: 8 Gallery Items with Images -->
        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?auto=format&fit=crop&q=80&w=500" alt="Mountain Landscape">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&q=80&w=500" alt="Tropical Beach">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&q=80&w=500" alt="Starry Night Sky">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1426604966848-d7adac902bff?auto=format&fit=crop&q=80&w=500" alt="Green Forest">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&q=80&w=500" alt="Yosemite Valley">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1447752875215-b2761acb3c5d?auto=format&fit=crop&q=80&w=500" alt="Misty Woodlands">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1511497584788-876761197069?auto=format&fit=crop&q=80&w=500" alt="Dense Jungle">
        </div>

        <div class="gallery-item">
            <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&q=80&w=500" alt="Snowy Peaks">
        </div>

    </main>

</body>
</html>
2. The CSS File (style.css)
CSS
/* Global Reset & Typography */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f8fafc;
    color: #1e293b;
    padding: 40px 20px;
}

.gallery-header {
    text-align: center;
    margin-bottom: 40px;
}

.gallery-header h1 {
    font-size: 2.25rem;
    color: #0f172a;
    margin-bottom: 8px;
}

.gallery-header p {
    color: #64748b;
    font-size: 1rem;
}

/* Steps 3 & 5: Auto-Responsive Grid Container with Gap */
.gallery-container {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    /* Automatically fits as many 260px columns as possible, then stretches them */
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); 
    gap: 20px; /* Step 5: Consistent spacing */
}

/* Gallery Item Card */
.gallery-item {
    background-color: #ffffff;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    border: 1px solid #e2e8f0;
    height: 220px; /* Uniform height for clean grid alignment */
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.gallery-item:hover {
    transform: translateY(-4px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

/* Step 4: Image Styling with width and object-fit */
.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures images crop and scale gracefully without distortion */
    display: block;
    transition: transform 0.3s ease;
}

.gallery-item:hover img {
    transform: scale(1.05);
}
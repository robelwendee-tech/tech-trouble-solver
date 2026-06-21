<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechFix - Electronics Troubleshooting Hub</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <style>
        :root {
            --primary: #2563eb;
            --dark: #1e293b;
            --light: #f8fafc;
            --accent: #ef4444;
        }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background-color: var(--light); color: var(--dark); line-height: 1.6; }
        header { background: var(--dark); color: white; padding: 1.5rem; text-align: center; }
        header h1 { margin-bottom: 0.5rem; color: #60a5fa; }
        
        .container { max-width: 1000px; margin: 2rem auto; padding: 0 1rem; }
        
        /* Device Categories */
        .categories { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1rem; margin-bottom: 3rem; }
        .card { background: white; padding: 1.5rem; border-radius: 8px; text-align: center; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); cursor: pointer; transition: transform 0.2s; }
        .card:hover { transform: translateY(-5px); }
        .card i { font-size: 2.5rem; color: var(--primary); margin-bottom: 1rem; }
        
        /* Quick Fixes Section */
        .quick-fixes { background: white; padding: 2rem; border-radius: 8px; margin-bottom: 3rem; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
        .quick-fixes h2 { margin-bottom: 1rem; color: var(--dark); border-bottom: 2px solid var(--primary); padding-bottom: 0.5rem; }
        .faq-item { margin-bottom: 1rem; padding-bottom: 1rem; border-bottom: 1px solid #e2e8f0; }
        .faq-item h3 { color: var(--primary); font-size: 1.1rem; margin-bottom: 0.25rem; }

        /* Upload Form */
        .upload-section { background: white; padding: 2.5rem; border-radius: 8px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
        .upload-section h2 { margin-bottom: 1rem; }
        .form-group { margin-bottom: 1.25rem; }
        label { display: block; margin-bottom: 0.5rem; font-weight: 600; }
        input[type="text"], select, textarea { width: 100%; padding: 0.75rem; border: 1px solid #cbd5e1; border-radius: 6px; font-size: 1rem; }
        textarea { resize: vertical; min-height: 120px; }
        input[type="file"] { background: #f1f5f9; padding: 0.75rem; border-radius: 6px; width: 100%; border: 2px dashed #cbd5e1; }
        
        button { background: var(--primary); color: white; border: none; padding: 0.75rem 1.5rem; font-size: 1rem; font-weight: 600; border-radius: 6px; cursor: pointer; width: 100%; transition: background 0.2s; }
        button:hover { background: #1d4ed8; }
    </style>
</head>
<body>

    <header>
        <h1><i class="fa-solid fa-screwdriver-wrench"></i> TechFix Portal</h1>
        <p>Find quick solutions or send us your device issues for expert help</p>
    </header>

    <div class="container">
        <h2 style="margin-bottom: 1rem;">Select Device Type</h2>
        <div class="categories">
            <div class="card">
                <i class="fa-solid fa-tv"></i>
                <h3>Television (TV)</h3>
                <p>Screen lines, power issues, audio cuts</p>
            </div>
            <div class="card">
                <i class="fa-solid fa-wifi"></i>
                <h3>Routers & Modems</h3>
                <p>No internet, blinking lights, reset loops</p>
            </div>
            <div class="card">
                <i class="fa-solid fa-mobile-screen-button"></i>
                <h3>Smartphones</h3>
                <p>Battery drain, bootloops, charging lag</p>
            </div>
        </div>

        <div class="quick-fixes">
            <h2><i class="fa-solid fa-lightbulb"></i> Common Quick Fixes</h2>
            <div class="faq-item">
                <h3>TV has sound but no picture?</h3>
                <p>Unplug the TV from the wall for 60 seconds. Press and hold the power button on the TV itself for 30 seconds while unplugged. Plug it back in. If it fails, the backlight strip might need replacement.</p>
            </div>
            <div class="faq-item">
                <h3>Router lights flashing red?</h3>
                <p>Unplug the power adapter, wait 30 seconds, and plug it back in. If the broadband light stays red, check your physical fiber/DSL line entry or contact your service provider.</p>
            </div>
        </div>

        <div class="upload-section" id="report-form">
            <h2><i class="fa-solid fa-camera"></i> Report an Electronic Issue</h2>
            <p style="color: #64748b; margin-bottom: 1.5rem;">Can't fix it? Upload details and a photo of the problem, and our technicians will review it.</p>
            
            <form name="device-issues" method="POST" data-netlify="true" enctype="multipart/form-data">
                <div class="form-group">
                    <label for="device">Device Type</label>
                    <select id="device" name="device-type" required>
                        <option value="">-- Choose Device --</option>
                        <option value="tv">Television</option>
                        <option value="router">Router / Network</option>
                        <option value="phone">Smartphone / Tablet</option>
                        <option value="other">Other Electronics</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="description">Describe the Problem</label>
                    <textarea id="description" name="problem-description" placeholder="Explain what happens (e.g., 'TV screen turns green after 10 minutes of usage')" required></textarea>
                </div>

                <div class="form-group">
                    <label for="photo">Upload Photo of the Issue</label>
                    <input type="file" id="photo" name="problem-photo" accept="image/*" required>
                </div>

                <button type="submit">Submit Issue to Technicians</button>
            </form>
        </div>
    </div>

</body>
</html>

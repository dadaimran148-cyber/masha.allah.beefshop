<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mashallah Beef Shop | Karachi</title>
    <style>
        /* Light Blue & White Theme */
        :root { 
            --bg-blue: #e3f2fd; 
            --main-white: #ffffff;
            --text-blue: #01579b;
        }

        body { font-family: 'Segoe UI', sans-serif; margin: 0; background: var(--bg-blue); color: #333; }

        /* HERO VIDEO SECTION */
        .video-container {
            position: relative;
            height: 60vh;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        #beefVideo {
            position: absolute;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: 0;
        }

        .overlay-text {
            z-index: 1;
            text-align: center;
            color: white;
            background: rgba(1, 87, 155, 0.6);
            padding: 25px;
            border-radius: 15px;
            border: 2px solid white;
        }

        /* GRID SECTION */
        .shop-container { padding: 40px 20px; max-width: 1200px; margin: auto; }
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }

        .meat-card {
            background: var(--main-white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        .meat-card img { width: 100%; height: 220px; object-fit: cover; border-bottom: 4px solid var(--text-blue); }

        .details { padding: 15px; text-align: center; }
        .details h3 { color: var(--text-blue); margin: 5px 0; }
        .pkr { font-size: 1.5rem; color: #2e7d32; font-weight: bold; }
        
        .whatsapp-link {
            display: block;
            background: #25d366;
            color: white;
            text-decoration: none;
            padding: 12px;
            border-radius: 5px;
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <section class="video-container">
        <video id="beefVideo" autoplay muted loop playsinline poster="https://images.unsplash.com/photo-1588168333986-5078d3ae3976">
            <source src="https://static.videezy.com/system/resources/previews/000/039/043/original/MEAT_SHOP_01.mp4" type="video/mp4">
        </video>
        <div class="overlay-text">
            <h1>MASHALLAH BEEF SHOP</h1>
            <p>"Your health is our priority"</p>
        </div>
    </section>

    <div class="shop-container">
        <h2 style="text-align: center; color: var(--text-blue);">Our 100% Fresh Beef Selection</h2>
        <div class="grid" id="productGrid"></div>
    </div>

    <script>
        const grid = document.getElementById('productGrid');
        
        // STATED BEEF IMAGES - ONLY BEEF
        const beefImages = [
            "https://images.unsplash.com/photo-1588168333986-5078d3ae3976?w=500",
            "https://images.unsplash.com/photo-1603048297172-c92544798d5a?w=500",
            "https://images.unsplash.com/photo-1558030006-450675393462?w=500",
            "https://images.unsplash.com/photo-1615937657715-bc7b4b7962c1?w=500"
        ];

        const titles = ["Beef Chest Piece", "Beef Steak Cut", "Premium Beef Ribs", "Fresh Beef Mince"];

        for (let i = 1; i <= 60; i++) {
            let pkr = (i % 2 === 0) ? 1200 : 880;
            let usd = (pkr / 280).toFixed(2);
            let img = beefImages[i % beefImages.length];
            let name = titles[i % titles.length];

            grid.innerHTML += `
                <div class="meat-card">
                    <img src="${img}" alt="Beef Item">
                    <div class="details">
                        <h3>${name} #${i}</h3>
                        <div class="pkr">PKR ${pkr}</div>
                        <div style="color: #666;">Approx $${usd} USD</div>
                        <a href="https://wa.me/923369849111" class="whatsapp-link">Order on WhatsApp</a>
                    </div>
                </div>
            `;
        }

        // The "Secret" to making video work on all phones:
        document.addEventListener('touchstart', function() {
            document.getElementById('beefVideo').play();
        }, { once: true });
    </script>
</body>
</html>

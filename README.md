# Beauty-story-tfg
এই ওয়েবসাইটটি সাগর ও বিউটির ভালোবাসার স্মৃতি রাখার জন্য তৈরি। Sagar ❤️ Beauty | Love 143
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beauty Story TFG 💞</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-pink: #ffc0cb; /* Soft Pink */
            --secondary-red: #ff69b4; /* Hot Pink/Rose */
            --accent-red: #e74c3c; /* Red for emphasis */
            --light-white: #fdfdff;
            --text-color: #333;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, var(--primary-pink) 0%, var(--light-white) 100%);
            color: var(--text-color);
            overflow-x: hidden;
            position: relative;
        }

        /* Floating Hearts Animation */
        .heart {
            position: fixed;
            background-color: var(--secondary-red);
            transform: rotate(-45deg);
            animation: floatHeart 10s infinite ease-in-out;
            opacity: 0;
            pointer-events: none;
            z-index: 1000;
        }
        .heart::before, .heart::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background-color: var(--secondary-red);
            border-radius: 50%;
        }
        .heart::before {
            top: -50%;
            left: 0;
        }
        .heart::after {
            left: 50%;
            top: 0;
        }

        @keyframes floatHeart {
            0% { transform: translateY(100vh) scale(0) rotate(-45deg); opacity: 0; }
            20% { opacity: 1; }
            100% { transform: translateY(-10vh) scale(1) rotate(-45deg); opacity: 0; }
        }

        /* General Styling */
        section {
            padding: 60px 20px;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 1s ease-out, transform 1s ease-out;
        }
        section.animated {
            opacity: 1;
            transform: translateY(0);
        }

        h1, h2, h3 {
            font-family: 'Great Vibes', cursive;
            color: var(--accent-red);
            margin-bottom: 20px;
        }

        h1 {
            font-size: 4em;
            text-shadow: 3px 3px 5px rgba(0,0,0,0.1);
        }

        h2 {
            font-size: 2.5em;
        }

        p {
            font-size: 1.1em;
            line-height: 1.6;
        }

        /* Homepage */
        #hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: linear-gradient(rgba(255,192,203,0.7), rgba(255,255,255,0.7)), url('https://via.placeholder.com/1500x800/ffc0cb/ffffff?text=Romantic+Background') no-repeat center center/cover;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            position: relative;
        }
        #hero h1 {
            color: white;
            font-size: 5em;
            margin-bottom: 10px;
        }
        #hero h3 {
            color: white;
            font-family: 'Montserrat', sans-serif;
            font-weight: 300;
            font-size: 1.8em;
            margin-top: 0;
        }

        .view-love-button {
            background-color: var(--accent-red);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.2em;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
            margin-top: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            text-decoration: none;
        }
        .view-love-button:hover {
            background-color: #c0392b;
            transform: translateY(-5px) scale(1.05);
        }

        /* Photo Gallery */
        #gallery {
            background-color: var(--light-white);
        }
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            max-width: 1200px;
            margin: 40px auto;
        }
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        .gallery-item:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 25px rgba(0,0,0,0.2);
        }
        .gallery-item img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            display: block;
            transition: transform 0.5s ease;
        }
        .gallery-item:hover img {
            transform: scale(1.1);
        }

        /* Fullscreen Overlay */
        .fullscreen-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease;
        }
        .fullscreen-overlay.active {
            opacity: 1;
            visibility: visible;
        }
        .fullscreen-overlay img {
            max-width: 90%;
            max-height: 90%;
            object-fit: contain;
            border-radius: 10px;
            box-shadow: 0 0 30px rgba(255,255,255,0.3);
        }
        .close-btn {
            position: absolute;
            top: 20px;
            right: 30px;
            color: white;
            font-size: 40px;
            cursor: pointer;
        }

        /* Love Message Section */
        #messages {
            background-color: var(--primary-pink);
            color: white;
            padding: 80px 20px;
        }
        #messages p {
            font-family: 'Great Vibes', cursive;
            font-size: 2.2em;
            margin: 20px 0;
            line-height: 1.4;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        #messages p:last-of-type {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.5em;
            font-weight: 700;
            margin-top: 40px;
        }

        /* Music Player */
        .music-player {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 10px 15px;
            border-radius: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            z-index: 1000;
            transition: transform 0.3s ease;
        }
        .music-player:hover {
            transform: translateY(-5px);
        }
        .music-player button {
            background: none;
            border: none;
            font-size: 1.5em;
            cursor: pointer;
            color: var(--accent-red);
            margin-left: 10px;
        }
        .music-player span {
            font-family: 'Montserrat', sans-serif;
            font-size: 0.9em;
            color: var(--text-color);
        }

        /* Footer */
        footer {
            background-color: var(--secondary-red);
            color: white;
            padding: 30px 20px;
            font-size: 1em;
            text-align: center;
            font-family: 'Montserrat', sans-serif;
            box-shadow: 0 -5px 15px rgba(0,0,0,0.1);
        }
        footer span {
            color: #fff;
            margin: 0 5px;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            h1 {
                font-size: 3em;
            }
            #hero h1 {
                font-size: 3.5em;
            }
            #hero h3 {
                font-size: 1.4em;
            }
            #messages p {
                font-size: 1.6em;
            }
            #messages p:last-of-type {
                font-size: 1.2em;
            }
            .gallery-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 2.5em;
            }
            #hero h1 {
                font-size: 3em;
            }
            #hero h3 {
                font-size: 1.2em;
            }
            .view-love-button {
                padding: 12px 25px;
                font-size: 1em;

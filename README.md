<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Green Home Grow</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: white;
            margin: 0;
            padding: 0;
        }

        /* Navigasi */
        .quick-nav {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            padding: 0.5rem 1rem;
            display: flex;
            justify-content: center;
            gap: 0.7rem;
            z-index: 3;
            flex-wrap: wrap;
        }

        .quick-nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            font-size: 1rem;
            padding: 0.5rem 1rem;
            transition: background-color 0.3s;
        }

        .quick-nav a:hover {
            background-color: rgba(225, 225, 225, 0.5);
            border-radius: 5px;
        }

        /* Header */
        header {
            text-align: center;
            margin-top: 1rem;
        }

        header .logo img {
            height: 50px;
        }

        /* Css Homepage */
        .home-page {
            background-image: url('Cuplikan layar 2024-10-08 142927 (3).png');
            background-size: cover;
            padding: 9rem;
            text-align: center;
            color: white;
            position: relative;
        }

        .home-page::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(3px);
            z-index: 2;
        }

        .home-content {
            position: relative;
            z-index: 2;
        }

        .home-page h1 {
            font-size: 62px;
            margin-bottom: 0.2rem;
        }

        .home-page h2 {
            font-size: 35px;
            margin-bottom: 0.1rem;
        }

        .home-page p {
            font-size: 25px;
            margin-bottom: 1rem;
        }

        .home-page button {
            padding: 0.9rem;
            background-color: orange;
            font-size: 18px;
            font-weight: bold;
            border: none;
            color: white;
            cursor: pointer;
            margin: 0 0.5rem;
            border-radius: 5px;
        }

        .home-page button:hover {
            background-color: rgba(225, 225, 225, 0.2);
            border-radius: 5px;
        }

        /* Css Feature */
        .features {
            padding: 4rem 2rem;
            background: white;
            font-size: 2rem;
            text-align: center;
        }

        .features h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 2rem;
        }

        .feature-list {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }

        .feature-item {
            flex: 1;
            padding: 2rem;
            text-align: left;
            max-width: 30%;
            border: 1px solid #ccc;
            border-radius: 10px;
            transition: transform 0.2s, background-color 0.2s;
            cursor: pointer;
        }

        .feature-item:hover {
            transform: scale(1.05);
            background-color: rgba(144, 238, 144, 0.6);
        }

        .feature-item h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .feature-item p {
            font-size: 1.3rem;
            margin-bottom: 1rem;
        }

        /* Lembar 2: Plant Guide */
        #plant-guide {
            padding: 6rem;
            background-color: lightyellow;
            text-align: center;
            display: none;
        }

        #plant-guide h2 {
            font-size: 3rem;
            margin-bottom: 1.2rem;
            color: black;
        }

        .plant-guide-list {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .plant-guide-item {
            background-color: white;
            border: 1px solid #ccc;
            border-radius: 10px;
            padding: 1.5rem;
            margin: 1rem;
            max-width: 400px;
            text-align: center;
            transition: transform 0.2s;
        }

        .plant-guide-item:hover {
            transform: scale(1.05);
        }

        .learn-more,
        .watch-video {
            display: inline-block;
            margin-top: 0.5rem;
            padding: 0.5rem 1rem;
            background-color: orange;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        .learn-more:hover,
        .watch-video:hover {
            background-color: #27ae60;
        }

        /* CSS Kalender */
        .calendar {
            padding: 4rem;
            text-align: center;
            background: #f9f9f9;
            display: none;
        }

        .calendar h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .calendar form {
            margin-bottom: 2rem;
            display: inline-block;
        }

        .calendar select,
        .calendar input {
            padding: 0.5rem;
            margin: 0.5rem;
            font-size: 1rem;
        }

        .calendar button {
            padding: 0.5rem 1rem;
            background-color: forestgreen;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .calendar button:hover {
            background-color: #27ae60;
        }

        .reminder-list {
            margin-top: 2rem;
            text-align: left;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            background-color: #fff;
            padding: 1rem;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .reminder-item {
            margin-bottom: 1rem;
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        /* Css Plant Journal */
        #plant-journal {
            padding: 3rem 2rem;
            background-color: antiquewhite;
            text-align: center;
            display: none;
        }

        #plant-journal h2 {
            font-size: 3rem;
            margin-bottom: 1.2rem;
            color: black;
        }

        .journal-form {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            max-width: 600px;
            margin: auto;
        }

        .journal-form textarea {
            width: 100%;
            height: 150px;
            margin-bottom: 1rem;
            padding: 1rem;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 1.2rem;
            resize: none;
        }

        .journal-form button {
            padding: 0.8rem;
            background-color: forestgreen;
            color: white;
            font-size: 1.2rem;
            font-weight: bold;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .journal-form button:hover {
            background-color: #27ae60;
        }

        .journal-entry {
            background-color: #fff;
            padding: 1rem;
            margin-top: 1rem;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: left;
        }

        .journal-date {
            font-size: 0.8rem;
            color: gray;
        }

        /* Css Marketplace */
        .marketplace {
            padding: 3rem;
            background: whitesmoke;
            font-size: 1.8rem;
            text-align: center;
            margin-bottom: 0.5rem;
        }

        .marketplace h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 1.5rem;
            color: black;
        }

        .marketplace-list {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            padding: 20px 0;
        }

        .marketplace-item {
            padding: 1rem;
            text-align: center;
            border: 1px solid #ccc;
            border-radius: 10px;
            transition: transform 0.2s, background-color 0.2s;
            cursor: pointer;
            min-width: 160px;
            background-color: #fff;
        }

        .marketplace-item:hover {
            transform: scale(1.05);
            background-color: rgba(144, 238, 144, 0.6);
        }

        .marketplace-item h2 {
            font-size: 2rem;
            font-weight: bold;
            margin: 10px 0;
        }

        .marketplace-item h3 {
            font-size: 1.5rem;
            font-weight: bold;
            color: orange;
            margin: 10px 0;
        }

        .marketplace-item p {
            font-size: 1rem;
            margin: 10px 0;
        }

        /* Css Blog */
        .blog-section {
            padding: 3rem;
            text-align: center;
        }

        .blog-section h2 {
            padding: 0;
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .blog-section p {
            padding: 0.8rem;
            font-size: 1rem;
            margin-bottom: 1rem;
        }

        .blog-posts {
            display: flex;
            overflow-x: auto;
            gap: 20px;
            padding: 1rem 0;
        }

        .blog-post {
            background-color: whitesmoke;
            border-radius: 10px;
            padding: 1rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            width: 180px;
            transition: transform 0.2s;
            flex: 0 0 auto;
        }

        .blog-post:hover {
            transform: scale(1.05);
            background-color: rgba(255, 165, 0, 0.1);
        }

        .blog-post img {
            width: 100%;
            height: auto;
            border-radius: 10px 10px 0 0;
        }

        .blog-post h3 {
            font-size: 1rem;
            margin: 1rem 0;
        }

        .blog-post p {
            font-size: 0.7rem;
            margin: 0.5rem 0;
        }

        .read-more {
            display: inline-block;
            margin-top: 0.5rem;
            text-decoration: none;
            color: orange;
            font-weight: bold;
            transition: color 0.3s;
        }

        .read-more:hover {
            color: darkorange;
        }

        /* Css Register */
        .register {
            padding: 8rem 5rem;
            background: forestgreen;
            border: 1px solid #ccc;
            border-radius: 15px;
            margin: 2rem auto;
            max-width: 500px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4);
            text-align: center;
            margin-top: 5rem;
            margin-bottom: 7rem;
        }

        .register h2 {
            font-size: 3rem;
            color: white;
            font-weight: bold;
            margin: 10px 0;
            padding: 1rem;
        }

        .register-options {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1rem;
        }

        .register-options button {
            padding: 1rem 2rem;
            font-size: 1.2rem;
            background-color: orange;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .register-options button:hover {
            background-color: darkgreen;
        }

        /* Css Form */
        form {
            background-color: lightgray;
            border: 1px solid #ccc;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            margin: 0 auto;
            max-width: 400px;
        }

        label {
            display: block;
            margin: 1rem 0 0.5rem;
        }

        input {
            width: 100%;
            padding: 0.5rem;
            margin-bottom: 1rem;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button[type="Submit"] {
            padding: 0.7rem 1.5rem;
            background-color: lightgreen;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button[type="submit"]:hover {
            background-color: darkgreen;
        }

        /* Css Error Message */
        .error-message {
            color: red;
            display: none;
            margin-top: 1rem;
        }

        /* Css Expert Consultation */
        #consultation {
            padding: 4.5rem;
            background: whitesmoke;
            text-align: center;
        }

        #consultation h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        #consultation p {
            font-size: 1rem;
            margin-bottom: 1rem;
        }

        .expert-list {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .expert-item {
            border: 2px solid #ccc;
            border-radius: 15px;
            padding: 1rem;
            width: 150px;
            text-align: center;
            background-color: white;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s;
        }

        .expert-item:hover {
            transform: scale(1.05);
            background-color: rgba(255, 165, 0, 0.1);
        }

        .expert-item img {
            width: 100%;
            border-radius: 20px;
        }

        /* Css About Us */
        .about {
            text-align: center;
            padding: 5rem;
            background-color: mintcream;
        }

        .about h1 {
            font-size: 30px;
            margin-bottom: 20px;
        }

        .about h2 {
            font-size: 18px;
            margin-bottom: 20px;
            font-weight: 100;
        }

        .about h3 {
            font-size: 15px;
            margin-bottom: 20px;
            line-height: 1.4;
            font-weight: bold;
            color: orange;
        }

        .about p {
            font-size: 12px;
            margin-bottom: 30px;
            line-height: 1.6;
            font-weight: bold;
        }

        .image-about-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .image-about {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 220px;
        }

        .image-about img {
            width: 220px;
            height: 220px;
            border-radius: 10px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .image-about h2 {
            font-size: 15px;
            margin-top: 10px;
            font-weight: bold;
            margin-bottom: 3px;
        }

        .image-about h3 {
            font-size: 13px;
            color: gray;
            font-weight: bold;
            margin-bottom: 2px;
        }

        /* Social Media Section */
        .social-media {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            margin-bottom: 15px;
        }

        .social-media div {
            display: flex;
            align-items: center;
        }

        .social-media img {
            width: 25px;
            height: 25px;
            margin-right: 10px;
        }

        .social-media p {
            margin: 0;
            font-size: 16px;
        }

        /* Css Footer */
        footer {
            background: black;
            color: white;
            text-align: center;
            padding: 1rem;
            margin-top: 2rem;
        }

        /* Media Queries for Responsiveness */

        @media (max-width: 768px) {
            .quick-nav {
                flex-direction: column;
                align-items: center;
                font-size: 1rem;
                padding: 0.4rem 0.8rem;
            }

            .home-page {
                padding: 4rem 1rem;
            }

            .home-page h1 {
                font-size: 40px;
            }

            .home-page h2 {
                font-size: 25px;
            }

            .feature-item {
                max-width: 100%;
                padding: 1rem;
            }

            .marketplace-list {
                grid-template-columns: repeat(2, 1fr);
            }

            .blog-post {
                width: 100%;
            }

            .social-media {
                flex-direction: column;
                align-items: center;
            }

            .social-media div {
                margin-bottom: 10px;
            }
    }
             .social-media img {
                width: 25px;
                height: 25px;
            }
        }

        @media (max-width: 480px) {
            .quick-nav {
            flex-direction: column;
            gap: 0.4rem;
            }

            .quick-nav a {
            font-size: 0.9rem;
            padding: 0.4rem;
            }
            .home-page {
                padding: 3rem 1rem;
            }

            .home-page h1 {
                font-size: 32px;
            }

            .home-page h2 {
                font-size: 22px;
            }

            .features h2 {
                font-size: 2rem;
            }

            .marketplace-list {
                grid-template-columns: repeat(1, 1fr);
            }

            .feature-item {
                max-width: 100%;
                padding: 0.5rem;
            }

            .blog-post {
                width: 100%;
            }

            .register h2 {
                font-size: 2rem;
            }

            .about h1 {
                font-size: 24px;
            }
            .social-media img {
                width: 20px;
                height: 20px;
            }
        }
    </style>
</head>

<body>
    <!-- Quick Navigation -->
    <div class="quick-nav">
        <a href="#home">Home</a>
        <a href="#features">Our Features</a>
        <a href="#marketplace">Marketplace</a>
        <a href="#blog-section">Blog & Articles</a>
        <a href="#about">About Us</a>
        <a href="#consultation">Consult with Experts</a>
    </div>

    <!-- Sheet Home Page -->
    <section id="home" class="home-page">
        <header>
            <div class="logo">
                <img src="C:/Users/nurai/Downloads/Green Home Grow.png" alt="Green Home Grow">
            </div>
        </header>

        <div class="home-content">
            <h1>Welcome to Green Home Grow</h1>
            <h2>Grow Organic, Healthy Live</h2>
            <p>Start Gardening at Home Today!</p>
            <button onclick="window.location.href='#register'">Start Now</button>
        </div>
    </section>

    <!-- Sheet Our Features -->
    <section id="features" class="features">
        <h2>Our Features</h2>
        <div class="feature-list">
            <div class="feature-item" onclick="showSection('plant-guide');">
                <h3>Interactive Plant Guide</h3>
                <p>Guide for caring and planting plants based on type and condition.</p>
            </div>
            <div class="feature-item" onclick="showSection('calendar');">
                <h3>Gardening Calendar</h3>
                <p>Automatic calendar feature that provides reminders for watering, fertilizing, pruning, and harvest times.</p>
            </div>
            <div class="feature-item" onclick="showSection('plant-journal');">
                <h3>Plant Journal</h3>
                <p>Record the progress of your plants here!</p>
            </div>
            <div class="feature-item" onclick="window.location.href='#marketplace';">
                <h3>Environmentally Friendly Marketplace</h3>
                <p>Online shop that sells organic seeds, compost, recycled pots, hydroponic tools, and other equipment.</p>
            </div>
            <div class="feature-item" onclick="window.location.href='#consultation';">
                <h3>Consult with an expert</h3>
                <p>Get direct advice from gardening experts.</p>
            </div>
        </div>
    </section>

    <!-- Sheet Plant Guide Section -->
    <section id="plant-guide" class="features">
        <h2>Interactive Plant Guide</h2>
        <div class="plant-guide-list">
            <div class="plant-guide-item">
                <h3>Tomato Care Guide</h3>
                <p>Learn how to plant tomatoes indoors in a tropical and dry climate.</p>
                <a href="https://jogja.idntimes.com/science/discovery/rosyida-l/cara-menanam-tomat-dalam-rumah-c1c2"
                    class="learn-more">Learn More</a>
                <a href="https://youtu.be/BV4UfwmGaYE?si=MbIY_6Wv8ORpq4uK" class="watch-video">Watch Video</a>
            </div>
            <div class="plant-guide-item">
                <h3>Melon Care Guide</h3>
                <p>Managing humidity for melons requires attention to soil moisture and diseases at Home and Humid
                    Condition.</p>
                <a href="https://vt.tiktok.com/ZS23d6BBD/" class="watch-video">Watch Video</a>
                <a href="https://youtu.be/tz_pme2Hddc?si=-2RcaIxbgunSSCqE" class="watch-video">Watch Video</a>
            </div>
            <div class="plant-guide-item">
                <h3>Mustard Greens Care Guide</h3>
                <p>How to care for mustard greens in wet environments, focusing on proper drainage and techniques for
                    growing mustard greens hydroponically indoors.</p>
                <a href="https://agri.kompas.com/read/2023/07/15/122055984/cara-menanam-sawi-hidroponik-cocok-untuk-lahan-sempit"
                    class="learn-more">Learn More</a>
                <a href="https://youtu.be/7udQtDC0vQE?si=wZlzBioVKdfB7u-z" class="watch-video">Watch Video</a>
            </div>
            <div class="plant-guide-item">
                <h3>Lettuce Care Guide</h3>
                <p>Explore ways to grow lettuce indoors using soil from the guide and outdoors in cooler climates.</p>
                <a href="https://youtu.be/9KluMD-1c9E?si=qw4mm_i0D-eW3XM" class="watch-video">Watch Video</a>
                <a href="https://youtu.be/KvgXaaYJqZM?si=QVggBFZitG331AUm" class="watch-video">Watch Video</a>
            </div>
            <div class="plant-guide-item">
                <h3>Rambutan Care Guide</h3>
                <p>Detailed methods for keeping rambutan trees small and productive and Learn about watering and pest
                    control specific to humid climates.</p>
                <a href="https://www.epicgardening.com/rambutan-tree/" class="learn-more">Learn More</a>
                <a href="https://vt.tiktok.com/ZS236URao/" class="watch-video">Watch Video</a>
            </div>
            <div class="plant-guide-item">
                <h3>Calathea Care Guide</h3>
                <p>Tips for keeping Calathea healthy indoors, especially in low-light environments and Learn about proper
                    watering schedules and how to prevent leaf curling.</p>
                <a href="https://vt.tiktok.com/ZS23dRS88/" class="watch-video">Watch Video</a>
                <a href="https://youtu.be/1dgweqGKfbw?si=7KH4q_LmT5_QywnQ" class="watch-video">Watch Video</a>
            </div>
        </div>
    </section>

    <!-- Sheet Gardening Calendar Section -->
    <section id="calendar" class="calendar">
        <h2>Gardening Calendar</h2>
        <form id="calendarForm" onsubmit="addReminder(event)">
            <label for="task">Choose Task:</label>
            <select id="task" required>
                <option value="">--Select Task--</option>
                <option value="Watering">Watering</option>
                <option value="Fertilizing">Fertilizing</option>
                <option value="Pruning">Pruning</option>
                <option value="Harvesting">Harvesting</option>
            </select>

            <label for="date">Choose Date:</label>
            <input type="date" id="date" required>

            <label for="time">Choose Time:</label>
            <input type="time" id="time" required>

            <button type="submit">Add Reminder</button>
        </form>

        <div class="reminder-list" id="reminderList">
            <h3>Your Reminders:</h3>
            <div id="reminders"></div>
        </div>
    </section>

    <!-- Plant Journal -->
    <section id="plant-journal" class="features">
        <h2>Plant Journal</h2>
        <div class="journal-form">
            <textarea id="journal-entry" placeholder="Write about your plant's progress..."></textarea>
            <button onclick="addJournalEntry()">Add Entry</button>
        </div>
        <div id="journal-entries">
            <h3>Your Entries:</h3>
            <div id="entry-list"></div>
        </div>
    </section>

    <!-- Sheet Marketplace -->
    <section id="marketplace" class="marketplace">
        <h2>Environmentally Friendly Marketplace</h2>
        <div class="marketplace-list">
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/LV5g3zESz';">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\soil-8080788_1280.jpg"
                    alt="Seeds" style="width:100%; height: auto;">
                <h3>Plant Seeds</h3>
                <p>Start from Rp 1.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/2VZaGIBK69';">
                <img src="C:/Users/nurai/OneDrive/Documents/MATKUL SEMESTER 3/PEMROGRAMAN WEBSITE/LOMBA/gardening-tools-350087_1280.jpg"
                    alt="Tools" style="width:100%; height: auto;">
                <h3>Gardening Tools</h3>
                <p>Rp 49.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/VoVsu7kOn';">
                <img src="C:/Users/nurai/OneDrive/Documents/MATKUL SEMESTER 3/PEMROGRAMAN WEBSITE/LOMBA/watering-can-397301_1280.jpg"
                    alt="Watering" style="width:100%; height: auto;">
                <h3>Plant Watering</h3>
                <p>Rp 65.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://id.shp.ee/EZwYXxV';">
                <img src="C:/Users/nurai/OneDrive/Documents/MATKUL SEMESTER 3/PEMROGRAMAN WEBSITE/LOMBA/plants-6520443_1280.jpg"
                    alt="Seeds" style="width:100%; height: auto;">
                <h3>Plant Seeds</h3>
                <p>Start from Rp 4.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/9f2lquD3uL';">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\POT tanah liat.jpg"
                    alt="Seeds" style="width:100%; height: auto;">
                <h3>Clay Pot</h3>
                <p>Start from Rp 35.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/7ALRJdB6bF';">
                <img src="C:/Users/nurai/OneDrive/Documents/MATKUL SEMESTER 3/PEMROGRAMAN WEBSITE/LOMBA/garden-5315602_1280.jpg"
                    alt="Fertilizer" style="width:100%; height: auto;">
                <h3>Organic Fertilizer</h3>
                <p>Start From Rp 3.500</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://id.shp.ee/tQyZNaY';">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\shovel-1867123_1280.jpg"
                    alt="Fertilizer" style="width:100%; height: auto;">
                <h3>Shovel</h3>
                <p>Rp 35.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/6V5k5j4DRx';">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\planting-4226838_1280.jpg"
                    style="width:100%; height: auto;">
                <h3>Gloves</h3>
                <p>Rp 15.000</p>
            </div>
            <div class="marketplace-item" onclick="window.location.href='https://s.shopee.co.id/LV6jvdPGY';">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\Gunting (2).jpg"
                    style="width:100%; height: auto;">
                <h3>Garden Scissors</h3>
                <p>Rp 42.000</p>
            </div>
        </div>
    </section>

    <!-- Sheet Blog & Article -->
    <section id="blog-section" class="blog-section">
        <h2>Blog & Articles</h2>
        <p> Read the article .can relate with us!</p>
        <div class="blog-posts">
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\tomatoes-5268689_1280.jpg">
                <h3>Hydroponic Plantation</h3>
                <p>Hydroponic Gardens function as a forum for the development of sustainable agriculture using hydroponic
                    techniques, while supporting the vision of conservation in the environment.</p>
                <a href="https://unnes.ac.id/konservasi/id/kebun-hidroponik/" class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\Kebun rooftop.jpg"
                    alt="Blog Post 2">
                <h3>The role of gardening in absorbing carbon emissions</h3>
                <p>Urban vegetation plays an important role in absorbing carbon emissions, thereby helping reduce the
                    impact of air pollution and climate change.</p>
                <a href="https://geotimes.id/opini/peran-vegetasi-dalam-penyerapan-emisi-karbon-di-perkotaan/"
                    class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\Emisi gas rumah kaca.jpg">
                <h3>Organic Agriculture Helps Solve Climate Change</h3>
                <p>Organic farming can help reduce climate change by reducing greenhouse gas emissions by around 20%
                    through more sustainable and environmentally friendly practices.</p>
                <a href="https://www.nrdc.org/bio/lena-brook/organic-agriculture-helps-solve-climate-change#:~:text=Organic%20Farming%20Reduces%20Greenhouse%20Gases&text=The%20production%20of%20these%20farm,gas%20emissions%20by%20about%2020%25."
                    class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\plant-6151414_1280.jpg">
                <h3>Why planting tons of trees isn’t enough to solve climate change</h3>
                <p>Planting trees can help combat climate change, but it is important to do so wisely as inappropriate
                    planting can disrupt ecosystems and is not always effective in capturing carbon.</p>
                <a href="https://www.sciencenews.org/article/planting-trees-climate-change-carbon-capture-deforestation"
                    class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\Eco farming (1).jpg">
                <h3>About Eco Farming</h3>
                <p>Ecofarming is an environmentally friendly agricultural practice that utilizes sustainable technology
                    and methods to maintain ecosystem balance and increase agricultural yields.</p>
                <a href="https://majoo.id/solusi/detail/ecofarminng-praktik-pertanian-ramah-lingkungan"
                    class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\Urban farming.jpg">
                <h3>The contribution of urban farming to urban food security: the case of “Buruan SAE”</h3>
                <p>Urban farming in Bandung, exemplified by Buruan SAE, enhances community welfare, food security, and
                    nutrition, but faces marketing challenges, necessitating government support for sustainable urban
                    agriculture policies similar to Singapore’s successful Edible Garden City initiative..</p>
                <a href="https://www.tandfonline.com/doi/full/10.1080/19463138.2024.2384876?src=exp-la#abstract"
                    class="read-more">Read More</a>
            </div>
            <div class="blog-post">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTARTIKEL\Hidroponik.jpg">
                <h3>Hydroponic farming – A state of art for the future agriculture</h3>
                <p>Hydroponic farming as an alternative to conventional agriculture, conserves water, avoids
                    soil-related challenges, and is environmentally friendly, though it also discusses its limitations
                    and benefits.</p>
                <a href="https://www.sciencedirect.com/science/article/abs/pii/S2214785322056048" class="read-more">Read
                    More</a>
            </div>
        </div>
    </section>

    <!-- Sheet Register or Login -->
    <section id="register" class="register">
        <h2>Register or Login</h2>
        <div class="register-options">
            <button id="register-btn" onclick="showForm('register')">Register</button>
            <button id="login-btn" onclick="showForm('login')">Login</button>
        </div>

        <div id="register-form" style="display: none;">
            <form id="registerForm" onsubmit="return validateForm('register')">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" placeholder="Enter your full name" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" placeholder="Enter your email" required>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" placeholder="Enter your password" required>
                <button type="submit">Register</button>
            </form>
            <div id="error-message-register" class="error-message"></div>
        </div>

        <div id="login-form" style="display: none;">
            <form id="loginForm" onsubmit="return validateForm('login')">
                <label for="email-login">Email:</label>
                <input type="email" id="email-login" name="email" placeholder="Enter your email" required>
                <label for="password-login">Password:</label>
                <input type="password" id="password-login" name="password" placeholder="Enter your password" required>
                <button type="submit">Login</button>
            </form>
            <div id="error-message-login" class="error-message"></div>
        </div>
    </section>

    <!-- Sheet 7 Consultation -->
    <section id="consultation" class="consultation">
        <h2>Consult with an Experts</h2>
        <div class="expert-list">
            <div class="expert-item">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\CONSULTPICT\Prof. Dr. Ir. FADJRY DJUFRY, M.Si.jpg">
                <h3>Dr. Ir.. Fadjry Djufry, M.Si.</h3>
                <p>Principal Researcher in Plant Cultivation and Production at the Plantation Research and Development
                    Center.</p>
            </div>
            <div class="expert-item">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\CONSULTPICT\Casey Houweling.webp">
                <h3>Casey Houweling</h3>
                <p>Owns and operates Houweling's Tomatoes</p>
            </div>
            <div class="expert-item">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\CONSULTPICT\Charles-dowding-.jpg">
                <h3>Charles Dowding</h3>
                <p>No Dig Gardening expert, author, and YouTuber who provides tips on no-till organic gardening.</p>
            </div>
            <div class="expert-item">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\CONSULTPICT\Monty Don (2).jpg">
                <h3>Monty Don</h3>
                <p>Lead presenter of BBC's Gardeners' World, author and renowned British gardener. He often shares
                    planting tips in gardens in the UK and around the world.</p>
            </div>
            <div class="expert-item">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\CONSULTPICT\Ron Finley.jpg">
                <h3>Ron Vinley</h3>
                <p>Known as the “Gangsta Gardener,” Ron Finley is driving the gardening movement in disadvantaged urban
                    neighborhoods in Los Angeles, promoting urban farming as a way to increase access to healthy food.
                </p>
            </div>
        </div>
    </section>

    <!-- Sheet About US -->
    <section id="about" class="about">
        <h1>This is Green Home Grow</h1>
        <h2>We hope can empower individuals to cultivate sustainable, organic gardens in their homes, promoting health,
            environmental consciousness, and food independence. We also try to provide a user-friendly digital platform
            that offers interactive gardening guides, modern techniques like urban farming and hydroponics, and access to
            eco-friendly products, enabling everyone to grow their own organic food and reduce reliance on harmful
            chemicals.</h2>

        <div class="image-about-container">
            <div class="image-about">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTTEAM\Dinar (1).jpg"
                    alt="Person 1">
                <h2>Dinar Shabrina Al Fitri</h2>
                <h3>Digital Bussines Study Program Student</h3>
            </div>
            <div class="image-about">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTTEAM\DSC06174-1.JPG"
                    alt="Person 2">
                <h2>Nur Aini Fadillah</h2>
                <h3>Digital Bussines Study Program Student</h3>
            </div>
            <div class="image-about">
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\PICTTEAM\IMG_0070.PNG"
                    alt="Person 3">
                <h2>Monica Clarissa Noni Nugroho</h2>
                <h3>Digital Bussines Study Program Student</h3>
            </div>
        </div>

        <h3>Choosing Green Home Grow now it means you are choosing a healthy life and saving the planet!</h3>

        <!-- Social Media Section -->
        <div class="social-media">
            <div>
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
                <p>@GreenHomeGrow</p>
            </div>
            <div>
                <img src="https://upload.wikimedia.org/wikipedia/commons/4/4e/Gmail_Icon.png" alt="Gmail">
                <p>greenhomegrow@gmail.com</p>
            </div>
            <div>
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\IMG_0072.PNG"
                    alt="Twitter">
                <p>@greenhomegrow</p>
            </div>
            <div>
                <img src="C:\Users\nurai\OneDrive\Documents\MATKUL SEMESTER 3\PEMROGRAMAN WEBSITE\LOMBA\Contact Person Picture.png"
                    alt="Contact">
                <p>+178 456 7890</p>
            </div>
        </div>

    </section>

    <footer>
        <p>&copy; 2024 Green Home Grow. Semua Hak Dilindungi.</p>
    </footer>

    <script>
        function showSection(sectionId) {
            // Sembunyikan semua bagian fitur
            document.getElementById('plant-guide').style.display = 'none';
            document.getElementById('calendar').style.display = 'none';
            document.getElementById('plant-journal').style.display = 'none';
            document.getElementById('consultation').style.display = 'none';

            // Tampilkan bagian yang dipilih
            document.getElementById(sectionId).style.display = 'block';
        }

        function validateForm(type) {
            let valid = true;
            let errorMessage = '';

            if (type === 'register') {
                const name = document.getElementById('name').value;
                const email = document.getElementById('email').value;
                const password = document.getElementById('password').value;

                if (!name || !email || !password) {
                    errorMessage = "Bagian ini harus diisi!";
                    valid = false;
                }
            } else if (type === 'login') {
                const emailLogin = document.getElementById('email-login').value;
                const passwordLogin = document.getElementById('password-login').value;

                if (!emailLogin || !passwordLogin) {
                    errorMessage = "Bagian ini harus diisi!";
                    valid = false;
                }
            }

            if (!valid) {
                if (type === 'register') {
                    document.getElementById('error-message-register').textContent = errorMessage;
                    document.getElementById('error-message-register').style.display = 'block';
                } else {
                    document.getElementById('error-message-login').textContent = errorMessage;
                    document.getElementById('error-message-login').style.display = 'block';
                }
            }

            return valid;
        }

        function addReminder(event) {
            event.preventDefault();

            const task = document.getElementById('task').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;
            const reminderList = document.getElementById('reminders');

            // Create a new reminder item
            const reminderItem = document.createElement('div');
            reminderItem.classList.add('reminder-item');
            reminderItem.textContent = `${task} on ${new Date(date).toLocaleDateString()} at ${time}`;

            // Append the new reminder to the list
            reminderList.appendChild(reminderItem);

            // Clear the form fields
            document.getElementById('calendarForm').reset();
        }

        function addJournalEntry() {
            const journalEntry = document.getElementById('journal-entry').value;
            const entryList = document.getElementById('entry-list');

            if (journalEntry) {
                const date = new Date().toLocaleDateString(); // Get the current date
                // Create a new journal entry item
                const entryItem = document.createElement('div');
                entryItem.classList.add('journal-entry');
                entryItem.innerHTML = `<strong>${date}</strong><br>${journalEntry}`; // Include the date

                // Append the new entry to the list
                entryList.appendChild(entryItem);

                // Clear the textarea
                document.getElementById('journal-entry').value = '';
            } else {
                alert("Please write something before adding an entry!");
            }
        }
    </script>

</body>

</html>

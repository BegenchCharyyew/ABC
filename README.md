<!DOCTYPE html>
<html lang="tk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Flexbox Öwreniş Sahypasy</title>
    <style>
        /* ==========================================================
           1. ESASY SAHYPA WE RESET STILLERI
           ========================================================== */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            background-color: #f4f7f6;
            color: #333;
        }

        /* Header üçin Flexbox (Elementleri iki gyra paýlamak) */
        header {
            display: flex; /* Header-i Flex konteýner edýär */
            justify-content: space-between; /* Elementleriň arasynda boşluk goýup, iki gyra süýşürýär */
            align-items: center; /* Vertikal boýunça merkeze deňleýär */
            background-color: #2c3e50;
            color: #fff;
            padding: 1rem 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }

        /* Nav menýu üçin Flexbox */
        nav ul {
            display: flex; /* Menýu elementlerini bir hatara düzýär */
            list-style: none;
            gap: 1.5rem; /* Elementleriň arasyndaky aralyk */
        }

        nav a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
        }

        nav a:hover {
            color: #1abc9c;
        }

        /* Main konteýner */
        main {
            max-width: 1100px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        section {
            background: #fff;
            padding: 1.5rem;
            margin-bottom: 2rem;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        h2 {
            color: #2c3e50;
            margin-bottom: 1rem;
            border-bottom: 2px solid #1abc9c;
            padding-bottom: 0.5rem;
        }

        p {
            margin-bottom: 1rem;
        }

        code {
            background-color: #eef1f5;
            padding: 0.2rem 0.4rem;
            border-radius: 4px;
            color: #e74c3c;
            font-weight: bold;
        }

        /* Flexbox boks görkeziliş stilleri */
        .flex-container {
            display: flex;
            background-color: #ecf0f1;
            padding: 1rem;
            border-radius: 6px;
            margin-top: 1rem;
            min-height: 120px;
        }

        .box {
            background-color: #3498db;
            color: white;
            padding: 1rem;
            margin: 0.5rem;
            text-align: center;
            font-weight: bold;
            border-radius: 4px;
            min-width: 60px;
        }

        /* ==========================================================
           2. FLEXBOX HÄSIÝETNAMALARY WIZUAL MYSALLARY
           ========================================================== */

        /* 1-nji Mysal: flex-direction */
        .demo-direction {
            flex-direction: row; /* Ugry: Çepden saga (Adaty ýagdaý) */
        }

        /* 2-nji Mysal: justify-content */
        .demo-justify {
            justify-content: space-between; /* Aralyklary deň paýlaýar */
        }

        /* 3-nji Mysal: align-items */
        .demo-align {
            align-items: center; /* Vertikal merkeze deňleýär */
            height: 150px;
        }

        /* 4-nji Mysal: flex-wrap */
        .demo-wrap {
            flex-wrap: wrap; /* Sypmadyk elementleri aşaky hatara geçirýär */
        }

        /* Cards layout (Flexbox ulanylyşy) */
        .card-grid {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .card {
            flex: 1 1 250px; /* Awtonom ulalmak/kiçelmek we deslapky giňlik */
            background: #e8f8f5;
            border: 1px solid #1abc9c;
            padding: 1rem;
            border-radius: 6px;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 1.5rem;
            background-color: #2c3e50;
            color: white;
            margin-top: 2rem;
        }
    </style>
</head>
<body>

    <!-- HEADER / BAŞLYK BÖLÜMI -->
    <header>
        <div class="logo">Flexbox.TK</div>
        <nav>
            <ul>
                <li><a href="#intro">Giriş</a></li>
                <li><a href="#properties">Häsiýetnamalar</a></li>
                <li><a href="#examples">Amalyat</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- GIRIŞ BÖLÜMI -->
        <section id="intro">
            <h2>CSS Flexbox Näme?</h2>
            <p><strong>Flexbox (Flexible Box Layout)</strong> — CSS3-iň elementleri sahypada bir ölçegli (setir ýa-da sütün boýunça) aňsatlyk bilen ýerleşdirmek, deňlemek we paýlamak üçin niýetlenen güýçli modulydyr.</p>
            <p>Konteýnere <code>display: flex;</code> berlen badyna, onuň içindäki ähli göni çagalanýan elementler (child elements) <strong>Flex Items</strong> (flex elementleri) bolup işleýär.</p>
        </section>

        <!-- ESASY FLEXBOX HÄSIÝETNAMALARY -->
        <section id="properties">
            <h2>Flexbox Konteýner Häsiýetnamalary</h2>

            <!-- 1. DISPLAY: FLEX -->
            <h3>1. <code>display: flex;</code></h3>
            <p>Elementi Flex konteýnere öwürýär. Ähli flex düzgünleri ussa konteýneriň içine ýazylýar.</p>

            <!-- 2. FLEX-DIRECTION -->
            <h3>2. <code>flex-direction</code></h3>
            <p>Elementleriň haýsy ugur boýunça düzüljekdigini kesgitleýär: <code>row</code> (horizontally), <code>column</code> (vertikal), <code>row-reverse</code>, <code>column-reverse</code>.</p>
            <div class="flex-container demo-direction">
                <div class="box">1</div>
                <div class="box">2</div>
                <div class="box">3</div>
            </div>

            <!-- 3. JUSTIFY-CONTENT -->
            <h3>3. <code>justify-content</code></h3>
            <p>Esasy ok (main axis - gorizontal) boýunça elementleri deňleýär. Bahalary: <code>flex-start</code>, <code>flex-end</code>, <code>center</code>, <code>space-between</code>, <code>space-around</code>, <code>space-evenly</code>.</p>
            <div class="flex-container demo-justify">
                <div class="box">1</div>
                <div class="box">2</div>
                <div class="box">3</div>
            </div>

            <!-- 4. ALIGN-ITEMS -->
            <h3>4. <code>align-items</code></h3>
            <p>Keseligine geçen ok (cross axis - vertikal) boýunça elementleri deňleýär. Bahalary: <code>stretch</code>, <code>center</code>, <code>flex-start</code>, <code>flex-end</code>.</p>
            <div class="flex-container demo-align">
                <div class="box">1</div>
                <div class="box" style="height: 80px;">2 (Beýik)</div>
                <div class="box">3</div>
            </div>

            <!-- 5. FLEX-WRAP -->
            <h3>5. <code>flex-wrap</code></h3>
            <p>Elementler bir hatara sypmadyk ýagdaýynda aşaky hatara geçmelidigi ýa-da geçmeli däldigini dolandyrýar: <code>nowrap</code>, <code>wrap</code>, <code>wrap-reverse</code>.</p>
            <div class="flex-container demo-wrap">
                <div class="box">1</div>
                <div class="box">2</div>
                <div class="box">3</div>
                <div class="box">4</div>
                <div class="box">5</div>
                <div class="box">6</div>
            </div>
        </section>

        <!-- AMALY MYSAL BÖLÜMI -->
        <section id="examples">
            <h2>Amaly Mysal: Kartoçkalar Toplomy (Responsive Cards)</h2>
            <p>Aşakdaky kartoçkalar <code>display: flex</code> we <code>flex: 1 1 250px</code> arkaly ýasaldy. Ekran kiçelse, olar awtomatiki aşak düşýärler:</p>

            <div class="card-grid">
                <div class="card">
                    <h3>Kartoçka 1</h3>
                    <p>Flexbox arkaly aňsatlyk bilen adaptiw (responsive) bloklary döredip bolýar.</p>
                </div>
                <div class="card">
                    <h3>Kartoçka 2</h3>
                    <p>Aralyklary sazlamak üçin Flexbox-yň <code>gap</code> häsiýetnamasy ulanyldy.</p>
                </div>
                <div class="card">
                    <h3>Kartoçka 3</h3>
                    <p>Bu bloklar ekranyň ölçegine görä awtomatiki giňelýär ýa-da kiçelýär.</p>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer>
        <p>&copy; 2026 CSS Flexbox Doly Gollanma. Ähli hukuklar goralan.</p>
    </footer>

</body>
</html>

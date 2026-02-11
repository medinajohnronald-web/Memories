<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>To Babi 💖</title>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Quicksand:wght@300;400;600&display=swap');

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        background: linear-gradient(135deg, #ffd5e5 0%, #ffe8f0 100%);
        font-family: 'Quicksand', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        padding: 20px;
    }

    .book {
        width: 400px;
        height: 580px;
        perspective: 2000px;
        position: relative;
    }

    .page {
        width: 100%;
        height: 100%;
        position: absolute;
        transform-origin: left;
        transition: transform 0.9s cubic-bezier(0.645, 0.045, 0.355, 1);
        border-radius: 0 20px 20px 0;
        box-shadow: 
            0 0 0 1px rgba(255, 182, 213, 0.2),
            0 20px 50px rgba(255, 77, 148, 0.15);
        backface-visibility: hidden;
    }

    .page-content {
        width: 100%;
        height: 100%;
        background: #ffffff;
        border-radius: 0 20px 20px 0;
        position: relative;
        overflow: hidden;
    }

    /* ============ COVER PAGE ============ */
    .cover-page .page-content {
        background: 
            radial-gradient(circle at 20% 20%, rgba(255, 200, 220, 0.4), transparent 40%),
            radial-gradient(circle at 80% 80%, rgba(255, 200, 220, 0.4), transparent 40%),
            linear-gradient(135deg, #ffe6f0, #fff0f6);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 40px 30px;
        border-left: 20px solid #ffc1e0;
    }

    .cover-page h1 {
        font-family: 'Dancing Script', cursive;
        font-size: 42px;
        color: #d63384;
        margin-bottom: 30px;
        text-shadow: 2px 2px 4px rgba(255, 255, 255, 0.8);
    }

    .cover-page .cover-image {
        width: 200px;
        height: 200px;
        border-radius: 50%;
        border: 6px solid white;
        box-shadow: 0 10px 30px rgba(214, 51, 132, 0.3);
        overflow: hidden;
        margin-bottom: 25px;
    }

    .cover-page .cover-image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .cover-page .cover-quote {
        font-size: 14px;
        line-height: 1.8;
        color: #c42d78;
        text-align: center;
        font-style: italic;
        max-width: 90%;
    }

    /* ============ NOTEBOOK PAGES ============ */
    .notebook-page .page-content {
        padding: 35px 30px 30px 50px;
        background: 
            linear-gradient(to right, transparent 39px, #ffb3d9 40px, transparent 41px),
            repeating-linear-gradient(
                transparent,
                transparent 31px,
                #ffe6f5 31px,
                #ffe6f5 32px
            );
        background-color: #fefefe;
        border-left: 45px solid #ffe6f0;
        position: relative;
    }

    /* Spiral holes */
    .notebook-page .page-content::before {
        content: '';
        position: absolute;
        left: 12px;
        top: 40px;
        width: 20px;
        height: calc(100% - 80px);
        background: 
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 0,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 40px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 80px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 120px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 160px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 200px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 240px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 280px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 320px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 360px,
            radial-gradient(circle, #ffb3d9 3px, transparent 4px) 0 400px;
        background-repeat: no-repeat;
    }

    .notebook-page h2 {
        font-family: 'Dancing Script', cursive;
        color: #d63384;
        font-size: 28px;
        margin-bottom: 20px;
        text-align: center;
        font-weight: 700;
    }

    /* ============ PHOTO COLLAGE ============ */
    .collage {
        position: relative;
        height: 240px;
        margin: 20px 0;
    }

    .photo {
        position: absolute;
        background: #fff;
        border-radius: 8px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        overflow: hidden;
        border: 5px solid #fff;
        transition: all 0.3s ease;
    }

    .photo:hover {
        transform: scale(1.1) !important;
        z-index: 10 !important;
        box-shadow: 0 15px 40px rgba(214, 51, 132, 0.4);
    }

    .photo img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }

    /* Overlapping collage effect - photos overlap each other */
    .p1 { 
        width: 150px; 
        height: 110px; 
        top: 5px; 
        left: 15px; 
        transform: rotate(-6deg);
        z-index: 3;
    }
    
    .p2 { 
        width: 160px; 
        height: 115px; 
        top: 30px; 
        right: 5px; 
        transform: rotate(7deg);
        z-index: 2;
    }
    
    .p3 { 
        width: 155px; 
        height: 110px; 
        bottom: 0; 
        left: 75px; 
        transform: rotate(-3deg);
        z-index: 1;
    }

    /* ============ NOTES SECTION ============ */
    .notes {
        margin-top: 15px;
        padding: 15px 10px;
        font-size: 14.5px;
        line-height: 1.9;
        color: #555;
        text-align: left;
        font-weight: 400;
        max-height: 180px;
        overflow-y: auto;
    }

    /* Custom scrollbar for notes */
    .notes::-webkit-scrollbar {
        width: 6px;
    }

    .notes::-webkit-scrollbar-track {
        background: #ffe6f5;
        border-radius: 10px;
    }

    .notes::-webkit-scrollbar-thumb {
        background: #ffb3d9;
        border-radius: 10px;
    }

    .notes::-webkit-scrollbar-thumb:hover {
        background: #ff9fc9;
    }

    .notes em {
        color: #d63384;
        font-style: italic;
        font-weight: 600;
    }

    /* ============ FINAL PAGE ============ */
    .final-page .page-content {
        background: 
            radial-gradient(circle at 10% 90%, rgba(255, 182, 213, 0.3), transparent 50%),
            radial-gradient(circle at 90% 10%, rgba(255, 182, 213, 0.3), transparent 50%),
            linear-gradient(135deg, #fff5f8, #ffe6f0);
        border-left: 15px solid #ffc1e0;
        padding: 30px 25px;
        overflow-y: auto;
    }

    /* Custom scrollbar for final page */
    .final-page .page-content::-webkit-scrollbar {
        width: 8px;
    }

    .final-page .page-content::-webkit-scrollbar-track {
        background: rgba(255, 230, 240, 0.5);
        border-radius: 10px;
    }

    .final-page .page-content::-webkit-scrollbar-thumb {
        background: #ffb3d9;
        border-radius: 10px;
    }

    .final-page .page-content::-webkit-scrollbar-thumb:hover {
        background: #ff9fc9;
    }

    .final-page-inner {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        min-height: 100%;
    }

    .final-page h2 {
        font-family: 'Dancing Script', cursive;
        font-size: 32px;
        color: #d63384;
        margin-bottom: 20px;
        font-weight: 700;
        flex-shrink: 0;
    }

    .final-page .final-image {
        width: 200px;
        height: 150px;
        border-radius: 15px;
        border: 5px solid white;
        box-shadow: 0 10px 30px rgba(214, 51, 132, 0.25);
        overflow: hidden;
        margin-bottom: 20px;
        flex-shrink: 0;
    }

    .final-page .final-image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .final-page .final-message {
        background: rgba(255, 255, 255, 0.7);
        border-radius: 15px;
        padding: 20px;
        font-size: 14px;
        line-height: 1.8;
        color: #c42d78;
        box-shadow: 0 5px 15px rgba(214, 51, 132, 0.1);
        flex-shrink: 0;
        max-width: 100%;
    }

    .final-page .final-message em {
        font-style: italic;
        font-weight: 600;
        color: #d63384;
    }

    /* ============ DECORATIVE ELEMENTS ============ */
    .hearts-corner {
        position: absolute;
        bottom: 20px;
        right: 20px;
        font-size: 16px;
        color: #ff6fae;
        opacity: 0.6;
    }

    /* ============ NAVIGATION ============ */
    .controls {
        position: absolute;
        bottom: -75px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        padding: 0 10px;
    }

    button {
        background: linear-gradient(135deg, #ff9fc9, #ff6fae);
        border: none;
        padding: 14px 28px;
        border-radius: 30px;
        color: white;
        font-size: 16px;
        font-weight: 600;
        cursor: pointer;
        box-shadow: 0 8px 20px rgba(255, 77, 148, 0.3);
        transition: all 0.3s ease;
        font-family: 'Quicksand', sans-serif;
    }

    button:hover:not(:disabled) {
        transform: translateY(-3px);
        box-shadow: 0 12px 25px rgba(255, 77, 148, 0.4);
    }

    button:active {
        transform: translateY(-1px);
    }

    button:disabled {
        opacity: 0.4;
        cursor: not-allowed;
    }

    /* ============ PAGE FLIP ============ */
    .flipped {
        transform: rotateY(-180deg);
        z-index: 0 !important;
    }

    /* ============ RESPONSIVE ============ */
    @media (max-width: 480px) {
        .book {
            width: 340px;
            height: 500px;
        }

        .cover-page h1 {
            font-size: 34px;
        }

        .notebook-page h2,
        .final-page h2 {
            font-size: 24px;
        }

        .notes,
        .final-page .final-message {
            font-size: 13px;
        }

        .collage {
            height: 200px;
        }

        .p1 { width: 125px; height: 90px; left: 10px; }
        .p2 { width: 130px; height: 95px; right: 5px; }
        .p3 { width: 128px; height: 90px; left: 55px; }
    }
</style>
</head>

<body>

<div class="book">

    <!-- ==================== PAGE 1: COVER ==================== -->
    <div class="page cover-page" style="z-index: 5;">
        <div class="page-content">
            <h1>to my babi</h1>
            
            <div class="cover-image">
                <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" alt="Heart">
            </div>
            
            <div class="cover-quote">
                "Not everyone you meet is meant to pass by.<br>
                Some are only lessons, but some are meant to stay.<br>
                I'm not here to be fleeting—I'm here because<br>
                I choose to stay with you."<br><br>
                <em>— from bab.</em>
            </div>
            
            <div class="hearts-corner">❤ ❤ ❤</div>
        </div>
    </div>

    <!-- ==================== PAGE 2: PRECIOUS MOMENTS ==================== -->
    <div class="page notebook-page" style="z-index: 4;">
        <div class="page-content">
            <h2>Why I love you</h2>

            <div class="collage">
                <div class="photo p1">
                    <img src="https://www.dropbox.com/scl/fi/eqrigsk4gsu9hthpy5mgo/1769933903533.jpg?rlkey=9vwr875k7a0ka686jwgiywfs5&st=gek8mrc4&raw=1" alt="Memory 1">
                </div>
                <div class="photo p2">
                    <img src="https://www.dropbox.com/scl/fi/uqfwpgzarxy8o1yrs9jme/Snapchat-242672793.jpg?rlkey=r7d8lfwbzs50t6s9l1hovb28d&st=skmkpfbw&raw=1" alt="Memory 2">
                </div>
                <div class="photo p3">
                    <img src="https://www.dropbox.com/scl/fi/mnr0dwbdryfyhkpy8xwge/1769696489209.jpg?rlkey=fggw5tzp6qsid1sre6jqf2ize&st=yn6mbnsg&raw=1" alt="Memory 3">
                </div>
            </div>

            <div class="notes">
                To answer why I love you is hard, because I didn't fall for a single reason, I fell because of the series of moments, or events that happened throughout our relationship, the way na, life keeps bringing us back together, and all the little things in between that slowly made me fall deeper and deeper for you. Not because of some perfect ideal, or some version of "you" I imagined — but because of how every shared moments, every long message, every time we found each other again, built this feeling in me. Every time we found our way back to each other, every small moment we shared, every laughter, every quiet and serious conversation, I felt myself falling deeper. It's not just one day or one thing — it's the way na everything keeps connecting, the way each memory adds to the next, the way how life keeps letting me see you more fully.... All of it made me realize that I want to be this present, caring, and intentional with you — over and over, in every small way I can. It's the story I want to write together with you — imperfect, real, and completely ours — and it's what keeps me falling for you, again and again... <br><br>
                
                <em>— cherished memories close to my heart </em>
            </div>
            
            <div class="hearts-corner">❤ ❤ ❤</div>
        </div>
    </div>

    <!-- ==================== PAGE 3: RANDOM MOMENTS ==================== -->
    <div class="page notebook-page" style="z-index: 3;">
        <div class="page-content">
            <h2>Why I wont get tired</h2>

            <div class="collage">
                <div class="photo p1">
                    <img src="https://www.dropbox.com/scl/fi/4h27qd0ry14lf62qxfx3q/Snapchat-1090529785.jpg?rlkey=ud8ry3bep3cg0q7rf1ldenwel&st=ufof5rri&raw=1" alt="Random 1">
                </div>
                <div class="photo p2">
                    <img src="https://www.dropbox.com/scl/fi/im3vvyw5k7imid1v9crmd/Snapchat-1777448215.jpg?rlkey=metkhcllmg3phxrrfdxvsned3&st=834o1vti&raw=1" alt="Random 2">
                </div>
                <div class="photo p3">
                    <img src="https://www.dropbox.com/scl/fi/nk60c2rmizq8ykfyghzy0/IMG_20260129_183224_882.jpg?rlkey=qcoaqf6mj6ozbi8rolxice5oo&st=ny5dpol3&raw=1" alt="Random 3">
                </div>
            </div>

            <div class="notes">
                You're not draining me, babi — never have, never will. Being with you isn't something I'll ever get tired of, because it doesn't feel like work or effort at all... on contrary I love being with you, and when you open up to me, because it shows how much you trust me. And in every word, every laugh, every little moments we share just makes me want to be more closer to you, more patient, more present.and I know sometimes na you worry that you're too much, you're being unfair, or that I'll get tired of assuring you — but that never even crossed my mind not even once. Babi,  I'm here, and I'll keep being here, even when things feel heavy or scary, even when you pull back or need some space,I will be here, I will keep choosing you over and over again. I'll keep Loving you like this, caring for you like this. 
                <em> — being present with you...is not tiring. It's exactly the place where I want to be.</em>
                 </div>
            
            <div class="hearts-corner">❤ ❤ ❤</div>
        </div>
    </div>

    <!-- ==================== PAGE 4: THE PLACE ==================== -->
    <div class="page notebook-page" style="z-index: 2;">
        <div class="page-content">
            <h2>Why I'll miss you</h2>

            <div class="collage">
                <div class="photo p1">
                    <img src="https://www.dropbox.com/scl/fi/q492kdk5xsnek2bozqb75/1769932666056.jpg?rlkey=yf46ncsa86t2kxaa2s5vq1uvd&st=6976bkx1&raw=1" alt="Place 1">
                </div>
                <div class="photo p2">
                    <img src="https://www.dropbox.com/scl/fi/xoogzhojskm7qxbeni22j/IMG_20260129_015514_966.jpg?rlkey=00xkvawdzwlnnogkoen4d0snj&st=u4ih1uzd&raw=1" alt="Place 2">
                </div>
                <div class="photo p3">
                    <img src="https://www.dropbox.com/scl/fi/2acd4he5hztdu2vlhxg5a/IMG_20260129_194046_785.jpg?rlkey=jjxy4x8bxuyvvridfwj5kk72l&st=awgpcqdw&raw=1" alt="Place 3">
                </div>
            </div>

            <div class="notes">
                Babi, because ofc I would, why wouldn't I diba???? Pero seriously I'll miss you because being near you makes everything feel lighter and warmer like that saying na having butterflies in your stomach? Ambot unsa to.....that aside I will miss all the little things — your laugh, your scent, your voice, the feeling of holding you close, the way na we can just be together... Na anytime I could run to your place and make all sorts of excuses just to see you. And I'll miss running to your side when you're sad, or when you're hungry..sharing small moments, even just walking around together...here, there, everywhere.. in a short span of a few weeks... everything changed as if being with you — like that felt so natural,  like it's supposed to be, and knowing I won't have that for a while makes my chest feel heavy...ngaun palang na mimiss na kita..haha
I will really miss the comfort of having you close, the ease of talking to you in person, listening to your voice, and just being together. Every meeting we had, even those brief meetings na naghahatid lang ako ng food became special because you were there...because I could see you and that's why I'll miss you — not just because of what we do, but because of how it feels to have you near..
                <em> — a reminder that no matter how far we are to each other, you will always be in my heart. </em>
            </div>
            
            <div class="hearts-corner">❤ ❤ ❤</div>
        </div>
    </div>

    <!-- ==================== PAGE 5: FINAL MESSAGE ==================== -->
    <div class="page final-page" style="z-index: 1;">
        <div class="page-content">
            <div class="final-page-inner">
                <h2>Happy Valentines Babi</h2>
                
                <div class="final-image">
                    <img src="https://media1.giphy.com/media/v1.Y2lkPTZjMDliOTUydXowbGR2NDY4ZjB3MDBmY2Y3bHIyNHZidmQ0Y3VoeDlqcmpnNmtlNCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/12afltvVzJIesM/giphy.gif" alt="Love">
                </div>
                
                <div class="final-message">
                    I want you to know that I love you with my entire heart and my entire soul.
                    Every moment that I've thought of you, every moment we've shared, reminds me that you're the one I want. The only one that I've loved — not just in words, but with everything I'll ever be.
                    You are in every beat of my heart, in every breath I take and <em><i>I would choose you, again and again, in every universe, in every timeline, and in every story.</i></em>
                </div>
            </div>
        </div>
    </div>

    <!-- ==================== NAVIGATION ==================== -->
    <div class="controls">
        <button id="prevBtn" onclick="prevPage()" disabled>⬅ Back</button>
        <button id="nextBtn" onclick="nextPage()">Next ➡</button>
    </div>

</div>

<script>
    const pages = document.querySelectorAll('.page');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    let currentPage = 0;

    function updateButtons() {
        prevBtn.disabled = currentPage === 0;
        nextBtn.disabled = currentPage >= pages.length - 1;
    }

    function nextPage() {
        if (currentPage < pages.length - 1) {
            pages[currentPage].classList.add('flipped');
            currentPage++;
            updateButtons();
        }
    }

    function prevPage() {
        if (currentPage > 0) {
            currentPage--;
            pages[currentPage].classList.remove('flipped');
            updateButtons();
        }
    }

    updateButtons();
</script>

</body>
</html>

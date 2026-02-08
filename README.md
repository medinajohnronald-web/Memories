<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>to babi</title>

<style>
    body {
        background: #ffe6f0;
        font-family: "Comic Sans MS", cursive;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        overflow: hidden;
    }

    .book {
        width: 340px;
        height: 510px;
        perspective: 2000px;
        position: relative;
    }

    .page {
        width: 100%;
        height: 100%;
        background: #fff0f6;
        position: absolute;
        transform-origin: left;
        transition: transform 0.8s ease;
        border-radius: 14px;
        box-shadow: 0 12px 30px rgba(0,0,0,0.2);
        padding: 18px;
        box-sizing: border-box;
    }

    .page::after {
        content: "❤ ❤ ❤";
        position: absolute;
        bottom: 12px;
        right: 16px;
        font-size: 14px;
        color: #ff6fae;
    }

    .cover {
        background: linear-gradient(135deg, #ffb6d5, #ffe6f0);
        text-align: center;
    }

    h1, h2 {
        color: #ff4d94;
        text-align: center;
    }

    /* NOTEBOOK TEXT AREA (FLEXIBLE) */
    .notes {
        margin-top: 10px;
        min-height: 130px;          /* minimum space for short notes */
        max-height: 150px;          /* optional max, scroll if needed */
        background: repeating-linear-gradient(
            #fff,
            #fff 22px,
            #ffd6e8 23px
        );
        border-radius: 10px;
        padding: 10px;
        font-size: 14px;
        overflow-y: auto;
        color: #444;
    }

    /* COLLAGE */
    .collage {
        position: relative;
        margin-top: 12px;
        height: 200px;
    }

    .photo {
        position: absolute;
        background: #fff;
        border-radius: 12px;
        box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        overflow: hidden;
    }

    .photo img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .p1 { width: 120px; height: 90px; top: 0; left: 10px; transform: rotate(-6deg); }
    .p2 { width: 140px; height: 100px; top: 40px; right: 10px; transform: rotate(5deg); }
    .p3 { width: 130px; height: 90px; bottom: 0; left: 60px; transform: rotate(-2deg); }

    .controls {
        position: absolute;
        bottom: -60px;
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    button {
        background: #ff9fc9;
        border: none;
        padding: 10px 18px;
        border-radius: 20px;
        color: white;
        font-size: 14px;
        cursor: pointer;
        box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

    button:hover {
        background: #ff6fae;
    }

    .flipped {
        transform: rotateY(-180deg);
        z-index: 0;
    }

    /* GIF STYLING */
    .gif-container {
        margin-top: 15px;
        text-align: center;
    }

    .gif-container img {
        width: 75%;
        border-radius: 12px;
        box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        object-fit: cover;
    }
</style>
</head>

<body>

<div class="book">

    <!-- ================= PAGE 1 : COVER ================= -->
    <div class="page cover" style="z-index:5;">
        <h1>💖 to my babi 💖</h1>

        <div class="notes">
          <br>
          “Not everyone you meet is meant to pass by.
Some are only lessons, but some are meant to stay.
I’m not here to be fleeting—I’m here because I choose to stay with you.”<br><br>
          
                          —from bab.<br>
            — babi, Im not really good at this huhu
            
        </div>
      
    </div>

    <!-- ================= PAGE 2 ================= -->
    <div class="page" style="z-index:4;">
        <h2>Precious moments</h2>

        <div class="collage">
            <!-- img -->
            <div class="photo p1">
                <img src="https://www.dropbox.com/scl/fi/eqrigsk4gsu9hthpy5mgo/1769933903533.jpg?rlkey=9vwr875k7a0ka686jwgiywfs5&st=gek8mrc4&raw=1" alt="Memory 1">
            </div>

            <!-- img -->
            <div class="photo p2">
                <img src="https://www.dropbox.com/scl/fi/uqfwpgzarxy8o1yrs9jme/Snapchat-242672793.jpg?rlkey=r7d8lfwbzs50t6s9l1hovb28d&st=skmkpfbw&raw=1" alt="Memory 2">
            </div>

            <!-- img -->
            <div class="photo p3">
                <img src="https://www.dropbox.com/scl/fi/mnr0dwbdryfyhkpy8xwge/1769696489209.jpg?rlkey=fggw5tzp6qsid1sre6jqf2ize&st=yn6mbnsg&raw=1" alt="Memory 3">
            </div>
        </div>

        <div class="notes">
            <!-- txt -->
            these are moments that I wont forget.
            moments that I will treasure for the rest of my life. 
            the kind that will make me smile every time ma remember nako.
            the kind na would make my heart melt.<br><br>
            
            —precious moments that means a lot to me.
        </div>
    </div>

    <!-- ================= PAGE 3 ================= -->
    <div class="page" style="z-index:3;">
        <h2>Random moments I love</h2>

        <div class="collage">
            <!-- img -->
            <div class="photo p1">
                <img src="https://www.dropbox.com/scl/fi/4h27qd0ry14lf62qxfx3q/Snapchat-1090529785.jpg?rlkey=ud8ry3bep3cg0q7rf1ldenwel&st=ufof5rri&raw=1">
            </div>

            <!-- imt -->
            <div class="photo p2">
                <img src="https://www.dropbox.com/scl/fi/im3vvyw5k7imid1v9crmd/Snapchat-1777448215.jpg?rlkey=metkhcllmg3phxrrfdxvsned3&st=834o1vti&raw=1">
            </div>

            <!-- img -->
            <div class="photo p3">
                <img src="https://www.dropbox.com/scl/fi/nk60c2rmizq8ykfyghzy0/IMG_20260129_183224_882.jpg?rlkey=qcoaqf6mj6ozbi8rolxice5oo&st=ny5dpol3&raw=1">
            </div>
        </div>

        <div class="notes">
            <!-- txt -->
            Even in these random captured moments, I keep finding myself looking at you, without even realizing it.
            I really thought talaga na sa movie lang yan mag slowmo-slowmo na vison nayan eh.. pero it happens in reality din pala..
            
            
            
            
        </div>
    </div>

    <!-- ================= PAGE 4 ================= -->
    <div class="page" style="z-index:2;">
        <h2>The place where I want to be</h2>

        <div class="collage">
            <!-- img -->
            <div class="photo p1">
                <img src="https://www.dropbox.com/scl/fi/q492kdk5xsnek2bozqb75/1769932666056.jpg?rlkey=yf46ncsa86t2kxaa2s5vq1uvd&st=6976bkx1&raw=1">
            </div>

            <!-- img -->
            <div class="photo p2">
                <img src="https://www.dropbox.com/scl/fi/xoogzhojskm7qxbeni22j/IMG_20260129_015514_966.jpg?rlkey=00xkvawdzwlnnogkoen4d0snj&st=u4ih1uzd&raw=1">
            </div>

            <!-- img -->
            <div class="photo p3">
                <img src="https://www.dropbox.com/scl/fi/2acd4he5hztdu2vlhxg5a/IMG_20260129_194046_785.jpg?rlkey=jjxy4x8bxuyvvridfwj5kk72l&st=awgpcqdw&raw=1">
            </div>
        </div>

        <div class="notes">
            These are the moments when I could say na,<br> 
            “This is the place where I want to be… sa tabi mo.”
            This feeling, this moment, this closeness... is the place where I want to stay forever,<br>
            the destination I want to reach, and the home where I find my comfort.
        </div>
    </div>

    <!-- ================= PAGE 5 ================= -->
    <div class="page" style="z-index:1;">
        <h2>Happy Valentines Babi</h2>
      
<div class="gif-container">
            <img src="https://media1.giphy.com/media/v1.Y2lkPTZjMDliOTUydXowbGR2NDY4ZjB3MDBmY2Y3bHIyNHZidmQ0Y3VoeDlqcmpnNmtlNCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/12afltvVzJIesM/giphy.gif" alt="Cute GIF">
        </div>
      
        <div class="notes">
            <!-- TXT  -->
            A little reassurance for our future:

I appreciate you, I respect you, I trust you, and I love you more than time or distance. I'm completely yours, unconditionally, irrevocably, and every day that ends in you. I wouldn't have it any other way.

I love us, and I love being yours.
            — I love you with everything that I have. happy valentines babi..
        </div>
        
    </div>

    <div class="controls">
        <button onclick="prevPage()">⬅ Back</button>
        <button onclick="nextPage()">Next ➡</button>
    </div>

</div>

<script>
    const pages = document.querySelectorAll('.page');
    let current = 0;

    function nextPage() {
        if (current < pages.length) {
            pages[current].classList.add('flipped');
            current++;
        }
    }

    function prevPage() {
        if (current > 0) {
            current--;
            pages[current].classList.remove('flipped');
        }
    }
</script>

</body>
</html>

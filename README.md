<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>OKASHA — Gaming Universe</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:Arial,Helvetica,sans-serif;
    background:#050914;
    color:white;
}

nav{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:70px;
    background:rgba(5,9,20,.95);
    border-bottom:1px solid #1c2a45;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 7%;
    z-index:1000;
}

.logo{
    font-size:28px;
    font-weight:bold;
    color:#00eaff;
    text-shadow:0 0 15px #00eaff;
}

.nav-links{
    display:flex;
    gap:30px;
}

.nav-links a{
    color:#dce8ff;
    text-decoration:none;
    font-weight:bold;
}

.nav-links a:hover{
    color:#00eaff;
}

.hero{
    min-height:100vh;
    padding-top:70px;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    background:
        radial-gradient(circle at 50% 40%,rgba(0,150,255,.15),transparent 40%),
        #050914;
}

.hero h1{
    font-size:clamp(45px,8vw,90px);
    color:#00eaff;
    text-shadow:0 0 30px #00eaff;
}

.hero p{
    margin-top:20px;
    color:#9db0d0;
    font-size:20px;
}

.hero-btn{
    display:inline-block;
    margin-top:35px;
    padding:15px 35px;
    border:2px solid #00eaff;
    color:#00eaff;
    text-decoration:none;
    font-weight:bold;
    border-radius:8px;
    transition:.2s;
}

.hero-btn:hover{
    background:#00eaff;
    color:#050914;
    box-shadow:0 0 25px #00eaff;
}

.stats{
    display:flex;
    justify-content:center;
    gap:60px;
    margin-top:50px;
    flex-wrap:wrap;
}

.stat h2{
    color:#00eaff;
    font-size:35px;
}

.stat p{
    font-size:14px;
    margin-top:5px;
}

section{
    padding:100px 7%;
}

.section-title{
    text-align:center;
    color:#00eaff;
    font-size:40px;
    margin-bottom:50px;
}

.games-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:25px;
}

.game-card{
    background:#0b1324;
    border:1px solid #1c3557;
    border-radius:15px;
    padding:25px;
    text-align:center;
    transition:.3s;
}

.game-card:hover{
    transform:translateY(-8px);
    border-color:#00eaff;
    box-shadow:0 0 25px rgba(0,234,255,.2);
}

.game-icon{
    font-size:60px;
    margin-bottom:20px;
}

.game-card h3{
    color:#00eaff;
    margin-bottom:12px;
}

.game-card p{
    color:#9db0d0;
    line-height:1.6;
}

.play-btn{
    margin-top:20px;
    padding:12px 25px;
    border:none;
    border-radius:7px;
    background:#00eaff;
    color:#03101a;
    font-weight:bold;
    cursor:pointer;
}

.play-btn:hover{
    box-shadow:0 0 20px #00eaff;
}

/* GAME */

#game-section{
    background:#030711;
}

.game-wrapper{
    max-width:1000px;
    margin:auto;
}

.game-info{
    display:flex;
    justify-content:space-between;
    flex-wrap:wrap;
    gap:15px;
    margin-bottom:15px;
}

.game-stat{
    background:#0b1324;
    border:1px solid #1c3557;
    padding:12px 18px;
    border-radius:8px;
}

.game-stat span{
    color:#00eaff;
    font-weight:bold;
}

canvas{
    width:100%;
    max-width:1000px;
    height:auto;
    display:block;
    margin:auto;
    background:#02050c;
    border:2px solid #17365c;
    border-radius:10px;
    box-shadow:0 0 30px rgba(0,234,255,.15);
}

.controls{
    text-align:center;
    margin-top:15px;
    color:#8296b7;
}

.controls b{
    color:#00eaff;
}

/* UPGRADES */

.upgrade-section{
    background:#070d19;
}

.upgrade-info{
    text-align:center;
    color:#9db0d0;
    margin-bottom:40px;
}

.score-display{
    color:#00eaff;
    font-size:22px;
    font-weight:bold;
}

.upgrade-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:25px;
    max-width:1100px;
    margin:auto;
}

.upgrade-card{
    background:#0b1324;
    border:1px solid #1c3557;
    border-radius:15px;
    padding:25px;
    text-align:center;
    transition:.3s;
}

.upgrade-card:hover{
    border-color:#00eaff;
    transform:translateY(-5px);
}

.upgrade-icon{
    font-size:50px;
    margin-bottom:15px;
}

.upgrade-card h3{
    color:#00eaff;
    margin-bottom:10px;
}

.upgrade-card p{
    color:#9db0d0;
    min-height:45px;
}

.upgrade-level{
    margin:20px 0;
    color:#dbe7ff;
}

.upgrade-level span{
    color:#00eaff;
    font-weight:bold;
}

.upgrade-btn{
    width:100%;
    padding:13px;
    border:none;
    border-radius:8px;
    background:#00eaff;
    color:#03101a;
    font-weight:bold;
    cursor:pointer;
}

.upgrade-btn:hover{
    box-shadow:0 0 20px #00eaff;
}

.upgrade-btn:disabled{
    background:#34445e;
    color:#9aa8bd;
    cursor:not-allowed;
    box-shadow:none;
}

/* FOOTER */

footer{
    padding:40px;
    text-align:center;
    color:#60718f;
    border-top:1px solid #18263d;
}

/* GAME OVER */

.game-over{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.8);
    display:none;
    align-items:center;
    justify-content:center;
    z-index:2000;
}

.game-over-box{
    background:#091323;
    border:2px solid #00eaff;
    border-radius:15px;
    padding:40px;
    text-align:center;
    box-shadow:0 0 40px rgba(0,234,255,.3);
}

.game-over-box h2{
    color:#ff405d;
    font-size:40px;
    margin-bottom:15px;
}

.game-over-box p{
    color:#b7c7df;
    margin-bottom:25px;
}

.game-over-box button{
    padding:13px 25px;
    margin:5px;
    border:none;
    border-radius:7px;
    font-weight:bold;
    cursor:pointer;
}

.replay-btn{
    background:#00eaff;
}

.home-btn{
    background:#273752;
    color:white;
}
</style>
</head>

<body>

<nav>
    <div class="logo">OKASHA</div>

    <div class="nav-links">
        <a href="#home">Home</a>
        <a href="#games">Games</a>
        <a href="#upgrades">Upgrades</a>
        <a href="#join">Join Now</a>
    </div>
</nav>

<!-- HOME -->

<section class="hero" id="home">
    <div>
        <h1>ENTER THE UNIVERSE</h1>
        <p>Welcome to OKASHA Gaming Universe.</p>
        <p>Fight. Upgrade. Survive.</p>

        <a href="#games" class="hero-btn">EXPLORE GAMES</a>

        <div class="stats">
            <div class="stat">
                <h2>4</h2>
                <p>Games</p>
            </div>

            <div class="stat">
                <h2>∞</h2>
                <p>Adventures</p>
            </div>

            <div class="stat">
                <h2>1</h2>
                <p>Universe</p>
            </div>
        </div>
    </div>
</section>

<!-- GAMES -->

<section id="games">
    <h2 class="section-title">🎮 FEATURED GAMES</h2>

    <div class="games-grid">

        <div class="game-card">
            <div class="game-icon">🚀</div>
            <h3>Space Fighter</h3>
            <p>Destroy enemy fighters, collect special powers and survive the endless battle.</p>
            <button class="play-btn" onclick="startGame()">PLAY NOW</button>
        </div>

        <div class="game-card">
            <div class="game-icon">👹</div>
            <h3>Shadow Realm</h3>
            <p>Enter a mysterious world full of dangerous creatures.</p>
            <button class="play-btn">COMING SOON</button>
        </div>

        <div class="game-card">
            <div class="game-icon">🏝️</div>
            <h3>Lost Island</h3>
            <p>Explore an unknown island and discover its secrets.</p>
            <button class="play-btn">COMING SOON</button>
        </div>

        <div class="game-card">
            <div class="game-icon">🌃</div>
            <h3>Cyber City</h3>
            <p>Fight through a futuristic city controlled by machines.</p>
            <button class="play-btn">COMING SOON</button>
        </div>

    </div>
</section>

<!-- GAME -->

<section id="game-section">

    <h2 class="section-title">🚀 SPACE FIGHTER</h2>

    <div class="game-wrapper">

        <div class="game-info">

            <div class="game-stat">
                Score:
                <span id="score">0</span>
            </div>

            <div class="game-stat">
                Level:
                <span id="level">1</span>
            </div>

            <div class="game-stat">
                ❤️ Lives:
                <span id="lives">3</span>
            </div>

            <div class="game-stat">
                🚀 Missiles:
                <span id="missiles">1</span>
            </div>

            <div class="game-stat">
                Power:
                <span id="power">NONE</span>
            </div>

        </div>

        <canvas id="gameCanvas" width="1000" height="600"></canvas>

        <div class="controls">
            <b>A / D</b> or <b>← / →</b> = Move
            &nbsp;&nbsp;|&nbsp;&nbsp;
            <b>SPACE</b> = Shoot
        </div>

    </div>
</section>

<!-- UPGRADES -->

<section class="upgrade-section" id="upgrades">

    <h2 class="section-title">⚡ FIGHTER UPGRADES</h2>

    <div class="upgrade-info">
        Spend your score to improve your fighter.
        <br><br>

        <span class="score-display">
            Score:
            <span id="upgradeScore">0</span>
        </span>
    </div>

    <div class="upgrade-grid">

        <div class="upgrade-card">

            <div class="upgrade-icon">❤️</div>

            <h3>Health</h3>

            <p>Increase your starting hearts by 1.</p>

            <div class="upgrade-level">
                Level:
                <span id="healthLevel">0</span>
            </div>

            <button
                class="upgrade-btn"
                id="healthBtn"
                onclick="buyUpgrade('health')">
                Upgrade — 500
            </button>

        </div>


        <div class="upgrade-card">

            <div class="upgrade-icon">🚀</div>

            <h3>Missiles</h3>

            <p>Increase your starting missiles by 1.</p>

            <div class="upgrade-level">
                Level:
                <span id="missileLevel">0</span>
            </div>

            <button
                class="upgrade-btn"
                id="missileBtn"
                onclick="buyUpgrade('missile')">
                Upgrade — 500
            </button>

        </div>


        <div class="upgrade-card">

            <div class="upgrade-icon">🔥</div>

            <h3>Laser Beam</h3>

            <p>Increase laser duration by 0.75 seconds.</p>

            <div class="upgrade-level">
                Level:
                <span id="laserLevel">0</span>
            </div>

            <button
                class="upgrade-btn"
                id="laserBtn"
                onclick="buyUpgrade('laser')">
                Upgrade — 500
            </button>

        </div>


        <div class="upgrade-card">

            <div class="upgrade-icon">👥</div>

            <h3>Clone Fighter</h3>

            <p>Increase clone duration by 1 second.</p>

            <div class="upgrade-level">
                Level:
                <span id="cloneLevel">0</span>
            </div>

            <button
                class="upgrade-btn"
                id="cloneBtn"
                onclick="buyUpgrade('clone')">
                Upgrade — 500
            </button>

        </div>

    </div>
</section>

<section id="join">
    <h2 class="section-title">🌌 JOIN THE UNIVERSE</h2>

    <div style="text-align:center;color:#9db0d0;">
        More games and features are coming to OKASHA Gaming Universe.
    </div>
</section>

<footer>
    © 2026 OKASHA Gaming Universe
</footer>

<!-- GAME OVER -->

<div class="game-over" id="gameOver">

    <div class="game-over-box">

        <h2>GAME OVER</h2>

        <p>
            Final Score:
            <strong id="finalScore">0</strong>
        </p>

        <button class="replay-btn" onclick="startGame()">
            REPLAY
        </button>

        <button class="home-btn" onclick="goHome()">
            HOME
        </button>

    </div>

</div>


<script>

/* =========================================================
   UPGRADE SYSTEM
   ========================================================= */

let healthUpgrade = 0;
let missileUpgrade = 0;
let laserUpgrade = 0;
let cloneUpgrade = 0;

/*
   PRICE SYSTEM

   Level 0 = 500
   Level 1 = 750
   Level 2 = 1000
   Level 3 = 1250
   ...
*/

let upgradeBaseCost = 500;

function getUpgradeCost(level){
    return upgradeBaseCost + level * 250;
}


/* =========================================================
   GAME VARIABLES
   ========================================================= */

const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

let gameRunning = false;

let score = 0;
let level = 1;

let lives = 3;
let missileCount = 1;

let enemies = [];
let bullets = [];
let enemyBullets = [];

let powerUps = [];
let specialBubbles = [];

let particles = [];
let stars = [];

let keys = {};

let shootCooldown = 0;

let activePower = "none";
let powerTimer = 0;

let nukeFlash = 0;
let screenShake = 0;

let cloneDuration = 10;
let laserDuration = 5;

let clone = null;


/* =========================================================
   PLAYER
   ========================================================= */

const player = {

    x:canvas.width / 2 - 30,

    y:canvas.height - 100,

    width:60,

    height:75,

    speed:7
};


/* =========================================================
   STARS
   ========================================================= */

for(let i=0;i<120;i++){

    stars.push({

        x:Math.random()*canvas.width,

        y:Math.random()*canvas.height,

        size:Math.random()*2+1,

        speed:Math.random()*2+0.5
    });
}


/* =========================================================
   KEYBOARD
   ========================================================= */

document.addEventListener("keydown",function(e){

    keys[e.key.toLowerCase()] = true;

    if(e.code === "Space"){

        e.preventDefault();

        shoot();
    }

});


document.addEventListener("keyup",function(e){

    keys[e.key.toLowerCase()] = false;

});


/* =========================================================
   GAME START
   ========================================================= */

function startGame(){

    score = 0;

    level = 1;

    lives = 3 + healthUpgrade;

    missileCount = 1 + missileUpgrade;

    enemies = [];

    bullets = [];

    enemyBullets = [];

    powerUps = [];

    specialBubbles = [];

    particles = [];

    activePower = "none";

    powerTimer = 0;

    clone = null;

    nukeFlash = 0;

    screenShake = 0;

    player.x = canvas.width / 2 - player.width / 2;

    player.y = canvas.height - 100;

    gameRunning = true;

    document.getElementById("gameOver").style.display = "none";

    updateUI();

}


/* =========================================================
   GAME OVER
   ========================================================= */

function endGame(){

    gameRunning = false;

    document.getElementById("finalScore").textContent = score;

    document.getElementById("gameOver").style.display = "flex";

    updateUI();
}


function goHome(){

    document.getElementById("gameOver").style.display = "none";

    document.getElementById("home").scrollIntoView({
        behavior:"smooth"
    });
}


/* =========================================================
   UPDATE UI
   ========================================================= */

function updateUI(){

    document.getElementById("score").textContent = score;

    document.getElementById("level").textContent = level;

    document.getElementById("lives").textContent = lives;

    document.getElementById("missiles").textContent = missileCount;

    let powerText = activePower.toUpperCase();

    if(powerTimer > 0){

        powerText += " " + Math.ceil(powerTimer / 60) + "s";
    }

    document.getElementById("power").textContent = powerText;

    document.getElementById("upgradeScore").textContent = score;

    document.getElementById("healthLevel").textContent = healthUpgrade;

    document.getElementById("missileLevel").textContent = missileUpgrade;

    document.getElementById("laserLevel").textContent = laserUpgrade;

    document.getElementById("cloneLevel").textContent = cloneUpgrade;

    document.getElementById("healthBtn").textContent =
        "Upgrade — " + getUpgradeCost(healthUpgrade);

    document.getElementById("missileBtn").textContent =
        "Upgrade — " + getUpgradeCost(missileUpgrade);

    document.getElementById("laserBtn").textContent =
        "Upgrade — " + getUpgradeCost(laserUpgrade);

    document.getElementById("cloneBtn").textContent =
        "Upgrade — " + getUpgradeCost(cloneUpgrade);

}


/* =========================================================
   UPGRADE PURCHASE
   ========================================================= */

function buyUpgrade(type){

    let levelValue = 0;

    if(type === "health")
        levelValue = healthUpgrade;

    if(type === "missile")
        levelValue = missileUpgrade;

    if(type === "laser")
        levelValue = laserUpgrade;

    if(type === "clone")
        levelValue = cloneUpgrade;

    const cost = getUpgradeCost(levelValue);

    if(score < cost){

        alert(
            "Not enough score!\n\n" +
            "You need " + cost + " score."
        );

        return;
    }

    score -= cost;

    if(type === "health"){

        healthUpgrade++;

    }

    if(type === "missile"){

        missileUpgrade++;

    }

    if(type === "laser"){

        laserUpgrade++;

        laserDuration = 5 + laserUpgrade * 0.75;

    }

    if(type === "clone"){

        cloneUpgrade++;

        cloneDuration = 10 + cloneUpgrade;

    }

    updateUI();

}


/* =========================================================
   PLAYER MOVEMENT
   ========================================================= */

function updatePlayer(){

    if(keys["a"] || keys["arrowleft"]){

        player.x -= player.speed;
    }

    if(keys["d"] || keys["arrowright"]){

        player.x += player.speed;
    }

    if(player.x < 0){

        player.x = 0;
    }

    if(player.x + player.width > canvas.width){

        player.x = canvas.width - player.width;
    }

}


/* =========================================================
   PLAYER SHOOT
   ========================================================= */

function shoot(){

    if(!gameRunning)
        return;

    if(shootCooldown > 0)
        return;

    shootCooldown = 12;

    const spacing = 15;

    const total =
        (missileCount - 1) * spacing;


    for(let i=0;i<missileCount;i++){

        const offset =
            i * spacing - total / 2;

        bullets.push({

            x:
                player.x +
                player.width / 2 -
                3 +
                offset,

            y:player.y,

            width:6,

            height:25,

            speed:12,

            cloneShot:false
        });
    }


    /* CLONE SHOOTS SAME NUMBER OF MISSILES */

    if(clone){

        for(let i=0;i<missileCount;i++){

            const offset =
                i * spacing - total / 2;

            bullets.push({

                x:
                    clone.x +
                    clone.width / 2 -
                    3 +
                    offset,

                y:clone.y,

                width:6,

                height:25,

                speed:12,

                cloneShot:true
            });
        }
    }

}


/* =========================================================
   CREATE ENEMY
   ========================================================= */

function createEnemy(){

    const width = 65;

    const height = 70;

    enemies.push({

        x:
            Math.random() *
            (canvas.width - width),

        y:-height,

        width:width,

        height:height,

        speed:
            1.5 +
            level * 0.25 +
            Math.random() * 1.5,

        shootTimer:
            80 +
            Math.random() * 140,

        type:
            Math.floor(Math.random()*3)

    });

}


/* =========================================================
   ENEMY UPDATE
   ========================================================= */

function updateEnemies(){

    if(Math.random() < 0.018 + level * 0.001){

        createEnemy();
    }


    for(let i=enemies.length-1;i>=0;i--){

        const e = enemies[i];

        e.y += e.speed;

        e.shootTimer--;


        /* ENEMY SHOOTS EXACTLY ONE ROCKET */

        if(e.shootTimer <= 0){

            enemyBullets.push({

                x:
                    e.x +
                    e.width / 2 -
                    3,

                y:
                    e.y +
                    e.height,

                width:6,

                height:18,

                speed:5 + level * 0.2

            });

            e.shootTimer =
                100 +
                Math.random()*150;
        }


        /* CONTACT */

        if(collides(player,e)){

            lives--;

            screenShake = 12;

            createExplosion(
                e.x + e.width/2,
                e.y + e.height/2
            );

            enemies.splice(i,1);

            if(lives <= 0){

                endGame();
            }

            continue;
        }


        /* MISSING ENEMY DOES NOT COST LIFE */

        if(e.y > canvas.height + 100){

            enemies.splice(i,1);
        }

    }

}


/* =========================================================
   BULLET UPDATE
   ========================================================= */

function updateBullets(){

    for(let i=bullets.length-1;i>=0;i--){

        const b = bullets[i];

        b.y -= b.speed;


        if(b.y < -50){

            bullets.splice(i,1);

            continue;
        }


        for(let j=enemies.length-1;j>=0;j--){

            const e = enemies[j];

            if(collides(b,e)){

                score += 10;

                createExplosion(
                    e.x + e.width/2,
                    e.y + e.height/2
                );

                createPowerUp(e);

                createSpecialBubble(e);

                enemies.splice(j,1);

                bullets.splice(i,1);

                break;
            }

        }

    }

}


/* =========================================================
   ENEMY BULLETS
   ========================================================= */

function updateEnemyBullets(){

    for(let i=enemyBullets.length-1;i>=0;i--){

        const b = enemyBullets[i];

        b.y += b.speed;


        if(collides(b,player)){

            lives--;

            screenShake = 10;

            createExplosion(
                player.x + player.width/2,
                player.y + player.height/2
            );

            enemyBullets.splice(i,1);

            if(lives <= 0){

                endGame();
            }

            continue;
        }


        if(b.y > canvas.height){

            enemyBullets.splice(i,1);
        }

    }

}


/* =========================================================
   NORMAL POWER-UP
   10% SPAWN CHANCE
   50% LIFE / 50% MISSILE
   ========================================================= */

function createPowerUp(e){

    if(Math.random() > 0.10)
        return;

    const type =
        Math.random() < 0.5
        ? "life"
        : "missile";

    powerUps.push({

        x:
            e.x +
            e.width / 2 -
            15,

        y:
            e.y +
            e.height / 2 -
            15,

        width:30,

        height:30,

        speed:2,

        type:type,

        pulse:0

    });

}


/* =========================================================
   SPECIAL BUBBLE
   TOTAL 5%
   33.33% NUKE
   33.33% LASER
   33.33% CLONE
   ========================================================= */

function createSpecialBubble(e){

    if(Math.random() > 0.05)
        return;


    const roll = Math.random();

    let type;


    if(roll < 1/3){

        type = "nuke";

    }else if(roll < 2/3){

        type = "laser";

    }else{

        type = "clone";

    }


    specialBubbles.push({

        x:
            e.x +
            e.width / 2 -
            21,

        y:
            e.y +
            e.height / 2 -
            21,

        width:42,

        height:42,

        speed:2,

        type:type,

        rotation:0,

        pulse:0

    });

}


/* =========================================================
   POWER-UP UPDATE
   ========================================================= */

function updatePowerUps(){

    for(let i=powerUps.length-1;i>=0;i--){

        const p = powerUps[i];

        p.y += p.speed;

        p.pulse += 0.08;


        if(collides(p,player)){

            if(p.type === "life"){

                lives++;

            }

            if(p.type === "missile"){

                missileCount++;

            }

            createParticles(
                p.x + p.width/2,
                p.y + p.height/2,
                20
            );

            powerUps.splice(i,1);

            continue;
        }


        if(p.y > canvas.height){

            powerUps.splice(i,1);
        }

    }

}


/* =========================================================
   SPECIAL BUBBLE UPDATE
   ========================================================= */

function updateSpecialBubbles(){

    for(let i=specialBubbles.length-1;i>=0;i--){

        const p = specialBubbles[i];

        p.y += p.speed;

        p.rotation += 0.05;

        p.pulse += 0.08;


        if(collides(p,player)){

            activatePower(p.type);

            specialBubbles.splice(i,1);

            continue;
        }


        if(p.y > canvas.height){

            specialBubbles.splice(i,1);
        }

    }

}


/* =========================================================
   SPECIAL POWERS
   ========================================================= */

function activatePower(type){

    activePower = type;


    if(type === "nuke"){

        powerTimer = 5 * 60;

        nukeFlash = 40;

        screenShake = 25;


        /* DESTROY ALL CURRENT ENEMIES */

        for(const e of enemies){

            score += 10;

            createExplosion(
                e.x + e.width/2,
                e.y + e.height/2
            );
        }

        enemies = [];

    }


    if(type === "laser"){

        powerTimer =
            laserDuration * 60;

    }


    if(type === "clone"){

        createClone();

        powerTimer =
            cloneDuration * 60;

    }

}


/* =========================================================
   CLONE
   ========================================================= */

function createClone(){

    clone = {

        x:player.x - 105,

        y:player.y + 8,

        width:player.width,

        height:player.height

    };

}


function updateClone(){

    if(!clone)
        return;

    clone.x =
        player.x - 105;

    clone.y =
        player.y + 8;

}


function updateSpecialPower(){

    if(activePower === "none")
        return;


    powerTimer--;


    if(powerTimer <= 0){

        if(activePower === "clone"){

            clone = null;
        }

        activePower = "none";

        powerTimer = 0;
    }

}


/* =========================================================
   LASER
   ========================================================= */

function updateLaser(){

    if(activePower !== "laser")
        return;


    const laserX =
        player.x +
        player.width / 2;


    for(let i=enemies.length-1;i>=0;i--){

        const e = enemies[i];


        if(
            laserX > e.x &&
            laserX < e.x + e.width
        ){

            score += 10;

            createExplosion(
                e.x + e.width/2,
                e.y + e.height/2
            );

            createPowerUp(e);

            createSpecialBubble(e);

            enemies.splice(i,1);
        }

    }

}


/* =========================================================
   LEVEL SYSTEM
   ========================================================= */

function updateLevel(){

    const newLevel =
        Math.floor(score / 100) + 1;


    if(newLevel > level){

        level = newLevel;

        createParticles(
            canvas.width/2,
            canvas.height/2,
            40
        );
    }

}


/* =========================================================
   COLLISION
   ========================================================= */

function collides(a,b){

    return (

        a.x < b.x + b.width &&

        a.x + a.width > b.x &&

        a.y < b.y + b.height &&

        a.y + a.height > b.y

    );

}


/* =========================================================
   PARTICLES
   ========================================================= */

function createParticles(x,y,count){

    for(let i=0;i<count;i++){

        particles.push({

            x:x,

            y:y,

            vx:(Math.random()-.5)*6,

            vy:(Math.random()-.5)*6,

            life:30 + Math.random()*30,

            size:Math.random()*4+1

        });

    }

}


function createExplosion(x,y){

    createParticles(x,y,35);
}


function updateParticles(){

    for(let i=particles.length-1;i>=0;i--){

        const p = particles[i];

        p.x += p.vx;

        p.y += p.vy;

        p.life--;

        p.vx *= .98;

        p.vy *= .98;


        if(p.life <= 0){

            particles.splice(i,1);
        }

    }

}


/* =========================================================
   STARS
   ========================================================= */

function updateStars(){

    for(const s of stars){

        s.y += s.speed + level * .05;


        if(s.y > canvas.height){

            s.y = 0;

            s.x =
                Math.random() *
                canvas.width;
        }

    }

}


/* =========================================================
   DRAW BACKGROUND
   ========================================================= */

function drawBackground(){

    ctx.fillStyle="#02050c";

    ctx.fillRect(
        0,
        0,
        canvas.width,
        canvas.height
    );


    /* NEBULA */

    const gradient =
        ctx.createRadialGradient(
            canvas.width*.5,
            canvas.height*.5,
            10,
            canvas.width*.5,
            canvas.height*.5,
            500
        );

    gradient.addColorStop(
        0,
        "rgba(0,120,255,.12)"
    );

    gradient.addColorStop(
        1,
        "rgba(0,0,0,0)"
    );

    ctx.fillStyle=gradient;

    ctx.fillRect(
        0,
        0,
        canvas.width,
        canvas.height
    );


    /* STARS */

    for(const s of stars){

        ctx.fillStyle="rgba(180,230,255,.8)";

        ctx.fillRect(
            s.x,
            s.y,
            s.size,
            s.size
        );
    }

}


/* =========================================================
   DRAW PLAYER JET
   ========================================================= */

function drawPlayerJet(x,y){

    ctx.save();

    ctx.translate(x,y);


    /* ENGINE GLOW */

    const glow =
        ctx.createRadialGradient(
            30,
            72,
            2,
            30,
            72,
            35
        );

    glow.addColorStop(
        0,
        "rgba(0,234,255,.9)"
    );

    glow.addColorStop(
        1,
        "rgba(0,234,255,0)"
    );

    ctx.fillStyle=glow;

    ctx.beginPath();

    ctx.arc(30,72,35,0,Math.PI*2);

    ctx.fill();


    /* MAIN BODY */

    ctx.beginPath();

    ctx.moveTo(30,0);

    ctx.lineTo(42,23);

    ctx.lineTo(58,47);

    ctx.lineTo(45,49);

    ctx.lineTo(39,72);

    ctx.lineTo(30,65);

    ctx.lineTo(21,72);

    ctx.lineTo(15,49);

    ctx.lineTo(2,47);

    ctx.lineTo(18,23);

    ctx.closePath();

    ctx.fillStyle="#a9b5c4";

    ctx.fill();

    ctx.strokeStyle="#00eaff";

    ctx.lineWidth=1.5;

    ctx.stroke();


    /* WINGS */

    ctx.beginPath();

    ctx.moveTo(18,25);

    ctx.lineTo(0,48);

    ctx.lineTo(20,43);

    ctx.closePath();

    ctx.fillStyle="#647384";

    ctx.fill();


    ctx.beginPath();

    ctx.moveTo(42,25);

    ctx.lineTo(60,48);

    ctx.lineTo(40,43);

    ctx.closePath();

    ctx.fill();


    /* COCKPIT */

    ctx.beginPath();

    ctx.moveTo(30,8);

    ctx.lineTo(38,28);

    ctx.lineTo(30,34);

    ctx.lineTo(22,28);

    ctx.closePath();

    ctx.fillStyle="#122b42";

    ctx.fill();

    ctx.strokeStyle="#4fefff";

    ctx.stroke();


    /* COCKPIT REFLECTION */

    ctx.beginPath();

    ctx.moveTo(26,13);

    ctx.lineTo(33,17);

    ctx.lineTo(35,22);

    ctx.lineTo(28,19);

    ctx.closePath();

    ctx.fillStyle="rgba(160,245,255,.8)";

    ctx.fill();


    /* CENTER LINE */

    ctx.beginPath();

    ctx.moveTo(30,34);

    ctx.lineTo(30,65);

    ctx.strokeStyle="#405469";

    ctx.stroke();


    ctx.restore();

}


/* =========================================================
   DRAW CLONE
   ========================================================= */

function drawCloneJet(x,y){

    ctx.save();

    ctx.translate(x,y);

    ctx.globalAlpha=.8;


    ctx.beginPath();

    ctx.moveTo(30,0);

    ctx.lineTo(42,23);

    ctx.lineTo(58,47);

    ctx.lineTo(43,45);

    ctx.lineTo(37,70);

    ctx.lineTo(30,63);

    ctx.lineTo(23,70);

    ctx.lineTo(17,45);

    ctx.lineTo(2,47);

    ctx.lineTo(18,23);

    ctx.closePath();

    ctx.fillStyle="#8d52ff";

    ctx.fill();

    ctx.strokeStyle="#d7aaff";

    ctx.lineWidth=2;

    ctx.stroke();


    ctx.beginPath();

    ctx.moveTo(30,8);

    ctx.lineTo(38,28);

    ctx.lineTo(30,34);

    ctx.lineTo(22,28);

    ctx.closePath();

    ctx.fillStyle="#25113d";

    ctx.fill();


    ctx.restore();

}


/* =========================================================
   DRAW ENEMY
   ========================================================= */

function drawEnemy(e){

    ctx.save();

    ctx.translate(e.x,e.y);


    /* GLOW */

    ctx.shadowBlur=15;

    ctx.shadowColor="#ff2348";


    /* BODY */

    ctx.beginPath();

    ctx.moveTo(32,70);

    ctx.lineTo(42,47);

    ctx.lineTo(62,28);

    ctx.lineTo(45,31);

    ctx.lineTo(38,5);

    ctx.lineTo(32,0);

    ctx.lineTo(26,5);

    ctx.lineTo(19,31);

    ctx.lineTo(2,28);

    ctx.lineTo(22,47);

    ctx.closePath();

    ctx.fillStyle="#64152a";

    ctx.fill();

    ctx.strokeStyle="#ff3658";

    ctx.lineWidth=2;

    ctx.stroke();


    /* WINGS */

    ctx.beginPath();

    ctx.moveTo(22,32);

    ctx.lineTo(0,53);

    ctx.lineTo(21,48);

    ctx.closePath();

    ctx.fillStyle="#3d101d";

    ctx.fill();


    ctx.beginPath();

    ctx.moveTo(42,32);

    ctx.lineTo(64,53);

    ctx.lineTo(43,48);

    ctx.closePath();

    ctx.fill();


    /* COCKPIT */

    ctx.beginPath();

    ctx.moveTo(32,10);

    ctx.lineTo(39,28);

    ctx.lineTo(32,33);

    ctx.lineTo(25,28);

    ctx.closePath();

    ctx.fillStyle="#160910";

    ctx.fill();

    ctx.strokeStyle="#ff6078";

    ctx.stroke();


    ctx.restore();

}


/* =========================================================
   DRAW BULLETS
   ========================================================= */

function drawBullets(){

    for(const b of bullets){

        ctx.save();

        ctx.shadowBlur=15;

        ctx.shadowColor="#00eaff";

        ctx.fillStyle="#00eaff";

        ctx.fillRect(
            b.x,
            b.y,
            b.width,
            b.height
        );

        ctx.restore();
    }


    for(const b of enemyBullets){

        ctx.save();

        ctx.shadowBlur=12;

        ctx.shadowColor="#ff304f";

        ctx.fillStyle="#ff304f";

        ctx.fillRect(
            b.x,
            b.y,
            b.width,
            b.height
        );

        ctx.restore();
    }

}


/* =========================================================
   DRAW POWERUPS
   ========================================================= */

function drawPowerUps(){

    for(const p of powerUps){

        const pulse =
            Math.sin(p.pulse)*3;


        ctx.save();

        ctx.translate(
            p.x + p.width/2,
            p.y + p.height/2
        );

        ctx.rotate(p.pulse);


        ctx.shadowBlur=20;

        ctx.shadowColor=
            p.type === "life"
            ? "#ff4d72"
            : "#00eaff";


        ctx.fillStyle=
            p.type === "life"
            ? "#ff4d72"
            : "#00eaff";


        ctx.beginPath();

        ctx.arc(
            0,
            0,
            12+pulse,
            0,
            Math.PI*2
        );

        ctx.fill();


        ctx.fillStyle="#ffffff";

        ctx.font="bold 15px Arial";

        ctx.textAlign="center";

        ctx.textBaseline="middle";

        ctx.fillText(
            p.type === "life" ? "♥" : "🚀",
            0,
            0
        );


        ctx.restore();
    }

}


/* =========================================================
   DRAW SPECIAL BUBBLES
   ========================================================= */

function drawSpecialBubbles(){

    for(const p of specialBubbles){

        const pulse =
            Math.sin(p.pulse)*5;


        ctx.save();

        ctx.translate(
            p.x + p.width/2,
            p.y + p.height/2
        );

        ctx.rotate(p.rotation);


        let glowColor =
            p.type === "nuke"
            ? "#ff304f"
            : p.type === "laser"
            ? "#ff38ff"
            : "#9d5cff";


        ctx.shadowBlur=25;

        ctx.shadowColor=glowColor;

        ctx.strokeStyle=glowColor;

        ctx.lineWidth=3;

        ctx.beginPath();

        ctx.arc(
            0,
            0,
            17+pulse,
            0,
            Math.PI*2
        );

        ctx.stroke();


        ctx.fillStyle="rgba(255,255,255,.15)";

        ctx.beginPath();

        ctx.arc(
            0,
            0,
            15+pulse,
            0,
            Math.PI*2
        );

        ctx.fill();


        ctx.fillStyle="#ffffff";

        ctx.font="bold 18px Arial";

        ctx.textAlign="center";

        ctx.textBaseline="middle";


        if(p.type === "nuke")
            ctx.fillText("☢",0,0);

        if(p.type === "laser")
            ctx.fillText("⚡",0,0);

        if(p.type === "clone")
            ctx.fillText("👥",0,0);


        ctx.restore();

    }

}


/* =========================================================
   DRAW LASER
   ========================================================= */

function drawLaser(){

    if(activePower !== "laser")
        return;


    const x =
        player.x +
        player.width / 2;


    ctx.save();

    ctx.shadowBlur=30;

    ctx.shadowColor="#ff35ff";

    ctx.strokeStyle="#ff55ff";

    ctx.lineWidth=12;

    ctx.beginPath();

    ctx.moveTo(x,player.y);

    ctx.lineTo(x,0);

    ctx.stroke();


    ctx.strokeStyle="#ffffff";

    ctx.lineWidth=3;

    ctx.beginPath();

    ctx.moveTo(x,player.y);

    ctx.lineTo(x,0);

    ctx.stroke();

    ctx.restore();

}


/* =========================================================
   DRAW NUKE EFFECT
   ========================================================= */

function drawNuke(){

    if(nukeFlash <= 0)
        return;


    ctx.save();

    const radius =
        (40 - nukeFlash) * 25;


    ctx.globalAlpha =
        nukeFlash / 40;


    ctx.strokeStyle="#ff304f";

    ctx.lineWidth=10;

    ctx.shadowBlur=30;

    ctx.shadowColor="#ff304f";


    ctx.beginPath();

    ctx.arc(
        canvas.width/2,
        canvas.height/2,
        radius,
        0,
        Math.PI*2
    );

    ctx.stroke();


    ctx.restore();

}


/* =========================================================
   DRAW PARTICLES
   ========================================================= */

function drawParticles(){

    for(const p of particles){

        ctx.globalAlpha =
            Math.max(0,p.life/60);

        ctx.fillStyle="#00eaff";

        ctx.fillRect(
            p.x,
            p.y,
            p.size,
            p.size
        );
    }

    ctx.globalAlpha=1;

}


/* =========================================================
   MAIN DRAW
   ========================================================= */

function draw(){

    ctx.save();


    if(screenShake > 0){

        ctx.translate(
            (Math.random()-.5)*screenShake,
            (Math.random()-.5)*screenShake
        );

        screenShake *= .85;

        if(screenShake < .5)
            screenShake=0;
    }


    drawBackground();

    drawPlayerJet(
        player.x,
        player.y
    );


    if(clone){

        drawCloneJet(
            clone.x,
            clone.y
        );
    }


    for(const e of enemies){

        drawEnemy(e);
    }


    drawBullets();

    drawPowerUps();

    drawSpecialBubbles();

    drawLaser();

    drawParticles();

    drawNuke();


    if(nukeFlash > 0){

        nukeFlash--;
    }


    ctx.restore();

}


/* =========================================================
   GAME LOOP
   ========================================================= */

function gameLoop(){

    updateStars();


    if(gameRunning){

        updatePlayer();

        updateEnemies();

        updateBullets();

        updateEnemyBullets();

        updatePowerUps();

        updateSpecialBubbles();

        updateSpecialPower();

        updateClone();

        updateLaser();

        updateParticles();

        updateLevel();

        if(shootCooldown > 0){

            shootCooldown--;
        }

        updateUI();
    }


    draw();

    requestAnimationFrame(gameLoop);
}


/* =========================================================
   INITIAL UI
   ========================================================= */

updateUI();

gameLoop();

</script>

</body>
</html>

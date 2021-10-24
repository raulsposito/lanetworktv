<template>
<div>
    <div class="header">
	<!-- 	<h1>Spinny Flipz</h1> -->
    </div>
    <section class="slider-section">
        <div class="wheel">
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-1.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-2.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-3.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-4.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-5.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-6.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-7.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-1.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-2.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-3.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-4.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-5.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-6.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-7.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-1.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-2.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-3.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-4.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-5.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-6.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-7.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-1.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-2.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-3.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-4.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-5.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-6.jpg" />
            </div>
            <div class="wheel__card">
                <img src="https://assets.codepen.io/756881/amys-7.jpg" />
            </div>
        </div>
    </section>

    <div class="scroll-down">Scroll down<div class="arrow"></div>
    </div>
</div>
</template>

<script>
import gsap from 'gsap'
import ScrollTrigger from "gsap/ScrollTrigger"

export default {

    mounted() {
        console.clear();

        gsap.registerPlugin(ScrollTrigger)

        let wheel = document.querySelector(".wheel");
        let images = gsap.utils.toArray(".wheel__card");

        gsap.to(".arrow", { y: 5, ease: "power1.inOut", repeat: -1, yoyo: true });

        function setup() {
            let radius = wheel.offsetWidth / 2;
            let center = wheel.offsetWidth / 2;
            let total = images.length;
            let slice = (2 * Math.PI) / total;

            images.forEach((item, i) => {
                let angle = i * slice;

                let x = center + radius * Math.sin(angle);
                let y = center - radius * Math.cos(angle);

                gsap.set(item, {
                    rotation: angle + "_rad",
                    xPercent: -50,
                    yPercent: -50,
                    x: x,
                    y: y
                });
            });
        }

        setup();

        window.addEventListener("resize", setup);

        gsap.to(".wheel", {
            rotate: () => -360,
            ease: "none",
            duration: images.length,
            scrollTrigger: {
                start: 0,
                end: "max",
                scrub: 1,
                snap: 1 / images.length,
                invalidateOnRefresh: true
            }
        });

        let cards = gsap.utils.toArray(".wheel__card");
        let header = document.querySelector(".header");
        let body = document.querySelector(".header");

        let isFullScreen = false;

        // keep track of last clicked card so we can put it back
        let lastClickedCard;

        cards.forEach((card) => {
            card.addEventListener("click", (e) => {
                if (lastClickedCard) {
                    putBack(e);
                }
                flip(e);
            });
        });

        header.addEventListener("click", (e) => {
            if (!lastClickedCard) return;
            putBack(e);
        });

        function putBack(e) {
            let image = header.querySelector("img");

            // let state = Flip.getState(image);

            lastClickedCard.appendChild(image);

            // Flip.from(state, {
            //     duration: 0.6,
            //     ease: "sine.out",
            //     absolute: true
            // });

            lastClickedCard = null;
        }

        function flip(e) {
            let image = e.target.querySelector("img");

            // let state = Flip.getState(image);

            header.appendChild(image);

            // Flip.from(state, {
            //     duration: 0.6,
            //     ease: "sine.out",
            //     absolute: true
            // });

            lastClickedCard = e.target;
        }

    }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

@font-face {
	font-family: "longline";
	src: url("https://assets.codepen.io/756881/Longline+Quart+FREE.ttf")
		format("truetype");
	font-weight: normal;
	font-style: normal;
}

body {
	padding: 0;
	margin: 0;
	height: 600vh;
	width: 100vw;
	font-family: "Nunito", sans-serif;
	background-color: #333334;
	color: white;
}

h1 {
	font-family: "longline";
}

.slider-section {
	height: 22vh;
	bottom: 0;
	position: fixed;
	width: 100%;
}

h1 {
	font-size: 10vw;
}

.wheel {
	position: absolute;
	top: 0;
	display: flex;
	align-items: center;
	justify-content: center;
	width: 300vw;
	height: 300vw;
	max-width: 2000px;
	max-height: 2000px;
	left: 50%;
	transform: translateX(-50%);
}

.wheel__card {
	position: absolute;
	top: 0;
	left: 0;
	width: 6%;
	max-width: 200px;
	aspect-ratio: 1 / 1;
	cursor: pointer;
}

img {
	width: 100%;
	pointer-events: none;
	z-index: 999;
	cursor: pointer;
}

.header {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 60vh;
	display: flex;
	align-items: center;
	justify-content: center;
	cursor: pointer;
}

.header img {
	width: 40vw;
	height: 40vw;
	max-height: 350px;
	max-width: 350px;
}

/* SCROLL DOWN */
.scroll-down {
	position: fixed;
	bottom: 20px;
	left: 50%;
	transform: translate(-50%, 0);
	color: white;
	font-weight: 400;
	text-transform: uppercase;
	font-size: 14px;
	overflow: visible;
}

.scroll-down .arrow {
	position: relative;
	top: 0px;
	margin: 0 auto;
	width: 15px;
	height: 15px;
	filter: invert(1);
	background-image: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj4KPHBhdGggZmlsbD0iYmxhY2siIGQ9Ik00ODMuMiwxOTIuMmMtMjAuNS0yMC41LTUzLjUtMjAuOC03My43LTAuNkwyNTcsMzQ0LjFMMTA0LjUsMTkxLjZjLTIwLjItMjAuMi01My4yLTE5LjktNzMuNywwLjYKCWMtMjAuNSwyMC41LTIwLjgsNTMuNS0wLjYsNzMuN2wxOTAsMTkwYzEwLjEsMTAuMSwyMy40LDE1LjEsMzYuOCwxNWMxMy4zLDAuMSwyNi43LTQuOSwzNi44LTE1bDE5MC0xOTAKCUM1MDMuOSwyNDUuNyw1MDMuNywyMTIuNyw0ODMuMiwxOTIuMnoiLz4KPC9zdmc+);
	background-size: contain;
}
</style>
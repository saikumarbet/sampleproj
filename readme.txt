index.html

    <main>
        <div><img src="https://assets.codepen.io/86170/img-1.webp" alt="Orango Jones"></div>
        <button id="dialog-open">Keep me informed</button>
    </main>

    <dialog id="dialog">
        <h2>Keep me informed</h2>
        <form action="" method="" name="">
            <label for="notify-email" data-visibility="hidden">Email address</label>
            <input type="email" id="dialog-email" name="dialog-email" placeholder="you @ your domain" required="">
            <button type="submit">Submit</button>
        </form>
        <button id="dialog-close">&#x2716</button>
    </dialog>




style.css



@import url('https://fonts.googleapis.com/css2?family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap');

:root {
--spacing-r: 1.5rem;
--spacing-l: 3rem; }

[data-visibility="hidden"] {
position: absolute;
margin: -1px;
padding: 0;
height: 1px;
width: 1px;
overflow: hidden;
border: 0;
-webkit-clip-path: polygon(0px 0px, 0px 0px, 0px 0px);
clip-path: polygon(0px 0px, 0px 0px, 0px 0px);
white-space: nowrap; }

html {
background-color: #a5b260;
-webkit-text-size-adjust: 100%;
overflow-x: hidden;
scroll-behavior: smooth; }

@media screen and (prefers-reduced-motion: reduce) {
html {
scroll-behavior: auto;
animation-duration: 1ms !important;
animation-iteration-count: 1 !important;
transition-duration: 1ms !important; }
}

body {
margin: 0 auto;
padding-block-end: var(--spacing-l);
padding-inline: var(--spacing-l);
max-inline-size: 105rem;
background-color: #a5b260;
color: #fff;
font-family: "Sour Gummy", sans-serif;
font-optical-sizing: auto;
font-weight: 400;
font-style: normal;
font-size: 1em;
font-variation-settings: "wdth" 100; }

h2 {
margin: 0 0 1rem;
font-size: 48px;
line-height: .9;
text-transform: uppercase; }

main {
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
block-size: 100vh; }

[src*="img-1"] {
display: block;
margin-block-end: var(--spacing-r);
margin-inline: auto;
inline-size: 320px; }

form {
margin: 0;
padding: 0; }

[type="email"] {
-webkit-appearance: none;
appearance: none;
display: block;
margin: 0 auto 1.5rem;
padding: 15px;
background-color: #f0e6db;
border-width: 0;
border-radius: 5px;
box-shadow: none;
font-family: inherit;
font-size: 16px;
text-align: center;
color: #251712;
transition: all .5s ease;
caret-color: #a5b260; }

[type="email"]:focus {
outline: 0;
accent-color: #a5b260; }

input[type]::placeholder {
font-family: inherit;
font-size: 16px;
color: #251712; }

input:focus::-webkit-input-placeholder {
transition: opacity .5s .25s ease !important;
opacity: 0; }

input:focus::placeholder {
transition: opacity .5s .25s ease !important;
opacity: 0; }

button {
inline-size: fit-content;
margin-inline: auto;
padding-block: 15px;
padding-inline: var(--spacing-r);
background-color: #251712;
border: none;
box-shadow: none;
border-radius: 10px;
outline: none;
font-family: inherit;
font-size: 21px;
font-weight: 500;
line-height: 1;
text-align: center;
text-transform: uppercase;
color: #fff;
cursor: pointer;
touch-action: manipulation;
-webkit-user-select: none;
user-select: none; }

dialog button {
color: #8a7e76; }

dialog:has(input:valid) button {
background-color: #7e8943;
color: #fff;
animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both; }

dialog {
overflow: hidden;
padding: 120px 60px 0;
width: 420px;
height: 480px;
background-color: transparent;
background-image: url("https://assets.codepen.io/86170/dialog.svg");
background-repeat: no-repeat;
background-size: contain;
border: none;
box-sizing: border-box;
color: #fff;
text-align: center;
opacity: 0;
scale: .5;
transition: opacity .3s ease, scale .3s ease;
pointer-events: none; }

dialog[open] {
pointer-events: auto; }

dialog.show {
opacity: 1;
scale: 1; }

dialog:has(input:valid) {
background-image: url("https://assets.codepen.io/86170/dialog-valid.svg");
animation: rubberBand 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both; }

dialog #dialog-close {
position: absolute;
top: 10px;
right: 10px;
background-color: transparent;
border-width: 0;
outline: 0;
font-size: 32px;
color: #fff; }

dialog:has(input:valid) #dialog-close {
display: none; }

dialog::backdrop {
opacity: 0;
background-image: url("https://assets.codepen.io/86170/backdrop.svg");
background-size: cover;
transition: opacity .3s ease; }

dialog:has(input:valid)::backdrop {
background-image: url("https://assets.codepen.io/86170/backdrop-valid.svg"); }

dialog[open]::backdrop {
opacity: .9; }

@keyframes heartBeat {
0% { scale: 1; }
14% { scale: 1.1; }
28% { scale: 1; }
42% { scale: 1.1; }
70% { scale: 1; }
}

@keyframes rubberBand {
from { transform: scale3d(1, 1, 1); }
30% { transform: scale3d(1.25, 0.75, 1); }
40% { transform: scale3d(0.75, 1.25, 1); }
50% { transform: scale3d(1.15, 0.85, 1); }
65% { transform: scale3d(0.95, 1.05, 1); }
75% { transform: scale3d(1.05, 0.95, 1); }
to { transform: scale3d(1, 1, 1); }
}

@keyframes shake {
10%, 90% { transform: translate3d(-1px, 0, 0); }
20%, 80% { transform: translate3d(2px, 0, 0); }
30%, 50%, 70% { transform: translate3d(-5px, 0, 0); }
40%, 60% { transform: translate3d(5px, 0, 0); }
}










script.js


window.dispatchEvent(new Event("scroll"));

const dialog = document.getElementById("dialog");
const openButton = document.getElementById("dialog-open");
const closeButton = document.getElementById("dialog-close");
const form = dialog.querySelector("form");

// OPEN with animation
openButton.addEventListener("click", () => {
  dialog.showModal();
  requestAnimationFrame(() => {
    dialog.classList.add("show");
  });
});

// CLOSE with animation
function closeDialog() {
  dialog.classList.remove("show");
  dialog.addEventListener(
    "transitionend",
    () => {
      dialog.close();
    },
    { once: true }
  );
}

closeButton.addEventListener("click", closeDialog);

form.addEventListener("submit", (event) => {
  event.preventDefault();
  closeDialog();
});

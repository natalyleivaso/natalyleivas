const track = document.querySelector(".carousel-track");
const slides = document.querySelectorAll(".carousel img");

const next = document.querySelector(".next");
const prev = document.querySelector(".prev");

let index = 0;

function updateCarousel(){
    track.style.transform =
    `translateX(-${index * 100}%)`;
}

next.addEventListener("click", () => {

    index++;

    if(index >= slides.length){
        index = 0;
    }

    updateCarousel();

});

prev.addEventListener("click", () => {

    index--;

    if(index < 0){
        index = slides.length - 1;
    }

    updateCarousel();

});

setInterval(() => {

    index++;

    if(index >= slides.length){
        index = 0;
    }

    updateCarousel();

}, 5000);
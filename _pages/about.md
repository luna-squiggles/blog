---
layout: page
title: About
---
  
## Hiya, my name is Luna Mustfa

I work in an MP's office where I build digital transparency tools, work on interesting interventions, and complain about how hot our office 

My interests are in developing responsive & functional web applications, writing about paintings, visiting coffee shops, and talking about housing policy.

There's lots of other things I enjoy~ maybe you like <a href='.'><span id="word"></span></a><span id="emoji"></span> too?

My website -> [lunamustfa.com](https://lunamustfa.com/)

<script>
// Cache DOM elements and constants
const INTERESTS = [
    { text: 'writing good code', emoji: ' 👾' },
    { text: 'knitting', emoji: ' 🧶' },
    { text: 'producing music', emoji: ' 🎼' },
    { text: 'photography', emoji: ' 📷' },
    { text: 'writing', emoji: ' 🖊️' },
    { text: 'figure skating', emoji: ' ⛸️' },
    { text: 'classical guitar', emoji: ' 🎵' },
    { text: 'sailing', emoji: ' ⛵' }
];

// Cache DOM elements
const wordElement = document.getElementById('word');
const emojiElement = document.getElementById('emoji');
const wordLink = document.querySelector('a[href="."]');

// Get or initialise indices from localStorage
let currentIndex = parseInt(localStorage.getItem('interestIndex') || 0);

// Update display with current interest
const updateDisplay = () => {
    const { text, emoji } = INTERESTS[currentIndex];
    wordElement.textContent = text;
    emojiElement.textContent = emoji;
    localStorage.setItem('interestIndex', currentIndex);
};

// Cycle to next interest
const cycleInterests = (event) => {
    if (event) event.preventDefault();
    currentIndex = (currentIndex + 1) % INTERESTS.length;
    updateDisplay();
};

// Initialise on DOM content loaded
document.addEventListener('DOMContentLoaded', () => {
    // Move to next interest on load
    currentIndex = (currentIndex + 1) % INTERESTS.length;
    
    // Add click handlers if links exist
    if (wordLink) {
        wordLink.addEventListener('click', cycleInterests);
    }
    
    // Initial display
    updateDisplay();
});
</script>

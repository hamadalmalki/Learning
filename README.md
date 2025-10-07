<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Learn Alphabet for Kids</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(135deg, #f9c5d1, #fceabb);
      color: #333;
      text-align: center;
      padding: 20px;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      color: #ff6f61;
      text-shadow: 1px 1px 2px #ffb3ab;
    }
    .letters-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      max-width: 700px;
      margin: 0 auto 30px;
    }
    .letter-btn {
      background: #ffccf9;
      border: 3px solid #ff6f61;
      border-radius: 10px;
      color: #ff3d6e;
      font-weight: bold;
      font-size: 1.8rem;
      width: 60px;
      height: 60px;
      margin: 8px;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(255, 111, 97, 0.5);
      transition: background 0.3s ease, transform 0.2s ease;
    }
    .letter-btn:hover {
      background: #ff6f61;
      color: white;
      transform: scale(1.1);
    }
    .display-area {
      background: #fff3f0;
      border: 3px solid #ff6f61;
      border-radius: 15px;
      max-width: 400px;
      margin: 0 auto;
      padding: 20px;
      box-shadow: 0 5px 15px rgba(255, 111, 97, 0.3);
    }
    .display-letter {
      font-size: 5rem;
      font-weight: bold;
      color: #ff3d6e;
      margin-bottom: 10px;
    }
    .display-word {
      font-size: 2rem;
      margin-bottom: 15px;
      color: #b33a4e;
    }
    .display-image {
      max-width: 100%;
      border-radius: 15px;
      box-shadow: 0 5px 10px rgba(255, 111, 97, 0.4);
    }
    @media (max-width: 500px) {
      .letter-btn {
        width: 50px;
        height: 50px;
        font-size: 1.4rem;
        margin: 6px;
      }
      .display-letter {
        font-size: 4rem;
      }
      .display-word {
        font-size: 1.6rem;
      }
    }
  </style>
</head>
<body>

<h1>Learn the Alphabet!</h1>
<div class="letters-container" id="lettersContainer">
  <!-- Letter buttons will go here -->
</div>

<div class="display-area" id="displayArea">
  <div class="display-letter" id="displayLetter">A</div>
  <div class="display-word" id="displayWord">Apple</div>
  <img
    src="https://upload.wikimedia.org/wikipedia/commons/1/15/Red_Apple.jpg"
    alt="Apple"
    class="display-image"
    id="displayImage"
  />
</div>

<script>
  const alphabet = [
    { letter: 'A', word: 'Apple', img: 'https://upload.wikimedia.org/wikipedia/commons/1/15/Red_Apple.jpg' },
    { letter: 'B', word: 'Ball', img: 'https://upload.wikimedia.org/wikipedia/commons/7/7a/Basketball.png' },
    { letter: 'C', word: 'Cat', img: 'https://upload.wikimedia.org/wikipedia/commons/3/3a/Cat03.jpg' },
    { letter: 'D', word: 'Dog', img: 'https://freedesignfile.com/640394-dog-cartoon-vector.jpg' },
    { letter: 'E', word: 'Elephant', img: 'https://upload.wikimedia.org/wikipedia/commons/3/37/African_Bush_Elephant.jpg' },
    { letter: 'F', word: 'Fish', img: 'https://upload.wikimedia.org/wikipedia/commons/7/7a/Goldfish3.jpg' },
    { letter: 'G', word: 'Guitar', img: 'https://upload.wikimedia.org/wikipedia/commons/4/45/GuitareClassique5.png' },
    { letter: 'H', word: 'Hat', img: 'https://upload.wikimedia.org/wikipedia/commons/3/32/Red_top_hat.svg'.replace('.svg','.png') },
    { letter: 'I', word: 'Ice cream', img: 'https://upload.wikimedia.org/wikipedia/commons/1/18/Blue_ice_cream_cone.png' },
    { letter: 'J', word: 'Juice', img: 'https://upload.wikimedia.org/wikipedia/commons/4/4f/Orangejuice.jpg' },
    { letter: 'K', word: 'Kite', img: 'https://upload.wikimedia.org/wikipedia/commons/1/1a/Kite_%28PSF%29.png' },
    { letter: 'L', word: 'Lion', img: 'https://upload.wikimedia.org/wikipedia/commons/7/73/Lion_waiting_in_Namibia.jpg' },
    { letter: 'M', word: 'Monkey', img: 'https://freepngimg.com/thumb/monkey/5-2-monkey-png-picture.png' },
    { letter: 'N', word: 'Nest', img: 'https://upload.wikimedia.org/wikipedia/commons/5/5c/Birds_nest_icon.svg'.replace('.svg','.png') },
    { letter: 'O', word: 'Owl', img: 'https://upload.wikimedia.org/wikipedia/commons/8/85/Cartoon_owl.svg'.replace('.svg','.png') },
    { letter: 'P', word: 'Pineapple', img: 'https://upload.wikimedia.org/wikipedia/commons/c/cb/Pineapple_and_cross_section.jpg' },
    { letter: 'Q', word: 'Queen', img: 'https://upload.wikimedia.org/wikipedia/commons/2/29/Crown_icon.svg'.replace('.svg','.png') },
    { letter: 'R', word: 'Rainbow', img: 'https://upload.wikimedia.org/wikipedia/commons/0/04/Cartoon_Rainbow.svg'.replace('.svg','.png') },
    { letter: 'S', word: 'Sun', img: 'https://upload.wikimedia.org/wikipedia/commons/1/17/Sun_symbol.svg'.replace('.svg','.png') },
    { letter: 'T', word: 'Tiger', img: 'https://upload.wikimedia.org/wikipedia/commons/5/56/Tiger.50.jpg' },
    { letter: 'U', word: 'Umbrella', img: 'https://upload.wikimedia.org/wikipedia/commons/1/19/Closed_Umbrella.svg'.replace('.svg','.png') },
    { letter: 'V', word: 'Violin', img: 'https://upload.wikimedia.org/wikipedia/commons/1/1b/Violin_VL100.png' },
    { letter: 'W', word: 'Whale', img: 'https://upload.wikimedia.org/wikipedia/commons/e/e9/Whale_icon.svg'.replace('.svg','.png') },
    { letter: 'X', word: 'Xylophone', img: 'https://upload.wikimedia.org/wikipedia/commons/5/58/Xylophone_icon.svg'.replace('.svg','.png') },
    { letter: 'Y', word: 'Yacht', img: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Sailing_yacht_icon.svg'.replace('.svg','.png') },
    { letter: 'Z', word: 'Zebra', img: 'https://freedesignfile.com/650657-zebra-cartoon-vector.jpg' }
  ];

  const lettersContainer = document.getElementById('lettersContainer');
  const displayLetter = document.getElementById('displayLetter');
  const displayWord = document.getElementById('displayWord');
  const displayImage = document.getElementById('displayImage');

  alphabet.forEach(item => {
    const btn = document.createElement('button');
    btn.textContent = item.letter;
    btn.classList.add('letter-btn');
    btn.addEventListener('click', () => {
      displayLetter.textContent = item.letter;
      displayWord.textContent = item.word;
      displayImage.src = item.img;
      displayImage.alt = item.word;
    });
    lettersContainer.appendChild(btn);
  });
</script>

</body>
</html>

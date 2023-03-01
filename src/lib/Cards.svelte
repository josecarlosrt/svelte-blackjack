<script>
let cards = [];
let sum = 0;
let hasBlackJack = false;
let isAlive = false;
let message = "";
let messageEl = "Want to play a round?";
let sumEl = "Sum: ";
let cardsEl = "Cards: ";


function getRandomCard() {
    let randomNumber = Math.floor( Math.random()*13 ) + 1
    if (randomNumber > 10) {
        return 10
    } else if (randomNumber === 1) {
        return 11
    } else {
        return randomNumber
    }
}

function startGame() {
    isAlive = true
    let firstCard = getRandomCard()
    let secondCard = getRandomCard()
    cards = [firstCard, secondCard]
    sum = firstCard + secondCard
    renderGame()
}

function renderGame() {
    cardsEl = "Cards: "
    for (let i = 0; i < cards.length; i++) {
        cardsEl += cards[i] + " "
    }
    
    sumEl = "Sum: " + sum
    if (sum <= 20) {
        message = "Do you want to draw a new card?"
    } else if (sum === 21) {
        message = "You've got Blackjack!"
        hasBlackJack = true
    } else {
        message = "You're out of the game!"
        isAlive = false
    }
    messageEl = message
}


function newCard() {
    if (isAlive === true && hasBlackJack === false) {
        let card = getRandomCard()
        sum += card
        cards.push(card)
        renderGame()        
    }
}


</script>
<h3>{messageEl}</h3>
<h3>{cardsEl}</h3>
<h3>{sumEl}</h3>
<!-- <button on:click={increment}>
    Start Game
  </button> -->
<div class="buttons-box">
    <button on:click={startGame}>
        Start Game
      </button>
      
      <button on:click={newCard}>
        New Card!
      </button>
</div>
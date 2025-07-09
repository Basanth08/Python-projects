# Blackjack Card Game

I built a complete implementation of the classic Blackjack card game with betting system, dealer AI, and full game logic. It's designed to give you the authentic casino experience right on your computer.

## 🃏 What I Built

- **Complete Blackjack Rules**: I implemented standard casino Blackjack gameplay
- **Betting System**: I created a system where you can place bets with a starting balance of $500
- **Dealer AI**: I programmed an automated dealer with standard hit/stand rules
- **Card Management**: I built a full deck with proper shuffling
- **Hand Evaluation**: I made automatic hand value calculation
- **Blackjack Detection**: I added special handling for natural Blackjack
- **Multiple Rounds**: I designed it so you can play until you run out of money

## 📁 How I Structured the Project

```
blackjack-card-game-solution/
├── main.py          # I put the game entry point here
├── game.py          # I handle main game logic and flow control here
├── card.py          # I implemented the card class here
├── deck.py          # I manage deck and shuffling here
├── hand.py          # I handle hand evaluation and display here
├── player.py        # I created the player class with balance here
└── dealer.py        # I built the dealer class here
```

## 🚀 Getting Started

### What You'll Need
- Python 3.6+ (I used features that require this version)
- No external dependencies (I kept it simple!)

### How to Run My Game

```bash
cd blackjack-card-game-solution
python main.py
```

## 🎯 How I Made It Work

### Game Rules I Implemented
- **Objective**: I made it so you beat the dealer by getting closer to 21 without going over
- **Card Values**: I programmed:
  - Number cards (2-10): Face value
  - Face cards (J, Q, K): 10 points
  - Ace: 1 or 11 (I made it automatically optimize)
- **Dealer Rules**: I made the dealer hit on 16 or below, stand on 17+

### Betting System I Created
- **Starting Balance**: I gave you $500 to start
- **Minimum Bet**: I set it at $1
- **Winning Payouts**: I programmed:
  - Regular win: 1:1 (double your bet)
  - Blackjack: 1.5:1 (2.5x your bet)
  - Tie: Return original bet

## 🎮 Game Flow I Designed

### 1. Round Start
```
Welcome to Blackjack!
You are starting with $500, would you like to play?
```

### 2. Betting
```
Place your bet: $25
```

### 3. Dealing
```
You are dealt: [A♠, 7♣]
The dealer is dealt: [K♥, ?]
```

### 4. Player Turn
```
You now have: [A♠, 7♣] (18)
Would you like to hit or stay? hit
You are dealt: 3♦
You now have: [A♠, 7♣, 3♦] (21)
```

### 5. Dealer Turn
```
The dealer has: [K♥, 6♠] (16)
The dealer hits and is dealt: 9♣
The dealer has: [K♥, 6♠, 9♣] (25)
The dealer busts, you win $25 :)
```

## 🔧 Technical Details I Implemented

### Key Classes I Built

#### `Game`
- I made it the main game controller
- I programmed it to manage betting, dealing, and round flow
- I added win/loss determination
- I designed it to control game loop and balance management

#### `Card`
- I created it to represent individual playing cards
- I made it handle suit and rank display
- I added hidden card functionality

#### `Deck`
- I built it to manage a 52-card deck
- I implemented a shuffling algorithm
- I made it handle card dealing

#### `Hand`
- I programmed it to evaluate hand value with Ace optimization
- I made it manage card collection
- I added string representation handling

#### `Player`
- I created it to store player balance
- I made it manage betting and payouts
- I added current hand tracking

#### `Dealer`
- I built automated dealer behavior
- I made it follow standard hit/stand rules
- I programmed it to manage dealer hand

### Game Logic I Wrote

#### Hand Evaluation
```python
def get_value(self):
    value = 0
    aces = 0
    
    for card in self.cards:
        if card.rank == 'A':
            aces += 1
            value += 11
        else:
            value += card.get_value()
    
    # I made it adjust aces from 11 to 1 if needed
    while value > 21 and aces > 0:
        value -= 10
        aces -= 1
    
    return value
```

#### Blackjack Detection
- I made it detect natural Blackjack (Ace + 10-value card)
- I programmed special payout of 1.5:1
- I made it an automatic win unless dealer also has Blackjack

## 🎯 Game Features I Built

### Betting System
- **Balance Tracking**: I made real-time balance updates
- **Bet Validation**: I ensured sufficient funds
- **Minimum Bet Enforcement**: I set $1 minimum bet requirement

### Dealer AI
- **Standard Rules**: I made it hit on 16 or below, stand on 17+
- **Hidden Card**: I kept dealer's hole card hidden until your turn ends
- **Automatic Play**: I made dealer actions automated

### Card Display
- **Unicode Suits**: I used ♠ ♥ ♦ ♣ for visual appeal
- **Hidden Cards**: I used "?" for dealer's hole card
- **Clear Formatting**: I made easy-to-read card representation

## 🛡️ Error Handling I Built

- **Invalid Input**: I added graceful handling of invalid commands
- **Insufficient Funds**: I prevented betting more than available balance
- **Invalid Bets**: I rejected negative or zero bets
- **Game State Validation**: I ensured proper game flow

## 📊 Game Statistics I Track

### Win Conditions I Programmed
- **Player Blackjack**: 1.5:1 payout
- **Dealer Bust**: 1:1 payout
- **Higher Hand Value**: 1:1 payout
- **Tie**: Return original bet

### Loss Conditions I Set Up
- **Player Bust**: Lose entire bet
- **Dealer Higher Value**: Lose entire bet
- **Dealer Blackjack**: Lose entire bet (unless you also have Blackjack)

## 🔄 Game Loop I Designed

```
Start Game → Check Balance → Place Bet → Deal Cards → 
Player Turn → Dealer Turn → Determine Winner → Update Balance → 
Play Again?
```

## 🎯 What I Learned Building This

This project taught me:
- Object-oriented programming principles
- Game state management
- User input handling
- Mathematical calculations
- String formatting and display
- Error handling and validation
- Algorithm implementation (shuffling, hand evaluation)
- Game design patterns 
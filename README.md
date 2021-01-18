# Release TODO:

### Backend Improvements & Optimizations
> Discord Interactions
###### We'll be switching from a traditional command handler, `!command`, to using Discord's new Interactions system (slash commands)
- [ ] Setup interactions handler
- [ ] Register the `"INTERACTIONS_CREATE"` WebSocket event on client ready
- [ ] Setup new Mongo database
- [ ] Implement the "Casino Economy"
  - [ ] Setup all transactions through the `USN Casino` bot user

### Casino Account System
###### Basically a "Create-an-Account" system. The main premise being, you can only see the #casino-usn channel if you register an account. Hopefully this will prevent everyone getting pinged about robberies every day if they don't want to participate in the casino. Also adds the possibility for the casino being opened to everyone (not just Admin+)
- [ ] Re-design user documents in Mongo
  - [ ] Account ID / Account Number
  - [ ] Cash Balance
  - [ ] NixxCoin Balance
  - [ ] Account Age
  - [ ] Account Inventory
  - [ ] "Threat Index" (Explained Later)
- [ ] `/openaccount` Command
- [ ] `/closeaccount` Command

### USN Store / Casino Shop
###### Version 2 will finally include this system. We may introduce a "player shop" system at some point but for the release, all items will be through the official shop. Users will be able to purchase items of different rarity. Static items, costmetic "role(s)", priority queue, and maybe even special access to a vehicle
- [ ] `/shop` Command
- [ ] Setup initial item list
  - [ ] Priority Queue Points (Under Review w/ Nixx)
  - [ ] High Roller
  - [ ] Account Security
  - [ ] Money Multiplier
  - [ ] Getaway Car
  - [ ] Speed Potion
  - [ ] "Friends in High Places"
- [ ] Implement inventories to the users
  - [ ] Tradeable inventories system

- [ ] Black Market??

### Robberies & Heist System
> Robberies
- [ ] `/rob` Command
  - [ ] Setup initial balance tables

> Heists
###### Opportunities to start a Heist of the casino will randomly appear. A user will pay a "setup" fee to start the heist and get the equipment needed. From there, other users can "buy into" the heist for a cut. The more players join, the higher chance for success but the lower the cut per user. This has great potential to be integrated with the server as well (collecting items, cutting off camera feeds, possibly even starting the heist from inside the game)
  - [ ] Create Heist document in Mongo
    - [ ] Heist Date
    - [ ] Potential Take
    - [ ] Heist Members
        - [ ] Heist Leader
        - [ ] Crew (Heist Members)
  - [ ] Create Heist Opportunity System
  - [ ] Setup initial balance tables
  - [ ] `/startheist` Command
  - [ ] `/joinheist` Command
  
### Loanshark System
###### Users will be able to take a loan through a very shady medium. Loans will grant a good chunk of change, but if they aren't payed back on time - you're toast.  
- [ ] `/loanshark` Command
- [ ] Setup initial balance tables
- [ ] Create payback system
  - [ ] Create Loanshark Discord User (for paying back the loan)
  - [ ] Link the Loanshark Account as a "bot"

## New or Improved Games
### Spin the Wheel / Wheel of Fortune
###### Users will "spin the wheel" a randomized gif will be sent showing the user what they've won. Will take quite a bit of work creating all the gifs, maybe using video files would be easier (prevent the auto replay feature of gifs)
- [ ] `/spin` Command
  - [ ] Setup initial balance tables
  - [ ] Create the gifs (or videos) to show the winnings / losses
  
### Automated Guessing Games
###### We'll have the bot post guessing games periodically throughout each day that users can participate in. Guess the correct number within the specified range, win the prize.
- [ ] Setup inital balance tables
  - [ ] Define use-able ranges
  - [ ] Define use-able prizes
- [ ] Create auto-start system

## Jackpot
###### A game of percentages. Once a users bets into the jackpot, their percentage to win will go up.
- [ ] Setup inital balance tables
- [ ] `/jackpot` Command
- [ ] `/buy-in` Command

### Giveaway / Lottery System (Possibility, not confirmed)
###### For Nixx to run giveaways. Maybe even put a "pay-wall" to it. Effectively a buy-in giveaway. Possible prizes: Discord Nitro, Patreon Spot Opening, Custom Role for a period of time, Custom TeamSpeak group for a period of time.

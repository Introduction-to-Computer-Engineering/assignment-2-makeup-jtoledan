This is a simple text based game I designed. It has the player make choices that would have them either fight a monster or run from it. It starts with a player entering a cave and the a randomly generated number determines wheter a monster shows up. 

basic.forever(function () {
    let player
    let monster
    let monsterHealth = 20
    let playerHealth = 20
    basic.showString("Hello Player. Press A to enter cave")
    basic.pause(3000) //introduces player to game
    input.onButtonPressed(Button.A, function () {
        basic.showString("Welcome to the Cave of Isolation")
        if (Math.randomRange(0, 20) > 5) {//determines if monster shows up
            basic.showString("A monster has appeared! Tilt up to fight the monster, tilt down to run away")
            if (input.onScreenUp) {//determines if player will fight the monster
                while (playerHealth > 0 || monsterHealth > 0) { // Fight between player and monster
                    playerAttack()
                    if (playerHealth <= 0) { //In case player dies
                        basic.showString("Player has died")
                    } else if (monsterHealth <= 0) {// in case monster dies
                        basic.showString("Monster has died! Congratulations")
                        break
                    }

                }

            } else {// if player tries to run 
                playerHealth -= Math.randomRange(0, 20)
                basic.showString("You tried to run away, but the enemy attacked you!")
                basic.pause(1000)
                basic.showString("Your health is now")
                basic.showNumber(playerHealth)

            }
        } else {// Searching the cave
            basic.showString("You found nothing, try again later!")
            basic.pause(3000)
        }



    })
    function playerAttack() { //Fight between monster and player
        let initiative = Math.randomRange(0, 20)
        if (initiative > Math.randomRange(0, 20)) { //player's attack
            basic.showString("Player attacks first")
            monsterHealth -= Math.randomRange(0, 20)
            basic.showNumber(monsterHealth)
            return monsterHealth

        } else { // monsters attack
            basic.showString("Monster attacks first")
            playerHealth -= Math.randomRange(0, 20)
            basic.showNumber(playerHealth)
            return playerHealth
        }
    }

})

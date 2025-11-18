# TREASURE HUNT 
let name = "Player";
let coins = 10;
let health = 5;
let score = 0;
let hasKey = false;

console.log("Treasure Hunt Start!");

for (let room = 1; room <= 6; room++) {
  console.log("Room:", room);

  if (room === 1) {
    coins += 10;
    score += 5;
    console.log("Found coins!");
  }

  else if (room === 2) {
    health -= 1;
    console.log("Trap! Lost health.");
  }

  else if (room === 3) {
    if (coins >= 10) {
      coins -= 10;
      hasKey = true;
      console.log("Bought a key.");
    }
  }

  else if (room === 4) {
    score += 10;
    console.log("Solved a puzzle!");
  }

  else if (room === 5) {
    if (hasKey) {
      score += 20;
      console.log("Unlocked treasure!");
    } else {
      health -= 2;
      console.log("Door hurt you.");
    }
  }

  else if (room === 6) {
    coins += 30;
    console.log("Treasure stash!");
  }

  if (health <= 0) {
    console.log("You died!");
    break;
  }
}

let status = (health > 0 && score >= 20) ? "WIN" : "LOSE";

console.log("=== Summary ===");
console.log("Name:", name);
console.log("Coins:", coins);
console.log("Health:", health);
console.log("Score:", score);
console.log("Has Key:", hasKey);
console.log("Status:", status);

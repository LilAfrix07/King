# King
Just a nobody tryna be somebody
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

const questions = [
    "What's your favorite drink?",
    "If you could have dinner with any celebrity, who would it be?",
    "What's the most embarrassing thing you've ever done?",
    "What's your guilty pleasure song?",
    "If you could travel anywhere in the world, where would you go?"
];

let score = 0;

function askQuestion(index) {
    if (index < questions.length) {
        rl.question(questions[index] + ' ', (answer) => {
            console.log(`You answered: ${answer}`);
            score++;
            askQuestion(index + 1);
        });
    } else {
        console.log(`Game Over! Your score is: ${score}/${questions.length}`);
        rl.close();
    }
}

console.log("Welcome to the Fun Game for Adults 18+!");
askQuestion(0);

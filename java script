// script.js

const quizData = [
    {
        question: "What is the capital of France?",
        a: "Berlin",
        b: "Madrid",
        c: "Paris",
        d: "Rome",
        correct: "c"
    },
    {
        question: "Who is the President of the USA?",
        a: "Barack Obama",
        b: "Donald Trump",
        c: "Joe Biden",
        d: "George Bush",
        correct: "c"
    },
    {
        question: "What is the largest planet in our solar system?",
        a: "Earth",
        b: "Mars",
        c: "Jupiter",
        d: "Saturn",
        correct: "c"
    },
    {
        question: "Which language is used for web apps?",
        a: "Python",
        b: "JavaScript",
        c: "C++",
        d: "Java",
        correct: "b"
    },
    {
        question:"Garampani sanctuary is located at",
        a:"Junagarh, Gujarat",
        b:"Diphu, Assam",
        c:"Kohima, Nagaland",
        d:"Gangtok, Sikkim",
        correct:"b"
    }
];

const questionEl = document.getElementById("question");
const answerEls = document.querySelectorAll(".answer");
const a_text = document.getElementById("a_text");
const b_text = document.getElementById("b_text");
const c_text = document.getElementById("c_text");
const d_text = document.getElementById("d_text");
const submitBtn = document.getElementById("submit");
const resultEl = document.getElementById("quiz-result");

let currentQuiz = 0;
let score = 0;

loadQuiz();

function loadQuiz() {
    deselectAnswers();
    const currentQuizData = quizData[currentQuiz];
    
    questionEl.innerText = currentQuizData.question;
    a_text.innerText = currentQuizData.a;
    b_text.innerText = currentQuizData.b;
    c_text.innerText = currentQuizData.c;
    d_text.innerText = currentQuizData.d;
}

function deselectAnswers() {
    answerEls.forEach(answerEl => answerEl.checked = false);
}

function getSelected() {
    let answer;
    answerEls.forEach(answerEl => {
        if (answerEl.checked) {
            answer = answerEl.id;
        }
    });
    return answer;
}

submitBtn.addEventListener("click", () => {
    const answer = getSelected();
    
    if (answer) {
        if (answer === quizData[currentQuiz].correct) {
            score++;
        }

        currentQuiz++;

        if (currentQuiz < quizData.length) {
            loadQuiz();
        } else {
            resultEl.innerHTML = `
                <h3>You answered correctly ${score}/${quizData.length} questions.</h3>
                <button onclick="location.reload()">Reload</button>
            `;
            resultEl.style.display = 'block';
            document.getElementById("quiz").style.display = 'none';
        }
    } else {
        alert("Please select an answer before submitting!");
    }
});

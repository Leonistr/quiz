import { useState, useEffect } from "react";
import { db } from "../firebase";
import { collection, addDoc } from "firebase/firestore";
import { useRouter } from "next/router";

const Quiz = () => {
  const [questionIndex, setQuestionIndex] = useState(0);
  const [score, setScore] = useState(0);
  const [loading, setLoading] = useState(false);
  const [feedback, setFeedback] = useState(null);
  const router = useRouter();

  const questions = [
    { question: "5 + 3", options: ["7", "8", "9", "6"], answer: "8" },
    { question: "10 - 4", options: ["5", "6", "7", "8"], answer: "6" },
  ];

  const handleAnswer = async (option) => {
    setLoading(true);
    const isCorrect = option === questions[questionIndex].answer;
    setFeedback(isCorrect ? "correct" : "incorrect");

    if (isCorrect) {
      setScore(score + 1);
    }
    
    await addDoc(collection(db, "quiz_results"), {
      question: questions[questionIndex].question,
      answer: option,
      correct: isCorrect,
      timestamp: new Date(),
    });

    setTimeout(() => {
      setFeedback(null);
      if (questionIndex < questions.length - 1) {
        setQuestionIndex(questionIndex + 1);
      } else {
        router.push("/leaderboard");
      }
      setLoading(false);
    }, 1000);
  };

  return (
    <div className={`flex flex-col items-center justify-center min-h-screen p-4 transition-all duration-500 relative ${feedback === "correct" ? "bg-green-100" : feedback === "incorrect" ? "bg-red-100" : "bg-gray-100"}`}>
      {feedback && (
        <div className={`absolute inset-0 transition-opacity duration-500 ${feedback === "correct" ? "bg-green-500/30" : "bg-red-500/30"}`}></div>
      )}
      <div className="w-full max-w-md bg-white p-6 rounded-2xl shadow-xl relative">
        {loading ? (
          <div className="text-center text-lg font-bold animate-pulse">Загрузка...</div>
        ) : (
          <>
            <h2 className="text-xl font-bold text-center mb-4">{questions[questionIndex].question}</h2>
            <div className="grid grid-cols-2 gap-4">
              {questions[questionIndex].options.map((option, index) => (
                <button
                  key={index}
                  onClick={() => handleAnswer(option)}
                  className={`bg-blue-500 text-white py-2 rounded-lg text-lg hover:bg-blue-600 transition-all relative flex justify-center items-center w-full h-14 sm:h-16 text-center`}
                >
                  {option}
                  {feedback && (
                    <span className={`absolute right-2 text-2xl transition-opacity duration-500 ${option === questions[questionIndex].answer ? "text-green-500" : feedback === "incorrect" && option !== questions[questionIndex].answer ? "text-red-500" : ""}`}>
                      {option === questions[questionIndex].answer ? "✔" : feedback === "incorrect" && option !== questions[questionIndex].answer ? "✖" : ""}
                    </span>
                  )}
                </button>
              ))}
            </div>
          </>
        )}
      </div>
    </div>
  );
};

export default Quiz;

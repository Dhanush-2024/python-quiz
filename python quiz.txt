import random


def general_knowledge_quiz():
    questions = [
        ("What is the capital of France?", ["Paris", "London", "Rome", "Berlin"], "Paris"),
        ("Who wrote 'To Kill a Mockingbird'?", ["Harper Lee", "J.K. Rowling", "Mark Twain", "George Orwell"],
         "Harper Lee"),
        ("What is the largest ocean on Earth?", ["Atlantic", "Indian", "Arctic", "Pacific"], "Pacific"),
        ("Which planet is known as the Red Planet?", ["Venus", "Mars", "Jupiter", "Saturn"], "Mars"),
        ("What is the smallest country in the world?", ["Vatican City", "Monaco", "San Marino", "Liechtenstein"],
         "Vatican City"),
        ("What is the chemical symbol for gold?", ["Au", "Ag", "Pb", "Fe"], "Au"),
        ("Who painted the Mona Lisa?", ["Vincent van Gogh", "Pablo Picasso", "Leonardo da Vinci", "Claude Monet"],
         "Leonardo da Vinci"),
        ("What is the national flower of Japan?", ["Rose", "Tulip", "Cherry Blossom", "Orchid"], "Cherry Blossom"),
        ("Which is the longest river in the world?", ["Amazon", "Nile", "Yangtze", "Mississippi"], "Nile"),
        ("Who developed the theory of relativity?",
         ["Isaac Newton", "Albert Einstein", "Galileo Galilei", "Nikola Tesla"], "Albert Einstein"),
        ("What is the capital of Japan?", ["Beijing", "Seoul", "Tokyo", "Bangkok"], "Tokyo"),
        ("Who was the first person to walk on the moon?",
         ["Buzz Aldrin", "Neil Armstrong", "Yuri Gagarin", "Michael Collins"], "Neil Armstrong"),
        ("What is the hardest natural substance on Earth?", ["Diamond", "Gold", "Iron", "Platinum"], "Diamond"),
        ("Which country is famous for the Great Wall?", ["India", "China", "Mongolia", "Russia"], "China"),
        ("What is the currency of the UK?", ["Euro", "Pound Sterling", "Dollar", "Yen"], "Pound Sterling"),
        ("What is the tallest mountain in the world?", ["K2", "Mount Everest", "Kilimanjaro", "Makalu"],
         "Mount Everest"),
        ("Who wrote '1984'?", ["George Orwell", "Aldous Huxley", "J.K. Rowling", "F. Scott Fitzgerald"],
         "George Orwell"),
        ("What is the chemical formula of water?", ["H2O", "CO2", "O2", "H2SO4"], "H2O"),
        ("Who invented the telephone?", ["Alexander Graham Bell", "Thomas Edison", "Nikola Tesla", "Michael Faraday"],
         "Alexander Graham Bell"),
        ("Which gas is most abundant in Earth's atmosphere?", ["Oxygen", "Carbon Dioxide", "Nitrogen", "Argon"],
         "Nitrogen"),
        ("Who is known as the father of computers?",
         ["Alan Turing", "Charles Babbage", "John von Neumann", "Steve Jobs"], "Charles Babbage"),
        (
        "Which country is known as the Land of the Rising Sun?", ["China", "Japan", "South Korea", "Vietnam"], "Japan"),
        ("What is the largest desert in the world?", ["Sahara", "Gobi", "Kalahari", "Antarctic"], "Antarctic"),
        ("Who discovered penicillin?", ["Marie Curie", "Louis Pasteur", "Alexander Fleming", "Robert Koch"],
         "Alexander Fleming"),
        ("Which is the longest bone in the human body?", ["Femur", "Tibia", "Humerus", "Radius"], "Femur"),
    ]

    while len(questions) < 100:
        questions += questions[:100 - len(questions)]

    score = 0
    random.shuffle(questions)

    for i, (question, options, correct_answer) in enumerate(questions[:100], 1):
        print(f"Q{i}: {question}")
        for idx, option in enumerate(options, 1):
            print(f"{idx}. {option}")

        try:
            user_choice = int(input("Enter the number of your answer: "))
            if options[user_choice - 1] == correct_answer:
                print("Correct! You earn 1 point.")
                score += 1
            else:
                print(f"Wrong! The correct answer is {correct_answer}.")
        except (IndexError, ValueError):
            print("Invalid input. No points awarded.")

    print(f"Your final score: {score}/100")


if __name__ == "__main__":
    general_knowledge_quiz()

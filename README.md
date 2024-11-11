import random
questions = {
    "easy": [("Bonjour means?", "Hello"), ("Merci means?", "Thank you")],
    "medium": [("Quelle heure est-il?", "What time is it?"), ("Je voudrais means?", "I would like")],
    "hard": [("Où se trouve la bibliothèque?", "Where is the library?"), ("J'ai besoin d'aide", "I need help")]
}
selected_questions = random.sample(questions["easy"], 2) + random.sample(questions["medium"], 2) + random.sample(questions["hard"], 2)
current_question = 0
correct_answers = 0
while current_question < len(selected_questions):
    question,answer=selected_questions[current_question]
    print(question)
    answer_entry = input("Enter your answer here:")
    user_answer = answer_entry.strip().lower()
    if user_answer == answer.lower():
        correct_answers += 1
    current_question += 1
    
if correct_answers < 2:
    level = "Beginner"
elif 2 <= correct_answers < 6:
    level = "Intermediate"
else:
    level = "Fluent"    
print("Your current level is:",level)


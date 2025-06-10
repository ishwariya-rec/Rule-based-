# Rule-based-
# expert_system.py

# Simple Rule-Based Expert System for Diagnosing Plant Problems

# Knowledge base: Rules and facts
knowledge_base = {
    "yellow_leaves": "lack of nutrients",
    "brown_spots": "fungal infection",
    "wilting": "underwatering",
    "leaf_drop": "temperature stress",
    "holes_in_leaves": "pest attack"
}

# Decision rules: What to recommend based on problems
recommendations = {
    "lack of nutrients": "Add fertilizer rich in nitrogen.",
    "fungal infection": "Apply fungicide and remove infected leaves.",
    "underwatering": "Increase watering frequency.",
    "temperature stress": "Move plant to a stable temperature environment.",
    "pest attack": "Use organic insecticide or neem oil spray."
}

# Inference engine
def diagnose(symptoms):
    print("🧠 Analyzing symptoms...")
    for symptom in symptoms:
        if symptom in knowledge_base:
            problem = knowledge_base[symptom]
            solution = recommendations[problem]
            print(f"✅ Detected Problem: {problem}")
            print(f"💡 Recommendation: {solution}\n")
        else:
            print(f"⚠️ No known diagnosis for symptom: '{symptom}'\n")

# Main driver
if __name__ == "__main__":
    print("🌿 Plant Doctor Expert System 🌿")
    print("Enter symptoms one by one (e.g., yellow_leaves, wilting)")
    print("Type 'done' to finish input.\n")

   user_symptoms = []
    while True:
        symptom = input("Enter symptom: ").strip().lower()
        if symptom == 'done':
            break
        user_symptoms.append(symptom)

  if user_symptoms:
        diagnose(user_symptoms)
    else:
        print("No symptoms entered. Cannot perform diagnosis.")

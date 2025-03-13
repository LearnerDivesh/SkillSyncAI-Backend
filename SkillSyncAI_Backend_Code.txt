 
# SkillSyncAI - Backend (Flask API)

from flask import Flask, request, jsonify

app = Flask(__name__)

# Dummy trainer database (To be replaced with real DB integration)
trainers = [
    {"id": 1, "name": "John Doe", "expertise": "Data Science", "rating": 4.8, "experience": 5},
    {"id": 2, "name": "Jane Smith", "expertise": "Cloud Computing", "rating": 4.5, "experience": 7}
]

@app.route('/search-trainers', methods=['POST'])
def search_trainers():
    data = request.json
    expertise = data.get("expertise")

    # AI-based filtering logic (Placeholder for ML model integration)
    matched_trainers = [t for t in trainers if expertise.lower() in t["expertise"].lower()]
    
    return jsonify({"message": "Trainer search results", "data": matched_trainers})

if __name__ == '__main__':
    app.run(debug=True)

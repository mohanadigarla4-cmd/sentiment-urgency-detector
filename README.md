# sentiment-urgency-detector
An AI-powered application that analyzes text to detect sentiment (positive, neutral, negative) and urgency levels (high, medium, low) using Natural Language Processing (NLP).
Sentiment & Urgency Detector
Problem Statement

Customer support teams receive a large volume of inbound tickets every day. High-priority complaints, urgent requests, and potential churn signals can be missed in the queue, leading to customer dissatisfaction and escalations.

The Sentiment & Urgency Detector automatically analyzes incoming support ticket text using an LLM to identify:

Customer sentiment (Positive, Neutral, Negative)
Urgency level
Churn-risk indicators
Escalation likelihood

Tickets exceeding configured thresholds are automatically flagged and sent to a Discord channel with an explanation, enabling faster response and proactive customer retention.

Team Members
Name	Role
Member 1	AI/ML Development
Member 2	Backend Development
Member 3	Integration & Deployment
Member 4	Documentation & Testing

(Replace with actual team details.)

Features Implemented
Core Features

✅ Ticket sentiment analysis

✅ Urgency detection

✅ Churn-risk identification

✅ LLM-generated reasoning

✅ Confidence scoring

✅ Threshold-based alerting

✅ Discord notifications

Advanced Features

✅ Structured JSON output

✅ Customizable scoring thresholds

✅ Real-time processing

✅ Explainable AI decisions

Architecture Overview
┌───────────────────┐
│ Customer Ticket   │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ LLM Classifier    │
│                   │
│ • Sentiment Score │
│ • Urgency Score   │
│ • Churn Risk      │
│ • Reasoning       │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Rule Engine       │
│ Threshold Check   │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Discord Alert Bot │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Support Team      │
└───────────────────┘
Workflow
Customer submits support ticket.
Ticket text is sent to the LLM.
LLM generates:
Sentiment score
Urgency score
Churn-risk score
Reason
Rule engine evaluates thresholds.
High-risk tickets trigger Discord alerts.
Support agents receive actionable notifications.
Tools and Technologies Used
AI & ML
OpenAI GPT API (Classifier)
Prompt Engineering
JSON Structured Outputs
Backend
Python
FastAPI
Integration
Discord Webhooks
REST APIs
Development Tools
VS Code
Git
GitHub
Optional Deployment
Docker
Render
Railway
AWS
Setup Instructions
1. Clone Repository
git clone https://github.com/your-repo/sentiment-urgency-detector.git

cd sentiment-urgency-detector
2. Create Virtual Environment
python -m venv venv

Activate environment:

Windows

venv\Scripts\activate

Mac/Linux

source venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
4. Configure Environment Variables

Create a .env file:

OPENAI_API_KEY=your_api_key

DISCORD_WEBHOOK_URL=your_webhook_url
Run Instructions

Start the application:

python app.py

or

uvicorn main:app --reload

Send sample request:

curl -X POST http://localhost:8000/analyze \
-H "Content-Type: application/json" \
-d '{
"text":"I am extremely disappointed with your service and will cancel my subscription if this issue is not fixed today."
}'
Sample Input
I am extremely disappointed with your service.
This is the third time I have reported this issue.
If it isn't fixed today, I will cancel my subscription.
Sample Output
{
  "sentiment": "Negative",
  "sentiment_score": 0.94,
  "urgency_score": 0.92,
  "churn_risk_score": 0.89,
  "alert": true,
  "reason": "Customer expresses strong dissatisfaction, references repeated unresolved issues, and explicitly mentions cancelling subscription."
}
Discord Alert Example
🚨 High Priority Ticket Detected

Sentiment: Negative (0.94)

Urgency: High (0.92)

Churn Risk: High (0.89)

Reason:
Customer threatens cancellation due to repeated unresolved issues.

Ticket:
"I am extremely disappointed with your service..."
AI Capability Demonstrated
LLM-Based Classification

The system uses a Large Language Model to:

Analyze emotional tone
Detect urgency indicators
Identify churn-risk language
Generate human-readable explanations
Produce structured classification outputs
Explainable AI

Instead of only assigning scores, the model provides reasoning behind each decision, improving trust and transparency.

Assumptions and Limitations
Assumptions
Ticket text is in English.
Customer messages contain sufficient context.
Discord webhook is configured correctly.
Limitations
Sarcasm may not always be detected accurately.
Performance depends on LLM quality.
Thresholds may require tuning for different industries.
Very short tickets may reduce classification accuracy.
Demo Video Link
Demo Video:
https://your-demo-video-link.com

(Replace with your actual demo video URL.)

Expected ROC (Result-Oriented Capability)

Input: Inbound customer support ticket

Processing: LLM classification with sentiment, urgency, and churn-risk scoring

Output: Automated Discord alert for tickets exceeding risk thresholds, including scores and explanation

Business Impact: Faster response to critical customer issues, reduced escalations, and improved customer retention.
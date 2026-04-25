Day 1 Assignment — Context Failure → Context Fix
Agentic AI Enterprise Mastery Bootcamp · Day 1
This project demonstrates why naive string-based LLM calls lose context across turns, and how the LangChain Messages API fixes the problem with structured SystemMessage / HumanMessage objects.
The goal is not to print outputs — it is to understand system behavior in production.
Project Structure
agentic-day1/
├── .gitignore
├── requirements.txt
├── README.md
└── app.py
Setup

Clone the repository:

bash   git clone https://github.com/durganuvvula/week1-assignment1.git
   cd week1-assignment1

Create and activate a virtual environment:

bash   python3 -m venv env
   source env/bin/activate          # macOS / Linux
   # env\Scripts\activate           # Windows

Install dependencies:

bash   pip install -r requirements.txt

Create a .env file in the project root (this file is git-ignored):

   OPENAI_API_KEY=sk-...

Run the script:

bash   python app.py
What the Script Demonstrates
Day 2 Routing

Agentic AI Enterprise Mastery Bootcamp · Day 2
A minimal but production-minded LangGraph workflow that routes users to different support paths based on their tier (VIP vs Standard), with conversation state tracked in a typed SupportState.
The routing logic is kept as a separate, pure function so it is explicit, testable, and auditable.

What the Graph Does

check_tier — entry node that inspects the first user message and decides whether the user is vip or standard (a mock implementation; in production this would query a CRM or entitlements service).
route_by_tier — pure routing function used by add_conditional_edges to send VIP users to vip_path and everyone else to standard_path.
vip_agent — VIP fast-lane node. Sets should_escalate = False and returns a priority response.
standard_agent — standard support node. Sets should_escalate = True to simulate possible escalation.

Execution Insructions

conda create --prefix ./env python=3.12 -y
conda activate ./env 
pip install -r requirements.txt

python app.py```# Day2-Routing


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


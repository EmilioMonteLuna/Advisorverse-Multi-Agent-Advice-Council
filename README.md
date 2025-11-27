# Advisorverse: Multi-Agent Decision Concierge

A sophisticated multi-agent AI system that provides diverse perspectives on life's toughest decisions by consulting five autonomous AI advisors simultaneously.

> **Built for**: <a href="https://www.kaggle.com/competitions/agents-intensive-capstone-project">Google's Agents Intensive 5-Day Course</a> - Capstone Project  
> **Full Writeup**: <a href="https://www.kaggle.com/competitions/agents-intensive-capstone-project/discussion/3345980">Read on Kaggle</a>

## The Problem

Most people face "decision paralysis" when making major life choices—career changes, difficult conversations, financial moves.  We often make these decisions in isolation, limited by our own biases and current emotional state. While we could ask friends or mentors, that process is slow and their availability is limited. 

Existing AI tools typically provide a single, homogenized answer.  They try to be the "average" helpful assistant, which often results in safe, generic advice that lacks nuance.  **Users don't need one average answer; they need diverse perspectives to weigh options effectively.**

## Why Multi-Agent Architecture? 

Agents solve the "Single Perspective Bias."

A standard LLM call generates one token stream based on one system prompt. To get diverse advice, a user would have to manually prompt a chatbot five different times with five different personas. 

By using a Multi-Agent Architecture, we can:

- **Parallelize Perspectives**: Spin up five distinct "minds" simultaneously, drastically reducing the time to insight
- **Enforce Personality Integrity**: Each agent has a rigid system prompt and "worldview" that prevents them from drifting into generic advice
- **Simulate a Council**: The value isn't in any single agent's answer, but in the contrast between them.  Agents are the only way to simulate a real-world advisory board where disagreement is a feature, not a bug

## The Board of Advisors

When you submit a dilemma, you'll receive guidance from five distinct perspectives:

### 💪 The Tough Love Coach
Focuses on action, discipline, and hard truths. Challenges you to push past fear and take decisive action.

### 🧠 The Empathetic Therapist
Focuses on emotional well-being, mental health, and safety.  Ensures you're considering the human cost of your decisions.

### 📊 The Business Strategist
Focuses on ROI, risk analysis, and long-term gain.  Breaks down the financial and strategic implications of your choices.

### 🧘 The Philosophical Sage
Focuses on ethics, purpose, and deeper meaning. Reframes decisions around life regret and personal values.

### 🎲 The Wildcard
Offers lateral thinking and unconventional, high-risk/high-reward ideas.  Proposes creative third options you hadn't considered.

## Example Use Case

**User Question**: "Should I quit my stable job to start a risky startup?"

**The Responses**:
- **The Strategist** immediately breaks down the financial runway needed and probability of failure
- **The Coach** challenges the user's fear of failure and urges them to take the leap
- **The Therapist** asks about the user's current stress levels and burnout risk
- **The Sage** reframes the question around life regret rather than money
- **The Wildcard** suggests keeping the job but outsourcing the work to fund the startup (a chaotic third option)

The user can then vote on the most helpful advice, which updates a persistent memory bank to tailor future interactions.

## Technical Architecture

This project utilizes a modern AI stack designed for parallel execution and state management:

- **Orchestration**: Python-based "ParallelAgent" class that manages asynchronous calls to the LLM
- **Model**: Google Gemini 1.5 Pro (via Vertex AI) for high-context understanding and nuanced persona adoption
- **Memory**: A dual-layer memory architecture:
  - **Session Memory**: Retains context for the immediate back-and-forth conversation
  - **Long-term Memory (SQLite)**: Stores user voting patterns to identify which "Advisor" the user prefers over time
- **Development Environment**: Developed and tested within a Kaggle Notebook environment, utilizing Vertex AI API keys for agent deployment

## Getting Started

1. Clone this repository
2. Set up your Google Vertex AI credentials
3. Install required dependencies
4. Open the Jupyter Notebook in Kaggle or your local environment
5. Run the cells to initialize the multi-agent system
6. Submit your dilemma and receive guidance from all five advisors

## Future Enhancements

Given more time, here are planned improvements:

- **Inter-Agent Debate**: Add a "Debate Mode" where agents can read each other's outputs and argue (e.g., The Strategist refuting the Wildcard's plan)
- **Custom Persona Creator**: Allow users to build their own advisors (e.g., "My Mom," "Steve Jobs," "A 5-year-old") by tweaking system prompts via a UI
- **RAG Integration**: Give the "Business Strategist" agent access to real-time stock market data or news via the Google Search tool to make its advice factually grounded
- **Voice Interface**: Turn this into a literal roundtable discussion where users can hear different voices arguing for different paths

## Why This Matters

Making big decisions in isolation leads to regret.  Advisorverse gives you instant access to a diverse council of perspectives, helping you make more informed choices by seeing your problem through multiple lenses simultaneously.

## About This Project

This project was completed as the capstone for Google's **Agents Intensive 5-Day Course** on Kaggle, showcasing the power of multi-agent systems in practical decision-making scenarios.

For a detailed breakdown of the design decisions, implementation details, and lessons learned, check out the <a href="https://www.kaggle.com/competitions/agents-intensive-capstone-project/discussion/3345980">full writeup on Kaggle</a>.

## License

MIT License

## Author

**Emilio Monte Luna**  
<a href="https://github.com/EmilioMonteLuna">GitHub</a> | <a href="https://www.kaggle.com/emiliomunteluna">Kaggle Profile</a>

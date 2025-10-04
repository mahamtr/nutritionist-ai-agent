# nutritionist-ai-agent

This project is a LangGraph + React-based AI Nutrition Assistant, designed to let users track their meals and get insights on calories, macronutrients, and nutrition quality — all through natural chat interactions.

⸻

Overview

The AI agent uses a ReAct (Reasoning + Acting) architecture to interact with the user and dynamically call backend tools for:
	•	Meal logging — record what you’ve eaten (“I had two eggs and toast for breakfast”).
	•	Nutrition lookup — fetch calories and macronutrient data from a nutrition API.
	•	Progress summaries — get daily or weekly summaries of nutritional intake.
	•	Goal tracking — compare intake against calorie or protein goals.

The goal of this project is to demonstrate agentic reasoning using LangGraph, LangChain, and a React UI, in an easy-to-deploy Docker environment.

⸻

Architecture

Frontend: React (Next.js or Vite)
Backend: FastAPI + LangGraph
Database: SQLite or PostgreSQL (configurable)
LLM Provider: OpenAI, Anthropic, or Hugging Face (easily swappable)
Containerization: Docker Compose for local and production deployment

Flow
	1.	The user interacts with the chat UI.
	2.	The LangGraph agent receives the prompt and decides whether to:
	•	Respond directly (reasoning), or
	•	Call a tool, such as:
	•	log_meal(meal_description)
	•	get_daily_summary(date)
	•	search_food_info(food_name)
	3.	The agent integrates tool results into its reasoning chain.
	4.	The UI updates to show:
	•	Chat history
	•	Logged meals
	•	Nutritional summaries and charts

  Example Tools

  Tool
 - log_meal() = Adds a meal to the database
 - get_daily_summary() = Summarizes total calories/macros
 - search_food_info() = Looks up nutritional info for a food
 - get_goal_progress() = Compares intake with user goals

UI Features
	•	Chat interface powered by the agent
	•	Meal log view (list of meals and nutrients)
	•	Summary dashboard (calories, macros, goals)
	•	Editable goals (daily calorie/protein targets)

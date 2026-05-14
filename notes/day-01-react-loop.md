# Day 01 — The ReAct Loop: Heartbeat of Every AI Agent

## The Core Question
What is the minimum viable thing an "agent" needs to do 
that a regular chatbot doesn't?

**Answer: It needs to loop.**

## The ReAct Pattern
- THOUGHT: The model reasons about the current situation
- ACTION: The model decides to call a tool
- OBSERVE: The model sees the tool's result
- Repeat until DONE

## Key Insight
Every agent framework (LangGraph, AutoGen, CrewAI) is just
this loop with extra features. If you understand this loop,
you understand all of them at their core.

## What I Built Today
- A mock LLM that simulates structured thoughts/actions
- A tool registry that maps tool names to Python functions
- A ReAct loop that runs until the agent says DONE
- End-to-end: give a goal, agent completes it in steps

## My "Aha" Moment
The LLM doesn't "call" a tool. It just outputs TEXT that 
looks like a tool call. YOUR code parses that text and 
actually calls the function. The LLM never touches your code.

## Questions I Still Have
- How does a real LLM output structured tool calls reliably?
- What happens when the LLM outputs malformed JSON?
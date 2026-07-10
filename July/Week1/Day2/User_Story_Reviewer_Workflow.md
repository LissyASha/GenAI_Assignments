# Task 1: User Story Reviewer using Langflow, Jira, Groq and Postman

## Objective

Build an AI-powered User Story Reviewer that extracts a Jira user story,
reviews it using an LLM through Langflow, and validates the output using
Postman.

## Steps

1. Extract a User Story from Jira.
2. Pass the extracted User Story to the Langflow workflow.
3. Review the user story by providing prompts to the LLM.
4. Copy the generated cURL command from Langflow.
5. Import or execute the same request in Postman.
6. Verify that the output generated through Postman matches the output
produced by Langflow.

## Langflow Workflow

API Request -> Parser -> Prompt Template -> Groq LLM -> Prompt
Template -> Groq LLM -> Chat Output

## Components

* API Request Component for Jira API integration.
* Parser Component to extract story details.
* Prompt Template for review instructions.
* Groq LLM for analysis and scoring.
* Chat Output to display results.

## Review Parameters

* Clarity
* Completeness
* Business Value Alignment
* Testability
* Technical Feasibility

## Validation

Compare Langflow and Postman responses for consistency.

## 


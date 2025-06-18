AutoGen Stock performance analyst Chatbot
This project demonstrates the implementation of an intelligent stock analysis chatbot built using the autogen framework. Designed for interactive financial analysis, this system leverages multiple AI agents to provide insights into stock data, making it a valuable tool for quick market overviews and preliminary investment research.

Project Description
The AutoGen Stock Analysis Chatbot empowers users to inquire about stock performance and receive analytical summaries. It orchestrates a conversation between a user-facing proxy agent and a specialized financial analyst agent, which utilizes a custom tool to fetch real-time daily stock data from the Alpha Vantage API. The project highlights the capabilities of multi-agent systems in automating complex information retrieval and analysis tasks.

LLM: gemini 2.5 flash
stock price data: Alpha vantage api

Features
Interactive Analysis: Engage in a conversational format to request stock data and analysis.

Two-Agent Architecture:

- User Proxy (Rattanon): Represents the human user, manages human input, and orchestrates tool execution.

- Financial Analyst (Mr.analyst): Provides expert financial opinions, synthesizes data, and includes necessary disclaimers.
  

Data Retrieval Tool (get_stock_data): Custom Python function integrated to fetch daily stock data (open, high, low, close, volume) from Alpha Vantage.

- Configurable Data Output: Option to retrieve compact (last 100 days) or full historical stock data.

- Robust Error Handling: Includes try-except blocks for API calls to ensure stable operation.

Clear Communication: Analyst agent is programmed to provide concise analyses and include disclaimers about investment risks.

How It Works
The chatbot operates on a multi-agent paradigm:

1. User Query: The user_proxy (representing you) initiates a query, such as asking for an analysis of a specific stock.

2. Analyst Action: The analyst agent, upon receiving the query, determines if stock data is required for its analysis.

3. Tool Invocation: If data is needed, the analyst calls the get_stock_data tool.

4. Tool Execution: The user_proxy executes the get_stock_data tool, fetching data from Alpha Vantage and converting it into a Markdown-formatted string.

5. Data Provision: The retrieved data is provided back to the analyst.

6. Analysis & Response: The analyst processes the data, combines it with its general understanding of market dynamics, and generates a concise financial analysis, which is then communicated back through the user_proxy to the human user.

7. Termination: The conversation can be gracefully terminated by either agent if "terminate" is detected in a message, or after a maximum number of consecutive auto-replies.


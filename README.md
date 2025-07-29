# Grexpensify-n8n
An n8n workflow that track's group's expenses via Telegram Bot automation using LLM and Google Sheets.

This is an n8n workflow that automates a model group expense tracking mobile application into a telegram bot. Here's what it does :

1. Listens for a telegram message from the Telegram bot that I made: If an account hits the Telegram bot with  some message regarding trip expenses (Like adding expense, splitting expense, settling past payments  - with a group) - the telegram message triggers the entire Automation.
2. I use Google sheets as a simple pseudo database here, where the group's details are kept along with trip expenses.
3. I assume that the automation will only be used by x number of people at a time which will be the group of friends who are travelling together in a trip. Thus, the google sheets should contain the necessary telegram IDs who will be using the telegram bot (Essentially, manually taking care of Auth).
4. The automation takes care of inserting expenses, splits and payments done during the trip via a simple text prompt given to the telegram bot. The conversion of Simple natural language text to JSON is done via Llama 3.3 70B LLM (running in groq).
5. There are dedicated code blocks written in simple javascript that takes care of handling additional things like calculating how much split should happen, who owes who - how much, and so on.

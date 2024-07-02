
# Amazon HackOn 2024

## Team Invincibles - Finalist of Amazon HackOn
Team Members 
- Rishav Aich [@Ris-code](https://github.com/Ris-code)
- Ashutosh [@ashuashutosh2211](https://github.com/ashuashutosh2211)
- Saloni Garg

## Problem Statement
Theme 4: Personalized Payment Experiences and Financial Management

- The key problem around payment arena include developing an AI-powered chatbot solution to automate the handling of customer payment queries.
- Creating an automated budgeting solution that allows customers to set purchase amount limits for the year, get notifications when they reach certain thresholds, track their savings on a yearly, monthly, and overall basis, and monitor their spending across different product categories.
- Designing an AI-generated recommendation engine that suggests the best payment method for each customer purchase based on their past payment history, current success rates, available cashbacks, and the costs of different payment options.

## Idea Submission Round
- [Ideation Presentation](https://github.com/Ris-code/Amazon-HackOn/blob/main/Team-Invincibles-prototype.pdf)

- [Ideation Testing Repo](https://github.com/Ris-code/Amazon-HackOn) 

- [Test Prototype Link](https://amazon-hackon-invincibles.streamlit.app/)

## Final Round

### Working Prototype Video

https://github.com/Ris-code/Amazon/assets/95609173/e077763b-0fa2-4e40-838d-a75d6f3ebb76

- [Presentation Link](https://drive.google.com/file/d/1Yctc4ETnXLcaqG7aar8SvhXUaLwMlP-z/view?usp=sharing) 
- [Prototype Link](https://amazon-production-175b.up.railway.app/) 

### ChatBot Model Architecture
![Model Architecture](https://i.postimg.cc/Lsxp1KxM/Screenshot-2024-07-02-184024.png)

We have used `Langchain` to build the chatbot. Basically a Large language model is limited to the
information with which its trained so we need to fine tune it with the external data sources. So
langchain provides the ease to handle multiple tools to fetch the required data to solve payment
queries. We have used `Mistral AI` as our LLM model, used pinecone as the vector database.
The Agent is the one who is controlling which tools to use inorder to satisfy the user needs.

#### Data to train the model
- Frequently asked questions on payment queries for all type of Amazon services like AWS, Amazon Pay, Amazon Shop, Amazon Prime services.
- On the complete user profile of the logged in user.
- Amazon payment policies.
- Customer pain point categorisation
- Fetch data about orders, transaction IDs and other relevant resources from the backend if the user needs it.

### Recommendation Model
![Recommendation Model](https://i.postimg.cc/VvnsMZSB/Screenshot-2024-07-02-184545.png)

- We evaluate all the available offers the cashback and the additional cost implied by the payment method to calculate the final price to be paid by customer. The payment method which provides the least cost gets the first priority.
- But if we get methods with same cost then we use a CNN model where we include two more features: `User payment history` and `Success rate` which is relative measure on how many users have used it over other payment methods for the particular product.

### Financial Management tools
We have used `Chart.js` to plot all the analysis graphs as well as added tools to enhance user experience and increase the business of Amazon.

### Dashboard

#### Spendings and Savings According to Item Category
![spending by category](https://i.postimg.cc/fbqcyC0R/Screenshot-2024-07-02-190202.png)

#### Monthly Spendings and Savings
![monthly spending](https://i.postimg.cc/85V1RQvK/Screenshot-2024-07-02-190727.png)

#### Spendings through each payment method
![payment](https://i.postimg.cc/T20RDs30/Screenshot-2024-07-02-190953.png)

#### Spending Rewards
![reward](https://i.postimg.cc/Bb79wd8G/Screenshot-2024-07-02-191249.png)

`Business Relevance`: Now customers when think about buying anything will first consider Amazon as the option because on spending then are getting exciting prices which also include prime subscription.This will increase the customer traffic on amazon.

## Customer Purchases and Suggestions
![order](https://i.postimg.cc/P5QGgpv4/Screenshot-2024-07-02-192154.png)

`Business Relevance`: Boosts customer engagement with price drops, new versions, and personalized suggestions, increasing purchase likelihood from trusted brands. Recommends complementary products and popular items, enhancing transaction value and managing stock efficiently.

## EMI Management and analysis
![EMI](https://i.postimg.cc/J0ZYjvbq/Screenshot-2024-07-02-192416.png)

`Business Relevance`: People readily opt for multiple EMIs because the Dashboard service manages them efficiently, allowing easy spending and later payments. This boosts Amazon Pay's business, offering the easiest EMI options and the latest deals. The flexible "pay now and change duration" feature lets customers pay as per their needs, driving up sales by making EMIs more reliable.

## Budget Management

### Monthly Spending Limit
![budget](https://i.postimg.cc/Bb9MZpd1/Screenshot-2024-07-02-192700.png)

The green bars show within budget limit whereas the red ones show the limit exceeded.

### Yearly Spending Limit
![budget-year](https://i.postimg.cc/xTbn41Px/Screenshot-2024-07-02-192939.png)

The green bars show within budget limit whereas the red ones show the limit exceeded.

### Warning and Suggestions
![warn](https://i.postimg.cc/zD4VBMtQ/Screenshot-2024-07-02-193235.png)

`Business Relevance`: The budget manager tool helps customers set budget limits and track spending, prioritizing their needs. We highly recommend Amazon Pay for its EMI solutions and exciting offers, ideal for urgent purchases within budget constraints.


## References
- Quickstart: https://python.langchain.com/v0.1/docs/use_cases/chatbots/quickstart/
- Memory Management: https://python.langchain.com/v0.1/docs/use_cases/chatbots/memory_management/
- Retrieval: https://python.langchain.com/v0.1/docs/use_cases/chatbots/retrieval/
- Tool Usage: https://python.langchain.com/v0.1/docs/use_cases/chatbots/tool_usage/
- Conversational RAG: https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/
- Build an Agent: https://python.langchain.com/v0.2/docs/tutorials/agents/
- Q&A over SQL+CSV: https://python.langchain.com/v0.1/docs/use_cases/sql/quickstart/
- Tool Functioning: https://python.langchain.com/v0.1/docs/modules/model_io/chat/function_calling/


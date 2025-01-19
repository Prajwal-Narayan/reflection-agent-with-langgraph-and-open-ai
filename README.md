# Reflection Agent Using Langgraph and Open AI

<img width="947" alt="langgraph tracing" src="https://github.com/user-attachments/assets/370df1b3-33f5-40a2-9ce7-f0cad2380fab" />


# Reflection Agent with LangGraph and OpenAI

This project is an implementation of a **Reflection Agent** using **LangGraph** and **OpenAI**'s models to enhance the quality of tweets. The agent generates and improves tweets iteratively, using a combination of **generation** and **reflection** chains. The model is designed to critique and improve user-submitted tweets in a way that mimics a viral Twitter influencer's style.

## Project Overview

The **Reflection Agent** works by:
1. **Generating a tweet** based on user input, using a predefined generation prompt.
2. **Reflecting** on the generated tweet by offering detailed critique and suggestions for improvement, such as tone, style, and virality.
3. **Iterating** between the generation and reflection phases to refine the tweet until a desired output is achieved.

This project uses the **LangChain** and **LangGraph** libraries for building the chains and managing the workflow. It also integrates **LangSmith's tracing** to monitor and analyze the agent's output and behavior during the refinement process.

### Key Features:
- **Generative Tweet Writing**: Uses a language model to craft tweets based on user requests.
- **Reflection**: Offers detailed critiques and suggestions to improve the generated tweet.
- **Iterative Process**: The system repeats the generation and reflection steps to continuously refine the output.
- **LangSmith Tracing**: Integrated tracing for monitoring and understanding the agent's decision-making process.
- **Environment Configuration**: Uses `.env` files for secure environment management.

## Technologies Used

- **LangChain**: A framework for building language model-powered applications.
- **LangGraph**: A tool for managing workflows of language models, supporting chaining and conditionally progressing through nodes.
- **OpenAI**: Used for the language models responsible for tweet generation and reflection.
- **LangSmith**: Used for tracing and visualizing the model’s execution.
- **Python**: Core language for the project.
- **Dotenv**: Manages environment variables securely.

## Getting Started

To get started with this project, follow the steps below to set up the environment and run the agent.

### Prerequisites

- Python 3.x or higher
- Git
- OpenAI API key
- LangSmith API key
- LangGraph and LangChain libraries

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Prajwal-Narayan/reflection-agent-with-langgraph-and-open-ai.git
   cd reflection-agent-with-langgraph-and-open-ai
   ```

2. **Create a Virtual Environment (Optional but recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up the `.env` File**
   Create a `.env` file in the root of the project and add the following environment variables:
   ```bash
   OPENAI_API_KEY=your_openai_api_key
   LANGSMITH_API_KEY=your_langsmith_api_key
   ```

   You can obtain your **OpenAI API Key** and **LangSmith API Key** by signing up for the respective services.

5. **Run the Project**
   ```bash
   python main.py
   ```

   This will run the agent and allow you to input tweets that you want to improve. The agent will then generate and critique your tweet, iterating over it multiple times.

## How It Works

1. **Main Components**:
    - **generate_chain**: A LangChain chain responsible for generating a tweet based on the user’s input.
    - **reflect_chain**: A LangChain chain responsible for reflecting on the generated tweet, offering critique and suggestions for improvement.
    - **LangGraph**: Manages the workflow of the agent, determining which chain to execute and when to transition between generation and reflection.

2. **Workflow**:
    - The agent begins by taking user input (a tweet or a tweet draft).
    - It enters the **generate_chain** to produce an initial tweet.
    - Then, the agent enters the **reflect_chain**, where the model provides feedback on the generated tweet.
    - This process is repeated iteratively until a satisfactory result is achieved.
    - LangSmith’s tracing is used to monitor the outputs of each iteration for better debugging and optimization.

3. **Conditioned Workflow**:
    - The agent decides whether to continue the generation-reflection loop based on the number of iterations. If the iteration count exceeds 6, the process ends.

4. **LangSmith Integration**:
    - LangSmith is used for tracing the entire execution, helping to visualize each step, debug, and analyze the flow of the agent. The results can be reviewed in the LangSmith dashboard.

## Example Use Case

### Input:
```txt
Make this tweet better:
@LangChainAI — newly Tool Calling feature is seriously underrated. After a long wait, it's here - making the implementation of agents across different models with function calling super easy. Made a video covering their newest blog post.
```

### Output (after refinement):
```txt
🚀 Just tested LangChain's new Tool Calling feature! It’s a game-changer for implementing agents across multiple models. Can't wait to see how it revolutionizes AI development. 🎥 Check out my breakdown of their latest blog post 🔥 @LangChainAI #AI #MachineLearning
```

## Contributing

We welcome contributions to this project! If you’d like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to your branch (`git push origin feature-branch`).
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **LangChain** and **LangGraph** for the powerful tools used to build the workflow.
- **OpenAI** for their amazing language models that power the generation and reflection chains.
- **LangSmith** for providing tracing capabilities that enhance the agent’s debugging and performance analysis.

---

Feel free to explore and improve this agent to suit your needs, and help make the Twitterverse even better!

```


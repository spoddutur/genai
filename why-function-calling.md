# Q) Ever wondered why one of the most popular tools — The Calculator — is essential for Large Language Models (LLMs)? 

While LLMs excel at natural language understanding, coding, and reasoning, they struggle with precise mathematical computations.

### 1. The Math Problem with GPT3 - 175B model:
Below graph from [Language Models are Few-Shot Learners" (Brown et al., 2020)](https://arxiv.org/pdf/2005.14165) research highlights the accuracy drop in arithmetic tasks with GPT3 - 175B model: <br/>
<img align="left" width="300" src="images/gpt3-arithmatic.png" alt="gpt-airthmatic-with-python-tool"/> 
- 2-digit addition/subtraction: 100% accuracy
  
- 3-digit addition/subtraction: 80% accuracy
  
- 4-digit arithmetic: 25% accuracy

- 5-digit arithmetic: 9% accuracy
<br/>

#### Q) Why does this happen? 
This demonstrates that even with scale, LLMs do not inherently develop rule-based mathematical reasoning but instead rely on statistical-patterns from training data.

### 2. Solution: Tell LLM that it has access to Calculator Tool
- Prompt to LLM: "You have a calculator tool to solve Math Problems. Never attempt to solve math problems by yourself. To use calculator, format the output as 'Calculator, Operator, Operand1, Operand2'. For Example, to solve 2+3, please output Calculate, +, 2,3."
- User: Add 4 and 5
- LLM Output: Calculator,+,4,5
- A separate script would then extract this request, execute it in a traditional programming environment, and return the result.

#### Problems: 
- LLMs were inconsistent in formatting responses, making parsing difficult.
- Prompt Injection Attacks: Attackers can manipulate LLM prompts to extract internal tool details or force unintended actions.
- Verbosity of Input and Output: LLMs often generate overly detailed responses when interacting with tools instead of just spitting out tool call.

### 3. Solution: Function Calling
A Framework for connecting llms to real-time data.
<img src="images/function-calling.png" alt="function calling"/>


### 2. The Math Problem with GPT4 model:
<img width="200" src="images/gpt4-arithmatic.png" alt="gpt-airthmatic-with-python-tool"/>




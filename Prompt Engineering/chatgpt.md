# Prompt Engineering

## What is the Prompt :
A Prompt is the instruction or message you write to an AI model.

**👉 The more clear, specific, and structured the prompt is,
the better the output will be.**


## Basics :

### AI models /Assistants : 
This is a general concept that includes different types of AI systems:
```
LLMs (Text)
Image Models (Images)
Speech Models (Audio)
````
Chatgpt , claude ... == AI models / AI Assistants
kan3tiwhom Prompt wkayrjj3o Response 

**👉 These systems:
Receive a Prompt
Return a Response**

Examples of AI Assistants:

1. ChatGPT
2. Claude AI
3. Google Gemini
4. DeepSeek
5. Microsoft Copilot
6. Perplexity AI


### LLMs (Large language model) : 
LLMs are AI models that work with text only.
They can:
```
Understand text
Generate text
Answer questions
```
*LLM = Brain*

### AI agent :
AI Agents are more advanced systems.

They:
```
Use LLMs
Have a Goal
Perform Planning
Execute Actions
Interact with Tools (APIs, files, etc.)
```

*Agent = LLM + Tools + Actions + Autonomy*
**Exemples**
AutoGPT
LangChain Agents

Simple Comparison
```
LLM → Thinks and generates text only
AI Assistant → Chat interface (talks with users)
AI Agent → Thinks + takes actions autonomously
```
image 1 Ai1.png

## Elements of a Professional Prompt : 
*Each prfessionel prompt should include 6 elements*

1. Role : 
The objectif is determine chkhsiyya or howwiyya or khibra for the AI  
Defines the identity or expertise of the AI.

Who Are You !
**Exemples**
```bash
You are a cybersecurity expert
You are a professional teacher
You are a Python developer
# 
You are a senior backend developer with 10 years of experience
in Node.js, REST APIs.
```
💡 Rule: The more specific the Role, the more expert the answer.

*Why is important!!*
Because the AI change the osslob of response for each role that you 3titih lih 

2. Task : 

talab principal -- what you need for the AI to do exactly
the task = verb + objectif targeted
A good Task must contain:

A clear action verb : explain, generate, refactor, debug, review
A specific goal : what exactly you need

**Exemples**
```bash
Explain SQL Injection
Write a lesson plan
Generate a report
#
Explain the concept of networking 
to a group of high school students.
```

3. Content :

The additional information you provide so the AI can perform the Task.
Can be:

- A code snippet to review or fix
- An error log to analyze
- A database schema to work with
- Any context the AI needs to understand your request

**Exemples**
```bash
Here is the function:

function getData(arr) {
  let result = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 10) {
      result.push(arr[i]);
    }
  }
  return result;
}

```
4.Reasoning : 

You instruct the AI to explain its thinking process step by step before giving the final answer.
This technique is called :
Chain of Thought Prompting

**Exemples**
```bash
Before writing the solution, analyze the problem step by step,
identify edge cases, then write the code.
# Another example :

Think step by step:
1. Identify the time complexity of the current solution
2. Suggest a more optimal approach
3. Then write the Refactored code
```

5. Stop Conditions :
fin khas AI yw9f 
Constraints that limit the response.
**Exemples**
```bash
- Limit to 200 words
- Use only vanilla JavaScript, no external libraries
- Do not modify the function signature
- Do not explain concepts I did not ask about
- Stay focused only on the provided code

```

6. Output : 

Determine the format and syntax of response 
**Exemples**
```bash
Return the answer as:
- A numbered list
- A table with 3 columns
- A JSON object
- A paragraph 
# 

Return your answer as:
- A code block with comments
- A JSON object with keys: solution, complexity, explanation
- A markdown table comparing two approaches
- A bullet list of improvements
```

# Full Prompt Template

```bash
ROLE:
You are [specific identity].

TASK:
[Exactly what you want the AI to do].

CONTENT:
[The code / data / text you provide].

REASONING:
Think step by step before writing the solution.

STOP CONDITIONS:
- [Constraint 1]
- [Constraint 2]
- [Constraint 3]

OUTPUT:
Return your answer as [exact format].



```
# Exemple : 

```bash
ROLE:
You are a senior full-stack developer
specialized in React and Node.js.

TASK:
Review the following API endpoint
and identify security vulnerabilities.

CONTENT:
app.post('/login', (req, res) => {
  const { username, password } = req.body;
  const query =
    `SELECT * FROM users
     WHERE username = '${username}'
     AND password = '${password}'`;
  db.query(query, (err, result) => {
    if (result.length > 0) {
      res.send({ token: generateToken(result[0]) });
    } else {
      res.status(401).send('Unauthorized');
    }
  });
});

REASONING:
Analyze the code step by step.
Identify each vulnerability before suggesting fixes.

STOP CONDITIONS:
- Do not rewrite the entire application
- Focus only on security issues
- Do not suggest switching to a different framework

OUTPUT:
Return your answer as:
1. List of vulnerabilities found
2. Explanation of each vulnerability
3. Fixed code with inline comments

```

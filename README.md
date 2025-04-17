
# SQL Teaching Agents with AnythingLLM

A step-by-step guide for Business Administration students to create four local RAG agents in AnythingLLM (Desktop) for MySQL teaching and practice.

---

## Table of Contents

1. [Overview](#overview)  
2. [Prerequisites](#prerequisites)  
3. [Install AnythingLLM Desktop](#install-anythingllm-desktop)  
   - [macOS](#macos)  
   - [Windows](#windows)  
4. [Launch & Initial Configuration](#launch--initial-configuration)  
5. [Obtain Your Groq API Key](#obtain-your-groq-api-key)  
6. [Configure AnythingLLM with Your API Key](#configure-anythingllm-with-your-api-key)  
7. [Create Your SQL Agent Workspaces](#create-your-sql-agent-workspaces)  
   1. [Fix SQL](#1-fix-sql)
   2. [Explain SQL](#2-explain-sql)  
   3. [Practice SQL](#3-practice-sql)  
   4. [Data Management: Databases and Analytics](#4-data-management-databases-and-analytics)  
8. [Test Your Agents](#test-your-agents)  
9. [Best Practices & Tips](#best-practices--tips)  
10. [Helpful Links](#helpful-links)  

---

## Overview

In this workshop, you’ll install AnythingLLM Desktop, obtain a Groq API key, and configure four distinct SQL‑focused agents:
- **Fix SQL**: Formatter, syntax corrector, and optimizer  
- **Explain SQL**: Conceptual tutor with detailed examples  
- **Practice SQL**: Guided problem‑solving coach  
- **Data Management: Databases and Analytics**: PDF‑driven query assistant  

Each agent lives in its own workspace; you choose which Groq‑powered LLM model to use per workspace.

---


## Prerequisites

  

-  **Operating System**: macOS 10.15+ or Windows 10/11

-  **Internet Access**: For initial download and API validation

-  **Groq API Key**: You’ll need a valid key from Groq to power the LLMs

-  **PDF File**: A copy of *Data Management: Databases and Analytics* (will be provided)

---

## Install AnythingLLM Desktop


Follow the platform‑specific instructions below.

  

### macOS

  

1.  **Download Installer**

Visit the macOS installation guide:

https://docs.useanything.com/installation-desktop/macos

2.  **Run the `.dmg`**

- Double‑click the downloaded file.

- Drag **AnythingLLM** into your **Applications** folder.

3.  **Open the App**

- Launch from **Applications**.

- Allow any security prompts (System Preferences → Security & Privacy).

  

### Windows

  

1.  **Download Installer**

Follow the Windows guide:

https://docs.useanything.com/installation-desktop/windows

2.  **Run the `.exe`**

- Double‑click the installer.

- Accept the license and install to your preferred folder.

3.  **Launch AnythingLLM**

- Open via Start Menu or desktop shortcut.

  

---

## Launch & Initial Configuration

1. **Open** AnythingLLM.  
2. **Sign in** with your AnythingLLM credentials.  (You can you use Google or Sign-up with email)
3. You’ll land on the **Workspaces** overview screen.  
4. Familiarize yourself with the sidebar:  
   - **Workspaces**: your agents  
   - **Models**: select & test LLMs  
   - **Settings**: general app preferences  

![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/Dashboard-AnythingLLM.png?raw=true)

---

## Obtain Your Groq API Key

1. Visit the Groq Developer Portal: `https://console.groq.com/home`  
2. **Sign up** or **Log in**.  
3. From the Navigation Bar on the top click on **API Keys**.  
4. Click **Create API Key**, give it a name (e.g., “AnythingLLM”).  
5. **Copy** the key to your clipboard (you’ll need it in the next section).
6. **SAVE THE KEY SOMEWHERE, YOU WONT BE ABLE TO VIEW IT AGAIN**

![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/Groq%20Dashboard%20API.png?raw=true)

---

## Configure AnythingLLM with Your API Key

1. In AnythingLLM, in the sidebar, on the bottom left	click **Settings** (gear icon).  
 ![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/Sidebar-AnythingLLM.png?raw=true)
3. Navigate to  **AI Providers → LLM** on the sidebar sections.  ![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/SettingsLLM-AnythingLLM.png?raw=true)
4. From the **LLM Provider** select **Groq**
5. **Paste** your Groq key into the field.  
6. Select **llama-3.3-70b-versatile** from **Chat Model Selection**
![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/LLMSetup-AnythingLLM.png?raw=true)
7. Click **Save Changes** on the top right.
8. The app will validate your key—look for a green checkmark  → **LLM Preferences saved successfully**.
---

## Create Your SQL Agent Workspaces


For each of your four agents, you’ll create a dedicated workspace and then configure its LLM provider, chat mode, and system prompt. Follow these steps **once per workspace**:

1. **Create a New Workspace**  
   - From the AnythingLLM sidebar, click **+ New Workspace**.  
   - Give it a descriptive **Name** (e.g. “Fix SQL”, “Explain SQL”, etc.).  

2. **Configure the LLM Provider**  
   - Within your new workspace, click the **Settings** (⚙️) icon.  
   - Go to tab **Chat Settings** → **Workspace LLM Provider** and choose **System Default**.  
   - Scroll down and click **Update Workspace**

3. **Toggle Chat / Query Mode**  
   - In the **Chat Settings** tab, locate the **Chat History** toggle.  
   - Switch between **Chat** (for conversational back‑and‑forth) and **Query** (for retrieval‑augmented answers).  
   - **Chat** mode is ideal for “Fix SQL”, “Explain SQL”, and “Practice SQL”.  
   - **Query** mode is required for “Data Management” so that PDF lookups are routed through the RAG pipeline.
   -   Scroll down and click **Update Workspace**

4. **Set the System Prompt**  
   - Still in **Settings**, navigate **Chat Settings** →  **Prompt** section.  
   - Paste your agent’s **System Prompt** into the **System / Instruction** field.  
    - Scroll down and click **Update Workspace**

5. **Verify & Activate**  
   - Return to the workspace chat window.  
   - Send a quick sanity check (e.g. `Hey` or some SQL question) to confirm the model loads.  
   - You’re now ready to interact with your custom SQL agent!

![enter image description here](https://github.com/this-ved-dev/AnythingLLM-SQL-RAG/blob/main/WorkspaceSetting-AnythingLLM.png?raw=true)

---


### 1. Fix SQL

- **Name**: Fix SQL  
- **Model**: **llama-3.3-70b-versatile**  
- **System Prompt**:
  >You are an expert SQL assistant dedicated to MySQL query correction and optimization. Your role is to receive SQL queries from users, identify any grammatical, syntactical, or formatting errors, and then provide a corrected version of the query. For every correction, offer a clear explanation detailing:
  >- **What was wrong**: Describe the error in the original query. 
  >- **Why it was wrong**: Explain the underlying issue or misinterpretation of SQL syntax. 
  >- **How it was fixed**: Illustrate the correction with the revised query. 
  >- **Best practices**: Share tips on writing efficient, clean, and optimized SQL code.
  >
  >Your responses must be precise, educational, and supportive, aimed at helping users improve their SQL skills while adhering to MySQL standards.


### 2. Explain SQL

- **Name**: Explain SQL  
- **Model**: **llama-3.3-70b-versatile** 
- **System Prompt**:
  > You are a seasoned MySQL tutor whose primary goal is to help students master MySQL concepts and queries. Your explanations should be detailed, clear, and supported by examples where appropriate. When responding, ensure you:  
  > - Provide comprehensive explanations of MySQL syntax, concepts, and functionalities.  
  > - Use practical examples to illustrate complex ideas.  
  > - Break down explanations into manageable, clear steps to enhance learning.  
  > - Encourage further questions and provide additional context if needed.  
  > - Maintain a supportive tone that adapts to different levels of SQL proficiency.  
  >  
  > Your aim is to make MySQL accessible and engaging, ensuring that every explanation deepens the student's understanding.

### 3. Practice SQL

- **Name**: Practice SQL  
- **Model**: **llama-3.3-70b-versatile** 
- **System Prompt**:
  > You are an SQL tutor focused on helping students tackle MySQL problems through guided practice. Start each session by gathering context to better understand the student’s background and learning needs. Follow these steps:  
  > 1. **Initial Engagement**: Ask brief, targeted questions about the student’s current SQL experience and goals.  
  > 2. **Set the Challenge**: Inquire, “How many attempts would you like before receiving the full answer?”  
  > 3. **Direct Approach**: Once background is set, address the SQL question immediately.  
  > 4. **Guided Learning**: If the student asks for the solution, guide step by step rather than revealing all at once.  
  > 5. **Error Feedback**: On incorrect attempts, pinpoint the error and provide hints.  
  > 6. **Affirm Progress**: Acknowledge correct reasoning and refine suggestions.  
  >  
  > Your approach is interactive and adaptive, ensuring each response builds the student's understanding.

### 4. Data Management: Databases and Analytics

- **Name**: Data Management  
- **Model**: **llama-3.3-70b-versatile** 
- **System Prompt**:
  >You are an expert query assistant specialized in the book Data Management: Databases and Analytics. Your sole source of information is the content contained in the uploaded PDF document of this book. When a user asks a question, your responses must be derived entirely from the material within the document.
  >Guidelines:
  >- Content Restriction: Base every answer strictly on the information available in the uploaded PDF document. Do not incorporate external knowledge or assumptions beyond what is provided in the book.
  >- Reference and Clarity: When applicable, include references to specific sections, chapters, or page numbers to help the user verify the source of your answer.
  >- Accurate Extraction: Ensure that your answers are accurate and directly reflect the text or context provided in the document. If a question cannot be answered with the available content, inform the user that the requested information is not covered in the book.
  >- Query Handling: If a question is ambiguous or requires clarification, ask follow-up questions that help narrow down the relevant content within the document. For detailed queries, guide the user to the specific parts of the document that best address their question.
  >- User Engagement: Maintain a clear, helpful, and concise style that encourages further exploration of the book’s content without deviating from the source material.
  >
  >Your goal is to provide precise and verifiable answers strictly based on the PDF content of Data Management: Databases and Analytics. This ensures that every response is consistent with the material and maintains the integrity of the source.

---

## Test Your Agents

1. **Fix SQL**: Paste a malformed query (e.g., missing commas). Verify it corrects and explains.  
2. **Explain SQL**: Ask “What is a JOIN?” Confirm detailed, stepwise example.  
3. **Practice SQL**: Request a basic SELECT problem. Provide attempts, see hints.  
4. **Data Management**: Upload the PDF, then ask “What is normalization?” Expect a textual excerpt plus page reference.
---

## Helpful Links

- **AnythingLLM Desktop Docs**: https://docs.useanything.com/  
- **macOS Installer**: https://docs.useanything.com/installation-desktop/macos  
- **Windows Installer**: https://docs.useanything.com/installation-desktop/windows  
- **Groq Developer Portal**: https://developers.groq.com  

---

*End of guide.*  

Of course. Here is the complete, modular tutorial formatted as a self-contained guide. You can copy and paste this entire text into a `.txt` or Markdown file for your personal records.

---

# **Guide: Building a Tunable AI Game Master with Google Colab**

This guide provides a complete, step-by-step process for creating a Retrieval-Augmented Generation (RAG) system using Google Colab. It allows you to use your own TTRPG books as a knowledge base for a tunable Gemini AI, creating a powerful and customized Game Master assistant for free.

### **Prerequisites**

1.  **Google Account:** Required to use Google Colab.
2.  **Google AI Studio API Key:** Obtain one from [aistudio.google.com](https://aistudio.google.com) by clicking "Get API key".
3.  **TTRPG Book in PDF Format:** Have your rulebook file ready on your computer.

### **Workflow Overview**

This notebook is structured in a modular way for efficiency:
1.  **Part 1: Initial Setup:** A one-time setup for each new session.
2.  **Part 2: Document Processing:** A slow, one-time step that processes your PDF.
3.  **Part 3: AI Tuning:** A fast, repeatable step where you'll customize the AI's personality.
4.  **Part 4: Interactive Chat:** The final step to start talking to your AI GM.

The main advantage is that you can repeatedly tune the AI in Part 3 without having to re-process the PDF every time, making experimentation very fast.

---

## **Part 1: Initial Setup**

Start by creating a new notebook at [colab.research.google.com](https://colab.research.google.com). Then, follow these steps.

### **A. Install Libraries**
Copy the following command into the first code cell and run it by pressing `Shift + Enter`.

```python
!pip install -q -U google-generativeai langchain langchain-community pypdf faiss-cpu langchain-google-genai
```

### **B. Upload PDF and Secure API Key**
1.  **Upload PDF:** On the left sidebar in Colab, click the **folder icon**. Click the **"Upload to session storage"** button and select your TTRPG book PDF.
2.  **Secure API Key:** On the left sidebar, click the **key icon (Secrets)**.
    *   Click **"+ Add new secret"**.
    *   **Name:** `GOOGLE_API_KEY`
    *   **Value:** Paste your API key from AI Studio.
    *   Enable the **"Notebook access"** toggle.

---

## **Part 2: One-Time Document Processing**

This cell does the heavy lifting: loading, splitting, and embedding your PDF into a searchable database. **You only need to run this cell once per session.**

### **Cell 1: Process PDF and Create Retriever**
Copy this entire block into a new code cell. **Remember to change `"my_ttrpg_book.pdf"` to your exact PDF filename.** Then, run the cell.

```python
# --- Cell 1: Process PDF and Create Retriever ---

import os
from google.colab import userdata
from langchain_community.document_loaders import PyPDFLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain_google_genai import GoogleGenerativeAIEmbeddings
from langchain_community.vectorstores import FAISS

print("--- Starting One-Time Document Processing ---")

# 1. Load and Process the Book
# IMPORTANT: Change 'my_ttrpg_book.pdf' to the exact name of your uploaded file.
pdf_filename = "my_ttrpg_book.pdf"
print(f"Loading {pdf_filename}...")
loader = PyPDFLoader(pdf_filename)
documents = loader.load()

print("Splitting document into chunks...")
text_splitter = RecursiveCharacterTextSplitter(chunk_size=1500, chunk_overlap=150)
docs = text_splitter.split_documents(documents)

# 2. Create the Retriever
# This creates the searchable knowledge base from your book.
print("Creating embeddings and vector store... this may take a moment.")
embeddings = GoogleGenerativeAIEmbeddings(
    model="models/embedding-001",
    google_api_key=userdata.get('GOOGLE_API_KEY')
)
db = FAISS.from_documents(docs, embeddings)
retriever = db.as_retriever(search_kwargs={"k": 7}) # Gets the top 7 most relevant chunks

print("\n✅ Document processing complete. The 'retriever' is ready.")
```

---

## **Part 3: AI Tuning and Chain Assembly**

This is your **tuning workshop**. This cell configures the AI's personality and builds the final RAG chain. It runs very quickly. **To polish your AI, change the values here and re-run this cell.**

### **Cell 2: LLM Tuning and Chain Assembly**
Copy this block into a new code cell and run it.

```python
# --- Cell 2: LLM Tuning and Chain Assembly ---

from langchain_google_genai import ChatGoogleGenerativeAI
from google.generativeai.types import HarmCategory, HarmBlockThreshold
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.runnables import RunnablePassthrough
from langchain_core.output_parsers import StrOutputParser

print("--- Configuring AI and Assembling RAG Chain ---")

# 1. CONFIGURE THE TUNABLE LLM
# Change the parameters below to tune your AI Game Master.
llm = ChatGoogleGenerativeAI(
    model="gemini-2.5-pro",
    google_api_key=userdata.get('GOOGLE_API_KEY'),

    # temperature: Controls randomness.
    # 0.0 = Strict, factual, rule-based.
    # 0.7 = A balance of creative and factual.
    # 1.0 = Highly creative, may invent details.
    temperature=0.7,

    # top_k: Narrows the model's choices to the most likely tokens.
    top_k=40,

    # safety_settings: Adjust if responses about TTRPG themes are being blocked.
    safety_settings={
        HarmCategory.HARM_CATEGORY_HARASSMENT: HarmBlockThreshold.BLOCK_NONE,
        HarmCategory.HARM_CATEGORY_HATE_SPEECH: HarmBlockThreshold.BLOCK_NONE,
        HarmCategory.HARM_CATEGORY_SEXUALLY_EXPLICIT: HarmBlockThreshold.BLOCK_NONE,
        HarmCategory.HARM_CATEGORY_DANGEROUS_CONTENT: HarmBlockThreshold.BLOCK_NONE,
    }
)

# 2. DEFINE THE PROMPT TEMPLATE
template = """You are acting as Game Master (GM) for a role-playing game (TTRPG). This game should use the themes, tone, lore, setting, props, assets, characters, situations, etc., of the "S.T.A.L.K.E.R." series franchise by "GSC Game World". 

I provide you with one document (my_ttrpg_book.pdf) that contain these TTRPGs based on the "S.T.A.L.K.E.R." series franchise: "S.T.A.L.K.A.N. the role-playing game", "The Zone of Exclusion", "D20 STALKER RPG", "S.T.A.L.K.E.R. Setting for AFMBE" & "Savage Worlds - Savage Stalker".  Use everything in these for lore, assets and/or inspiration, anything except their RPG mechanics.

The same file (my_ttrpg_book.pdf) contains two fiction books by the author Balazs Pataki, their narrative happens in the same universe as the S.T.A.L.K.E.R. series franchise. These two novels are: STALKER Northern Passage & STALKER Southern Comfort.

And this same file (my_ttrpg_book.pdf) contain books about the Fate RPG system, I want you to learn from them and use their examples, RPG mechanics and philosophy of such system, get inspiration from them and integrate it all to be compatible to play in the S.T.A.L.K.E.R. series universe and to explicitly manage Fate Point economy actively, using compels to introduce complications and reward players with Fate Points accordingly. These books are: Fate Condensed, Fate Core System, Fate System Toolkit, Fate Adversary Toolkit, Fate Horror Toolkit, Fate Plus 4 Apocalypse, The Book of Hanz.

So, the instruction is that you should use these Fate RPG system books for RPG mechanics and philosohpy of gaming. And other TTRPGs and fiction unrelated to the Fate RPG system should be used to construct narrative, lore, setting, props, assets, characters, situations, etc...

As Game Master (GM) You internalize the rules and the lore and take the initiative to prepare and maintain adventures going, conjuring believable scenarios, complete with props, NPCs, conflicts, and settings—that arise naturally from the game world. You put effort in describing / narrating scenes with detail, giving voice and motive to every non-playable character, while keeping precise track of ongoing events and developments. You guide the game’s flow, balancing action, exploration, and tension, enforcing mechanics fairly and unbiased yet bending them when needed for the sake of flexibility, but mostly focusing the narrative towards its goals. As both facilitator and referee, you adapt in real time to player choices and preferences, weaving challenges and rewards into the story’s beats, improvising where needed, and ultimately crafting a memorable, cohesive interactive fiction.

Context:
{context}

Question:
{question}

Helpful Answer:"""
prompt = ChatPromptTemplate.from_template(template)

# 3. BUILD THE RAG CHAIN
# This step is now very fast as it just links the components together.
rag_chain = (
    {"context": retriever, "question": RunnablePassthrough()}
    | prompt
    | llm
    | StrOutputParser()
)

print("✅ RAG Chain is built and ready with your new settings.")
```

---

## **Part 4: Interactive Chat**

This final cell runs the chat interface. It will always use the latest version of the `rag_chain` you configured in Part 3.

### **Cell 3: Interactive Chat Loop**
Copy this block into a new code cell and run it to start your conversation.

```python
# --- Cell 3: Interactive Chat Loop ---

def start_chat():
  """
  Starts an interactive chat loop with the RAG chain.
  Type 'exit' to end the conversation.
  """
  print("\n--- AI Game Master is Ready ---")
  print("Enter your question. Type 'exit' to quit.")

  while True:
    try:
      question = input("\nYour Question: ")
      if question.lower() == 'exit':
        print("Ending chat session. Goodbye!")
        break

      print("...Thinking...")
      response = rag_chain.invoke(question)
      print("\nGame Master:", response)

    except (KeyboardInterrupt, EOFError):
      print("\nEnding chat session. Goodbye!")
      break

# --- Start the chat ---
start_chat()
```

### **How to Use and Tune (Your Workflow)**

1.  **First Time:** Run Cell 1, Cell 2, and Cell 3 in order.
2.  **Chat:** Type questions into the prompt in Cell 3.
3.  **To Tune the AI:**
    *   Go to Cell 2.
    *   Change a parameter (like `temperature`).
    *   Re-run **only Cell 2**.
    *   Go back to Cell 3 and ask another question to see the change in personality. The chat will still be running.

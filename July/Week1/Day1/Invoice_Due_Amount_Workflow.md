# Invoice Due Amount Extraction Workflow using Langflow

## Objective

Extract only the **Due Amount** from an invoice PDF using Langflow and a
Groq LLM.

## Workflow Diagram

``` text
Read File
   ↓
Prompt Template
   ↓
Groq LLM
   ↓
Chat Output
```

## Component Details

### 1\. Read File Component

Purpose: - Reads the uploaded invoice PDF. - Extracts the file content
as **Raw Content**.

Configuration: - Input File: `invoicefile.pdf` - Output Type:
`Raw Content`

Connection:

``` text
Read File (Raw Content) → Prompt Template (input)
```

\---

### 2\. Prompt Template Component

Purpose: - Receives the extracted invoice text. - Instructs the LLM to
extract only the invoice due amount.

Prompt Used:

``` text
Answer user's questions based on the document below:

---

{input}

Extract only invoice due amount output as

Due Amount is :
```

Variable Mapping:

Variable   Source

\---

input      Read File → Raw Content

Connection:

``` text
Prompt Template → Groq Input
```

\---

### 3\. Groq Component

Purpose: - Processes the prompt and extracts the due amount.

Configuration:

Property   Value

\---

Model      llama-3.1-8b-instant
Provider   Groq
API Key    Groq API Key

Example Response:

``` text
Due Amount is : ₹7,500
```

\---

### 4\. Chat Output Component

Purpose: - Displays the extracted due amount to the user.

Connection:

``` text
Groq Model Response → Chat Output
```

\---

## End-to-End Flow

``` text
invoicefile.pdf
      ↓
Read File
      ↓
Raw Content
      ↓
Prompt Template
      ↓
Groq (llama-3.1-8b-instant)
      ↓
Chat Output
```

## Expected Result

Input Invoice:

``` text
Total Amount : ₹25,000
Paid Amount  : ₹17,500
Due Amount   : ₹7,500
```

Output:

``` text
Due Amount is : ₹7,500


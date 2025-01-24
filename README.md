## 🤖 Retrieval Augmented Generation (RAG) System with Guardrails

A sophisticated question-answering system powered by Large Language Models (LLMs) with multiple validation checks and guardrails to ensure high-quality, relevant, and appropriate responses.

## ✨ System Overview

![System Flow](/Picture1.png)

The system implements a comprehensive validation pipeline that processes user questions through multiple guardrails before generating responses:

### 🔄 Processing Flow

1. **Question Improvement**: Enhances the original question for better information retrieval
2. **Topic Validation**: Ensures questions are within allowed domains
3. **Context Retrieval**: Fetches relevant information using vector search
4. **Relevancy Check**: Validates retrieved context against the question
5. **Response Generation**: Creates detailed answers using LLMs
6. **Content Moderation**: Ensures responses meet quality and appropriateness standards

## 🛠️ Technical Components

### Core Technologies

- OpenAI GPT-3.5/4.0 for question answering
- Pinecone for vector storage and similarity search
- LangChain for workflow orchestration
- PyPDF2 for document processing
- Asyncio for efficient async operations

### Vector Store Configuration

- Dimension: 1536 (OpenAI embeddings)
- Metric: Dot product
- Index Type: Serverless
- Cloud Provider: AWS

## 🚀 Setup Instructions

### Environment Setup

```bash
pip install -r requirements.txt
```

### API Keys Configuration

Create a `.bashrc` file with:

```bash
export OPENAI_API_KEY='your-key'
export PINECONE_API_KEY='your-key'
export PINECONE_REGION='your-region'
```

## 🔒 Guardrails Implementation

### 1. Topical Guardrail

Validates if questions align with allowed topics:

- Business news topics (Final31)
- Historical events (Final32)
- Custom domains can be configured

### 2. Context Relevancy

Scores context relevance on a scale of 1-10:

- Scores ≤ 3: Insufficient relevance
- Scores > 3: Sufficient for response generation

### 3. Content Moderation

Evaluates response quality and appropriateness:

- Scores ≤ 4: Acceptable content
- Scores > 4: Content requires revision

## 📊 Performance Metrics

The system demonstrates strong performance across various question types:

- High accuracy for on-topic questions
- Effective filtering of off-topic queries
- Robust context validation
- Reliable content moderation

## 💡 Use Cases

Perfect for building knowledge-based Q&A systems in domains like:

- Historical research and analysis
- Business intelligence
- Educational content delivery
- Document analysis
- Custom domain-specific applications

## 🔍 Validation Results

System effectively handles:

- Topic-relevant questions with detailed responses
- Off-topic questions with appropriate rejection
- Context relevancy assessment
- Content moderation and filtering
- Edge cases and complex queries

## ⚙️ Customization

The system can be adapted for different domains by modifying:

- Allowed topics in topical guardrail
- Relevancy scoring thresholds
- Moderation criteria
- Vector store configuration

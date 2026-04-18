RAG Architectures Compared
1. Standard RAG
User query => Query Processing => Retrival => Document selection => Context integration (Tích hợp bối cảnh) => LLM response

2. Corrective RAG
User query => Initial Response => Error Detection => Retrival => Response Correction => Final Response

3. Speculative RAG
User query => Small Model Draft 
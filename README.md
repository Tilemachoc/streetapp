## Welcome to my repository 🤗

### Technologies Used:

- **Web Application**: Built with Django
- **Databases**: Utilized Django ORM
- **AI Integration**: Leveraged OPENAI API for responses
- **Embeddings Model**: Employed the `intfloat/e5-large-v2` HuggingFace 🤗 model

### Guide:

- **Dataset**:
  - The [Original Dataset](https://github.com/Tilemachoc/streetapp/blob/main/data.jsonl) was initially scraped and transformed into TextDataset and VectorDataset [models](https://github.com/Tilemachoc/streetapp/blob/main/web_proj/street/models.py) using [custom commands](https://github.com/Tilemachoc/streetapp/tree/main/web_proj/street/management/commands).

- **Backend**:
  - The backend encompasses various [functions](https://github.com/Tilemachoc/streetapp/blob/main/web_proj/street/utils/functions.py).

- **Architecture**:
  - The architectural concept follows this flow:
    - Incoming message ➔
    - Simplification by retaining only keywords ➔
    - Structuring and vectorization of the simplified incoming message ➔
    - Retrieval of top-k most cosine-similar embeddings from VectorDataset ➔
    - Acquisition of the IDs of these top-k VectorDataset objects, enabling retrieval of corresponding text from TextDataset ➔
    - Feeding the text context to an OPENAI API to obtain responses.

```markdown
# Tutorial: ChatBotSeguroAprimorado

## Introdução

O `ChatBotSeguroAprimorado` é uma classe desenvolvida para interagir com usuários em um contexto de seguros, utilizando um modelo de linguagem da Hugging Face. O bot pode responder perguntas baseadas em documentos PDF carregados, armazenar interações e coletar feedback do usuário.

## Pré-requisitos

Para usar o `ChatBotSeguroAprimorado`, você precisa ter instalado as seguintes bibliotecas:

```bash
pip install langchain_community langchain_text_splitters langchain_core
```

## Estrutura do Código

### 1. Importação de Bibliotecas

O código começa com a importação das bibliotecas necessárias:

```python
import os
import time
from langchain_community.document_loaders import PyPDFLoader
from langchain_community.embeddings.sentence_transformer import SentenceTransformerEmbeddings
from langchain_community.vectorstores import Chroma
from langchain_text_splitters import RecursiveCharacterTextSplitter
from langchain_community.llms import HuggingFaceEndpoint
from langchain.chains import ConversationalRetrievalChain
from langchain.memory import ConversationBufferMemory
from langchain_core.prompts import PromptTemplate
from IPython.display import display, Markdown
```

### 2. Classe `ChatBotSeguroAprimorado`

A classe principal é `ChatBotSeguroAprimorado`. Abaixo está a descrição dos métodos e atributos principais.

#### Atributos

- `caminho_pdfs`: Caminho para os arquivos PDF a serem carregados.
- `repo_id`: ID do modelo de linguagem a ser utilizado.
- `paginas_pdfs`: Lista para armazenar páginas de PDFs carregados.
- `armazenamento_vetorial`: Armazenamento vetorial para busca.
- `llm`: Modelo de linguagem.
- `memoria`: Memória para armazenamento do histórico de interações.
- `historico_interacoes`: Lista de interações com o usuário.
- `total_perguntas`: Contador total de perguntas feitas.
- `respostas_bem_sucedidas`: Contador de respostas válidas.
- `feedback_usuario`: Armazena feedback do usuário.
- `tempo_inicio`: Marca o tempo de início do bot.

#### Métodos

1. **`__init__`**: Inicializa o bot, carrega documentos, cria embeddings e inicializa o modelo de linguagem.
2. **`carregar_documentos`**: Carrega e divide documentos PDF do caminho especificado.
3. **`criar_embeddings`**: Cria embeddings e os armazena em um banco de dados vetorial.
4. **`inicializar_llm`**: Inicializa o modelo de linguagem a partir do ID fornecido.
5. **`obter_resposta`**: Obtém uma resposta para uma pergunta com base nos documentos carregados.
6. **`salvar_resposta`**: Salva a resposta em um arquivo de texto.
7. **`coletar_feedback_usuario`**: Coleta feedback do usuário sobre a resposta fornecida.
8. **`buscar_por_palavra_chave`**: Busca por respostas nos documentos carregados com base em uma palavra-chave.
9. **`limpar_memoria`**: Limpa o histórico da conversa.
10. **`listar_documentos_carregados`**: Lista os documentos que foram carregados.
11. **`contar_palavras_na_resposta`**: Conta o número de palavras na resposta.
12. **`formatar_resposta`**: Formata a resposta para exibição.
13. **`gerar_relatorio_desempenho`**: Gera um relatório de desempenho com estatísticas sobre interações.

### Exemplo de Uso

A seguir, um exemplo de como utilizar a classe:

```python
# Criar uma instância do ChatBot
bot = ChatBotSeguroAprimorado('/kaggle/input/chat-banco', repo_id="google/gemma-1.1-2b-it")

# Fazer uma pergunta ao bot
pergunta = "O que é seguro Santander?"
resposta = bot.obter_resposta(pergunta)

# Exibir a resposta formatada
display(Markdown(bot.formatar_resposta(resposta)))

# Exibir o relatório de desempenho
relatorio = bot.gerar_relatorio_desempenho()
display(Markdown(relatorio))
```

## Conclusão

O `ChatBotSeguroAprimorado` é uma ferramenta poderosa para responder a perguntas em um contexto de seguros, utilizando inteligência artificial. Com suas funcionalidades, como coleta de feedback e geração de relatórios de desempenho, é possível aprimorar continuamente a experiência do usuário.
```

### Como usar este Markdown

- Copie o conteúdo acima e cole em um arquivo com a extensão `.md`.
- Você pode visualizar este arquivo em qualquer editor de Markdown ou usar plataformas como GitHub para visualização.

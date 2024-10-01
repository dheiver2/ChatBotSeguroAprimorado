
# ChatBot Seguro Aprimorado

Um chatbot projetado para fornecer respostas sobre seguros utilizando documentos PDF como fonte de informações. O chatbot usa técnicas de processamento de linguagem natural (NLP) e embeddings para responder perguntas de forma eficaz.

## Índice
- [Visão Geral](#visão-geral)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Uso](#uso)
- [Estrutura do Código](#estrutura-do-código)
- [Geração de Relatórios](#geração-de-relatórios)
- [Contribuições](#contribuições)

## Visão Geral

Este chatbot é capaz de:
- Carregar e processar documentos PDF.
- Criar embeddings a partir do texto contido nos PDFs.
- Responder perguntas de forma conversacional com base no conteúdo dos documentos carregados.
- Fornecer estatísticas sobre seu desempenho, como taxa de sucesso e tempo médio de resposta.

## Tecnologias Utilizadas

- Python
- LangChain
- Sentence Transformers
- Chroma
- IPython

## Instalação

Para executar o chatbot, você precisará ter o Python instalado. Em seguida, instale as dependências necessárias usando pip:

```bash
pip install langchain langchain-community sentence-transformers chroma ipython
```

## Uso

1. Clone este repositório:

```bash
git clone <URL_DO_REPOSITORIO>
cd <DIRETORIO_DO_REPOSITORIO>
```

2. Coloque seus arquivos PDF no diretório `./seus_pdfs`.
3. Execute o script:

```bash
python seu_script.py
```

4. Quando solicitado, digite uma pergunta sobre seguros.

### Exemplo de Pergunta
```python
pergunta_usuario = "Qual é a definição de seguro de vida?"
```

## Estrutura do Código

### 1. Classe `ChatBotSeguroAprimorado`

Esta classe é responsável por toda a lógica do chatbot. Suas principais funcionalidades incluem:

- **`__init__`**: Inicializa o chatbot, carrega documentos, cria embeddings e inicializa o modelo de linguagem.
- **`carregar_documentos`**: Carrega e divide documentos PDF do caminho especificado.
- **`criar_embeddings`**: Cria embeddings e os armazena no Chroma.
- **`inicializar_llm`**: Inicializa o modelo de linguagem com um endpoint da Hugging Face.
- **`obter_resposta`**: Obtém uma resposta para uma pergunta com base nos documentos carregados.
- **`salvar_resposta`**: Salva a resposta em um arquivo de texto.
- **`coletar_feedback_usuario`**: Coleta feedback do usuário sobre a resposta fornecida.
- **`buscar_por_palavra_chave`**: Busca respostas nos documentos carregados por palavra-chave.
- **`limpar_memoria`**: Limpa o histórico de conversa.
- **`listar_documentos_carregados`**: Lista os documentos que foram carregados.
- **`contar_palavras_na_resposta`**: Conta o número de palavras na resposta.
- **`formatar_resposta`**: Formata a resposta para exibição.
- **`gerar_relatorio_desempenho`**: Gera um relatório de desempenho do chatbot.

### 2. Exemplo de Uso

O código na parte inferior do script demonstra como instanciar o chatbot, fazer uma pergunta e exibir a resposta formatada.

```python
if __name__ == "__main__":
    chatbot = ChatBotSeguroAprimorado(caminho_pdfs="./seus_pdfs")
    pergunta_usuario = "Qual é a definição de seguro de vida?"
    resposta = chatbot.obter_resposta(pergunta_usuario)
    resposta_formatada = chatbot.formatar_resposta(resposta)
    display(Markdown(resposta_formatada))
    print(chatbot.gerar_relatorio_desempenho())
```

## Geração de Relatórios

O método `gerar_relatorio_desempenho` fornece informações sobre o desempenho do chatbot, incluindo:
- Total de Perguntas
- Respostas Bem-Sucedidas
- Respostas Incorretas
- Tempo Total
- Taxa de Sucesso e Erro

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

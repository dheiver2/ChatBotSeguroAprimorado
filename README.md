
# Tutorial: Usando o Copiloto Seguro Aprimorado

## Introdução

O `CopilotoSeguroAprimorado` é uma classe desenvolvida para carregar documentos PDF, criar embeddings de texto e responder a perguntas específicas relacionadas a seguros, utilizando técnicas de Processamento de Linguagem Natural (PLN) e Modelos de Linguagem. Este tutorial irá guiá-lo através dos passos necessários para usar esta classe.

## Pré-requisitos

Antes de começar, você precisará ter as seguintes bibliotecas instaladas:

```bash
pip install langchain langchain-community
```

Certifique-se também de que você possui documentos PDF que deseja usar como contexto para o copiloto.

## Estrutura da Classe

A classe `CopilotoSeguroAprimorado` possui as seguintes funcionalidades principais:

- **Carregar Documentos PDF**: Lê e divide os documentos PDF em partes menores.
- **Criar Embeddings**: Gera representações vetoriais dos textos utilizando um modelo de linguagem.
- **Responder Perguntas**: Permite fazer perguntas e fornece respostas baseadas nos documentos carregados.
- **Coletar Feedback**: Armazena o feedback do usuário sobre as respostas dadas.
- **Gerar Relatórios de Desempenho**: Fornece estatísticas sobre o desempenho do copiloto.

## Como Usar

### Passo 1: Importar a Classe

Primeiro, importe a classe `CopilotoSeguroAprimorado` no seu script Python.

```python
from seu_modulo import CopilotoSeguroAprimorado
```

### Passo 2: Criar uma Instância do Copiloto

Crie uma instância do copiloto, especificando o caminho para os documentos PDF.

```python
copiloto = CopilotoSeguroAprimorado(caminho_pdfs="/caminho/para/seus/pdfs")
```

### Passo 3: Fazer uma Pergunta

Utilize o método `obter_resposta` para fazer perguntas ao copiloto. Por exemplo:

```python
resposta = copiloto.obter_resposta("Qual é a cobertura do seguro Bradesco?")
```

### Passo 4: Formatar e Exibir a Resposta

Você pode formatar a resposta usando o método `formatar_resposta`.

```python
print(copiloto.formatar_resposta(resposta))
```

### Passo 5: Coletar Feedback do Usuário

Para coletar feedback sobre a resposta fornecida, utilize o método `coletar_feedback_usuario`:

```python
copiloto.coletar_feedback_usuario("Qual é a cobertura do seguro Bradesco?", "A resposta foi útil.")
```

### Passo 6: Gerar Relatório de Desempenho

Para obter um relatório de desempenho do copiloto, utilize o método `gerar_relatorio_desempenho`:

```python
print(copiloto.gerar_relatorio_desempenho())
```

## Conclusão

O `CopilotoSeguroAprimorado` fornece uma maneira eficaz de interagir com documentos PDF e obter informações relevantes sobre seguros. Você pode expandir suas funcionalidades conforme necessário e integrá-lo a outras aplicações.

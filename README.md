# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar um repositório

Escolha um repositório real que possua testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar o repositório selecionado

Busque o repositório escolhido no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar uma prática de teste

Escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

**Repositório:** https://github.com/b12io/orchestra

**URL TestMiner:** https://andrehora.github.io/testminer/#b12io/orchestra

**Explicação:** 
Bem, no repositório que analisei (Orchestra), o ponto mais relevante, acredito, é a forte presença de `Test Helpers`. São 46 desses arquivos de suporte para 41 arquivos de teste principais e 2 *fixtures* (o que pode ser visto na figura abaixo). Com esse número de arquivos auxiliares superando o número de arquivos de teste em si, entendo que o intuito foi focar em reutilização e abstração (ex.: `init`, `workflow`), o que reduz código duplicado e simplifica a escrita de novos cenários / situações.

<img width="842" height="572" alt="image" src="https://github.com/user-attachments/assets/c878abd1-1b06-4ddb-a39e-0d799fdad41c" />

Ao analisar o gráfico de `Test History`, percebi também que o conjunto de testes cresceu de forma contínua junto com o sistema: na versão `v0.1.0`, haviam 210 arquivos de código-fonte e 12 arquivos de teste; já na versão `v0.2.39`, foi para cerca de 400 arquivos de código-fonte, com 36 testes e 46 *helpers*; por fim, na versão `v1.0.61`, o sistema chegou a 510 arquivos de código-fonte e 41 arquivos de teste. O histórico de testes pode ser visto na próxima figura:

<img width="827" height="457" alt="image" src="https://github.com/user-attachments/assets/18c25e9b-bd7d-4fd1-96bc-5c1366ad8915" />

Um último ponto que achei interessante foi que o projeto combina dependências de Python (como `coverage` para medir cobertura e `moto` para *mocking*) com testes de interface em JavaScript / TypeScript (com `Jest` e `Testing Library`).


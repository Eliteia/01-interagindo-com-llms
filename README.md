# Interagindo com LLMs 🧠
Esse foi o tema do primeiro desafio do curso de Agentes Autônomos ministrado pela organização I2A2.

Cada membro do grupo teve a responsabilidade de realizar essas três atividades com o auxílio de modelos de IA:
* Traduzir textos antigos em latim
* Analisar uma planilha com dados coletados de sensores e descobrir o equipamento defeituoso
* Desenvolver uma reimaginação da popular história da "Chapéuzinho Vermelho"

### Primeiro Exercício - Tradução de Textos Antigos 📜
A atividade proposta disponibiliza dois arquivos para serem baixados e utilizados para tradução. 

O objetivo é pedir para diferentes modelos de IA interpretarem os textos, traduzirem para o português e criarem resumos do que estava escrito no texto original.

Textos em latim:
* [Philosophiae Naturalis](https://github.com/Eliteia/01-interagindo-com-llms/blob/main/assets/Base%20Text%20I.txt)
* [Passagens Bíblicas em Latim](https://github.com/Eliteia/01-interagindo-com-llms/blob/main/assets/Base%20Text%20II.txt)

Principais modelos utilizados:
* ChatGPT 4.0
* Claude 3.7 Sonnet
* Grok 3
* Gemini

Para essa atividade, um modelo de prompt adequado pode ser:
```
Realize a análise do documento anexado e faça um resumo traduzido para o português brasileiro do texto,
crie um arquivo de texto com o nome [seu modelo LLM]-resumo-[nome arquivo] e adicione o resumo dentro.
Mantenha o mesmo sentido apresentado no texto original. Tente descobrir o autor e insira ao final do texto.

```
Ainda, se aproveitando da fantasia computacional dos modelos:
```
Você é um tradutor especializado em textos em latim. Realize a análise a partir do documento anexado e faça
a tradução completa do texto para o português brasileiro.
Certifique-se de manter o mesmo sentido apresentado no texto original.
Tente descobrir o autor e adicioná-lo no final do texto.

```
Antes de verificar os resultados, algumas considerações são tomadas:
* Cada prompt é utilizado em um novo "chat" para evitar que o modelo gaste recursos analisando a conversa inteira
* Os testes são realizados até duas vezes por modelo para corrigir possíveis falhas de interpretação

![Captura de tela de 2025-05-06 21-38-00](https://github.com/user-attachments/assets/f1ae7b74-41b5-4d64-89a5-c7ea02ca7f69)


Como resultado desses prompts, os diversos modelos retornaram o resumo corretamente, mas com os seguintes adendos:

1. **Claude 3.7 Sonnet**:
Resumiu o texto em cinco parágrafos, colocando tudo em um artefato (funcionalidade do modelo para criação de blocos de código).
Todo o conteúdo descrito no texto foi explicado corretamente no resumo, utilizando linguagem formal. Além da criação do artefato, ainda escreveu uma explicação do que foi resumido, possuindo um bloco de contexto notavelmente maior do que os demais. Porém, não teve a possibilidade de criar um arquivo com o conteúdo.
Em outro teste, conseguiu traduzir o texto completamente e adicioná-lo em um artefato.

3. **GPT 4.0**:
Criou um arquivo de texto com o resumo em cinco parágrafos, usando menos linguagem complexa e resumindo mais do texto. Ao final oferece a possibilidade de criar o arquivo em PDF também, trazendo continuidade para a conversa.
Como segundo teste, foi demandado que traduzisse o texto completamente, porém retornou apenas resumos do texto.

5. **Grok 3**:
Criou um arquivo de texto com o resumo em um grande parágrafo, explicando com linguagem formal o que foi apresentado. Também escreveu uma análise do resumo após a criação do arquivo. Observa-se que possui menos funcionalidades de formatação de texto para aumentar a legibilidade.
Passou no teste de tradução completa do texto.

7. **Gemini 2.0**:
Realizou o resumo do texto corretamente e criou um arquivo de texto após habilitar a função "Canvas", possui a integração com o Google Drive trazendo facilidades para exportar o arquivo.
Também passou no teste de tradução completa do texto.


### Segundo Exercício - Análise de Equipamento Defeituoso 🔢
A análise de uma planilha contendo oito equipamentos (V1-V8) e dezessete sensores foi realizada nesse exercício.

Para concluir essa atividade era necessário que os modelos descobrissem qual equipamento estava com defeito, utilizando como base os dados da planilha e aplicando funções estatísticas apropriadas.

Planilha utilizada:
* [Defective Equipment](https://github.com/Eliteia/01-interagindo-com-llms/blob/main/assets/Defective_Equipment%20v2025-04-23.xlsx)

Principais modelos testados:
* Claude 3.7 Sonnet
* DeepSeek R1
* GPT 4
* Copilot

Modelo de prompt utilizado para a atividade:
```
Faça uma análise estatística da planilha anexada e identifique qual é o equipamento defeituoso, levando em consideração que são 8 colunas de equipamentos e 17 linhas de sensores, a primeira linha e coluna são identificadores da planilha então desconsidere no cálculo.
Para identificar o equipamento com defeito, faça o uso de funções estatísticas aplicadas nas colunas. Lembre-se que apenas um dos equipamentos possui defeito.
Explique como identificar o erro após a análise. 
```

**Resultado**:

Cada modelo se divergiu nos resultados e valores estatísticos, no entanto os resultados mais proeminentes estavam entre os equipamentos **V2 e V8**.

Após uma análise sobre os valores retornados, foi decidido que o equipamento V2 era o mais provável de se estar com defeito, pois possuia valores maiores do que o anterior. Além disso, vários dos modelos indicaram este equipamento.

A seguir um gráfico, com dados próximos em até 95% da realidade, gerado pelo Claude 3.7: [gráfico de análise estatística](https://claude.ai/public/artifacts/3d856a5b-8011-4050-bd0f-0354dfe77c08)

Outros gráficos gerados pelo ChatGPT na análise da atividade:

* Boxplot para análise de outliers (valores extremos).
![grafico_boxplot_equipamentos](https://github.com/user-attachments/assets/0c73e5e4-6d23-41d5-bc1d-379a7d06ab39)

* Gráfico de barras para análise de variabilidade (anomalias em padrões de dados)
![coeficiente_variacao_equipamentos](https://github.com/user-attachments/assets/a4426d33-c3d6-4e85-a244-e85909be3554)


### Terceiro Exercício - Reimaginando uma História Infantil 📖
Nesta atividade, o exercício é dado para criar uma nova história do conto popular da Chapéuzinho Vermelho, utilizando um tom jornalístico na história.

Cada historia está disponível [aqui](https://github.com/Eliteia/01-interagindo-com-llms/tree/main/assets/historias).

Os principais modelos utilizados para o roteiro:
* ChatGPT 4
* Grok 3
* Gemini 2.0

Modelos para geração de imagens:
* ChatGPT 4 (Dall-e)

Prompt para auxiliar na criação do roteiro:
```
Escreva um prompt adequado para gerar uma nova história da Chapeúzinho Vermelho, de modo que
esteja em um formato jornalístico e profissional, como uma notícia contada.
Coloque ideias de finais para essa reimaginação da história
```

A seguir exemplos das historias geradas com os modelos:

![Captura de tela de 2025-05-06 22-26-35](https://github.com/user-attachments/assets/4bd777a3-847f-409b-8d65-14945acbb05e)


![Captura de tela de 2025-05-06 22-27-31](https://github.com/user-attachments/assets/2eb7c647-2b8b-45dd-a2a9-ba6c79172cd4)


![Captura de tela de 2025-05-06 22-25-32](https://github.com/user-attachments/assets/51babe06-acb2-4062-a339-d9b3b98f4f0c)


![Captura de tela de 2025-05-06 22-27-05](https://github.com/user-attachments/assets/6bdc61c4-dbb5-430e-8ca3-347d7e80d710)


![Captura de tela de 2025-05-06 22-25-59](https://github.com/user-attachments/assets/3d35abb7-2b9e-48d0-a8f6-f053b9aa5ccf)


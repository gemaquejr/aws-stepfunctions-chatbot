# AWS Step Functions: Gerenciamento de Fluxo de Conversação (Chatbot)

Projeto implementado utilizando AWS Step Functions para gerenciar o fluxo de conversação de um chatbot. O fluxo envolve a interação com DynamoDB para obter mensagens, atualizar o histórico de conversação e invocar um modelo de IA para processar respostas.

## Descrição

O workflow gerencia a lógica de conversação por meio dos seguintes passos principais:

1. **Seed DynamoDB Table**: Inicializa a tabela do DynamoDB.
2. **Initialize Conversation History**: Inicializa o histórico da conversa.
3. **For Loop Condition**: Verifica se a conversação foi concluída.
4. **Read Next Message from DynamoDB**: Lê a próxima mensagem da tabela do DynamoDB.
5. **Update Conversation History with Message**: Atualiza o histórico de conversação com a nova mensagem.
6. **Invoke Model with Message**: Invoca um modelo de IA (por exemplo, Bedrock) para processar a mensagem.
7. **Update Conversation History with Response**: Atualiza o histórico com a resposta do modelo.
8. **Truncate Conversation History**: Trunca o histórico de conversação após o processamento.
9. **Pop Element from List**: Remove um elemento da lista de mensagens.
10. **Succeed**: Conclui o fluxo.

## 🚀 Tecnologia

- ⚡ DynamoDB: Utilizado para armazenar e recuperar mensagens da conversa.

- ⚡ Lambda Functions: Funções Lambda são invocadas em várias etapas do fluxo para manipulação de dados e processamento.

- ⚡ Bedrock Model: Um modelo de IA é invocado para gerar respostas com base nas mensagens recebidas.

## ✋🏻 Pré-requisitos

- Conta AWS com permissões adequadas para acessar o AWS Step Functions, Lambda, DynamoDB e Bedrock.

- Funções Lambda configuradas adequadamente para truncar o histórico e realizar outras operações necessárias.

## :hammer_and_wrench: Antes de iniciar o projeto.

### Configuração Inicial:

- Crie uma tabela no DynamoDB chamada ConversationTable com o campo id como chave primária.

- Configure as funções Lambda e o modelo Bedrock conforme necessário.

### Deploy do Workflow:

- Importe o fluxo de trabalho JSON para o AWS Step Functions.

- Inicie o fluxo de trabalho via console da AWS ou usando AWS SDKs.

### Monitoramento e Logs:

- Acompanhe a execução do fluxo de trabalho e os logs das funções Lambda para debugar e melhorar o desempenho.

<h2 align="left">
  <img src="assets/logo_sant.png" width="40" style="vertical-align: middle; margin-right: 10px;">
   Tarefas automatizadas com Lambda Function e S3
</h2>


A integração entre o **AWS Lambda** e o **Amazon S3** permite automatizar tarefas e processar dados de forma *serverless* — ou seja, sem precisar gerenciar servidores.  
Uma **função Lambda** pode ser acionada automaticamente por eventos no **S3**, como o upload, exclusão ou modificação de um arquivo, para executar um código e realizar ações automatizadas.

---

## ⚙️ Como Funciona

 **Evento no S3:** Um evento ocorre em um bucket, como o upload de um novo arquivo.  
 **Notificação de evento:** O S3 envia uma notificação do evento para o AWS Lambda.  
 **Execução da função:** O Lambda é acionado automaticamente e executa o código em uma linguagem como **Python** ou **Node.js**.  
 **Processamento:** A função acessa o arquivo recém-adicionado, processa-o e realiza a tarefa programada.  
 **Resultado:** Pode gerar um novo arquivo, salvar dados em outro serviço da AWS (como o **DynamoDB**) ou enviar uma notificação.

---

## 💡 Exemplos Práticos de Automação

🖼️ **Processamento de imagens:** Criar miniaturas, adicionar marcas d’água ou redimensionar imagens automaticamente.  
📊 **Transformação de dados:** Processar e transformar arquivos (como CSV) e salvar os resultados no S3 ou em um banco de dados.  
🎬 **Transcodificação de vídeo:** Converter vídeos para diferentes formatos após o upload.  
🔍 **Indexação de arquivos:** Extrair metadados ou conteúdo de documentos (PDF, TXT) e indexar em um serviço de busca.  
💾 **Backups automáticos:** Criar cópias de segurança ou arquivar arquivos automaticamente quando novos dados forem enviados ao S3.

---

## 🧩 Passo a Passo para Criar uma Automação

### 1️⃣ Crie um bucket S3
Acesse o console da **AWS**, crie um novo bucket S3 e defina um nome para armazenar os arquivos que irão acionar a automação.

### 2️⃣ Crie a função Lambda
No console do **AWS Lambda**, crie uma nova função, selecione o tempo de execução (por exemplo, `Python 3.12`) e defina um nome.

### 3️⃣ Adicione um gatilho do S3
Na página da função Lambda:
- Clique em **Add Trigger (Adicionar gatilho)**.  
- Escolha **Amazon S3**.  
- Selecione o bucket criado e o tipo de evento (por exemplo, `ObjectCreated (All)` para qualquer novo upload).

### 4️⃣ Conceda as permissões necessárias
Verifique se o **IAM Role** associado à função Lambda possui permissão para acessar o S3.

### 2️⃣ Desenvolva o código da função
Escreva o código que será executado ao ser acionado pelo evento.

### 2️⃣ Teste a automação
Envie um arquivo para o bucket S3 configurado.
Acesse o CloudWatch Logs para verificar a execução e o resultado da função Lambda.

---

## 💬 Conclusão

Com o AWS Lambda e o Amazon S3, é possível construir fluxos automáticos e escaláveis de processamento de dados, economizando tempo e recursos, sem precisar gerenciar infraestrutura.


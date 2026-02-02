# Buscando Produtos Odata é convertendo em CSV e Enviando no Email Anexo
SAP BTP CPI - Send Email Attachement

## Buscando OData e enviando com Anexo no E-Mail

Este iFlow foi desenvolvido no SAP BTP – Integration Suite (Cloud Integration) com o objetivo de extrair dados de produtos a partir de um serviço OData, converter essas informações para o formato CSV e enviar o arquivo como anexo por e-mail de forma automática.

Esse cenário é muito comum em integrações onde é necessário distribuir dados para áreas de negócio, auditoria, relatórios ou integrações legadas que consomem arquivos CSV.

![Capa](imagens/capa-linkedin.png)


📊 Exemplo Prático do Fluxo

### Acessando o E-mail no GMAIL
https://myaccount.google.com/apppasswords
![Fluxo](imagens/Screenshot_1.png)

### APP menos Seguro no GMAIL
![Fluxo](imagens/Screenshot_2.png)

### Armazenando a senha do APP
![Fluxo](imagens/Screenshot_3.png)

### Criando nosso Manage Security
Em Monitor -> Integrations and APIs -> Vamos em Security Material
![Fluxo](imagens/Screenshot_4.png)

### Criar nossas credenciais
![Fluxo](imagens/Screenshot_5.png)

### Criando nosso usuários
![Fluxo](imagens/Screenshot_6.png)

### Testando nossas credenciais no GMAIL
Podemos testar nossas configurações em Em Monitor -> Integrations and APIs -> Vamos em Security Material -> Connectivity Tests
![Fluxo](imagens/Screenshot_7.png)

### Testando o Gmail
![Fluxo](imagens/Screenshot_8.png)

### Criando nosso Pacote
![Fluxo](imagens/Screenshot_9.png)

### Adicionando o nome para nosso Pacote
![Fluxo](imagens/Screenshot_10.png)

### Criando nosso Artefato do iFlow
![Fluxo](imagens/Screenshot_11.png)

### Adicionando o Integration Flow
![Fluxo](imagens/Screenshot_12.png)

### Editando nosso Iflow
![Fluxo](imagens/Screenshot_13.png)

### Removendo o Start
Não vamos precisar do Start nesse momento, vamos adicionar o Timer mais para frente.
![Fluxo](imagens/Screenshot_14.png)

### Adicionadno um Timer
https://services.odata.org/V2/
![Fluxo](imagens/Screenshot_15.png)

### Conectar o Timer no End
![Fluxo](imagens/Screenshot_16.png)

### Renomeando o Receiver para OData
![Fluxo](imagens/Screenshot_17.png)

### Adicionando o Request Replay
![Fluxo](imagens/Screenshot_18.png)

### Conectando o Request Replay no Receiver OData
![Fluxo](imagens/Screenshot_19.png)

### Selecionando o OData
![Fluxo](imagens/Screenshot_20.png)

### Selecionando o OData V2 
![Fluxo](imagens/Screenshot_21.png)

### Acessando a página do OData para (Ler-Escrever)
https://services.odata.org/V2

![Fluxo](imagens/Screenshot_22.png)

### Usuário criado do OData V2
![Fluxo](imagens/Screenshot_23.png)

### Configurando o OData V2 - Conection
![Fluxo](imagens/Screenshot_24.png)

### Configurando o OData V2 - Processing
![Fluxo](imagens/Screenshot_25.png)

### Conectando Sistema do OData V2
![Fluxo](imagens/Screenshot_26.png)

### Configurando o e Definindo Operações do OData V2
Selecionamos o GET
![Fluxo](imagens/Screenshot_27.png)

### Selecionando o Products 
![Fluxo](imagens/Screenshot_28.png)

### Marcando para gerar o XML Schema e todos Fields
![Fluxo](imagens/Screenshot_29.png)

### No Conector vamos adicinar o XML para CSV
![Fluxo](imagens/Screenshot_30.png)

### Transformar o XML para CSV
![Fluxo](imagens/Screenshot_31.png)

### Renomeando o XML to CSV Converter
![Fluxo](imagens/Screenshot_32.png)

### Definindo o caminho que vai ser convertido no XML para CSV
![Fluxo](imagens/Screenshot_33.png)

### Como indentificar o Path no XML
![Fluxo](imagens/Screenshot_46.png)

### Removendo o Sender
Não vamos utilizar ele nesse exemplo
![Fluxo](imagens/Screenshot_34.png)

### Criando um novo Receiver
![Fluxo](imagens/Screenshot_35.png)

## Renomeando o Receiver para EMAIL_GMAIL
![Fluxo](imagens/Screenshot_36.png)

### Conectando o End para EMAIL_GMAIL
![Fluxo](imagens/Screenshot_37.png)

### Selecionando Mail
![Fluxo](imagens/Screenshot_38.png)

### Configurando o E-Mail em Connection
![Fluxo](imagens/Screenshot_39.png)

### Configurando o E-Mail em Processing
![Fluxo](imagens/Screenshot_40.png)

### Configurando nosso Anexos
**Subject:** Dados do Produtos em Anexo

**Mail Body:**
```
Prezados(as), Tudo bem!

Segue anexo dados do Produtos

${in.body}

Atenciosamente,
SAP CPI
```
![Fluxo](imagens/Screenshot_41.png)

### Configurando nosso Anexos
**Name:** Produtos_${date:now:yyyy-MM-dd}T00:00:00.000.csv

**Mime-Type:** Text/CSV

**Source:** Body

![Fluxo](imagens/Screenshot_42.png)

### E-mail Recebido com o Anexo
![Fluxo](imagens/Screenshot_43.png)

### Verificando o corpo do E-mail e o Anexos
![Fluxo](imagens/Screenshot_44.png)

### Verificando Anexos do E-mail
![Fluxo](imagens/Screenshot_45.png)


## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – Package/OdataIntegrationSendEmailAttachment.zip](Package/OdataIntegrationSendEmailAttachment.zip)



> O arquivo pode ser importado diretamente no SAP Integration Suite (CPI).

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

### Criando nosso Security Material em User Credentials
![Fluxo](imagens/Screenshot_32.png)

### Adicionando nossas credencial do FTP
![Fluxo](imagens/Screenshot_33.png)

### Verificando nossas credencial do FTP
![Fluxo](imagens/Screenshot_34.png)

### Vamos voltar ao nosso Iflow
E clicar em Transformation - Converter - Converter XML to CSV
![Fluxo](imagens/Screenshot_35.png)

##Converter XML to CSV (Conversor XML para CSV) Esta etapa realiza a transformação dos dados.
Como funciona: Ela pega o conteúdo XML recebido da etapa anterior e o converte para o formato CSV, que é mais simples e amplamente usado por sistemas de planilhas e bancos de dados. Aqui, você provavelmente mapeia quais campos do XML (como ProductID, Name, Price) se tornam as colunas do CSV.
![Fluxo](imagens/Screenshot_36.png)

### Altearando o nome XML to CSP Converter
![Fluxo](imagens/Screenshot_37.png)

### Salvar e Públicar nosso iFlow
Esta etapa é responsável por carregar os dados processados no destino.
Ela leva o arquivo DetalhesProdutos.csv gerado e o envia (upload) para o servidor FTP remoto, na pasta especificada por você.
![Fluxo](imagens/Screenshot_38.png)

### Acessando o Client de FTP com nossas credencial do FTP.
No nosso exemplo estamos usando o WinSCP
![Fluxo](imagens/Screenshot_39.png)

### Verificando se o arquivo foi adicionado ao FTP
![Fluxo](imagens/Screenshot_40.png)

### Abrindo nosso arquivo gerado
![Fluxo](imagens/Screenshot_41.png)


## 📦 Exemplo prático – iFlow para baixar

📦 [Download do iFlow – Package/ODataIntegrationwithFTP.zip](Package/OData%20Integration%20with%20FTP.zip)



> O arquivo pode ser importado diretamente no SAP Integration Suite (CPI).

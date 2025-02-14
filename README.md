# 📚 Monitoramento de Publicações Acadêmicas e Notícias

Este projeto coleta publicações acadêmicas do **Google Scholar** e notícias do **Google News** utilizando a **API Serper**. Ele permite **baixar PDFs de artigos científicos** e **buscar notícias relacionadas à LGPD e ANPD**.

## 📌 Funcionalidades

✅ **Busca de artigos acadêmicos no Google Scholar**  
✅ **Download automático de PDFs disponíveis**  
✅ **Monitoramento de notícias relacionadas à LGPD e ANPD**  
✅ **Armazenamento dos dados para análise futura**  

---

## 🛠 Tecnologias Utilizadas

- **Linguagem:** R  
- **Pacotes:** `httr`, `jsonlite`, `dplyr`, `RCurl`  
- **Fonte de Dados:** [Serper API](https://serper.dev/) - API para Google Scholar e Google News  

---

## 📂 Estrutura do Código

```
📁 /  (Diretório Raiz)
├── 01_scholar_download_pdf.R  # Busca e download de artigos do Google Scholar
├── 02_news.R                  # Coleta de notícias do Google News
└── downloads/                 # Pasta onde os PDFs são armazenados
```

---

## 🚀 Como Executar

### 1️⃣ **Instalar os pacotes necessários**

Se ainda não estiverem instalados, execute no R:

```r
install.packages(c("httr", "jsonlite", "dplyr", "RCurl"))
```

### 2️⃣ **Configurar a API Key do Serper**

No arquivo `01_scholar_download_pdf.R` e `02_news.R`, edite a variável `X-API-KEY` e insira sua chave:

```r
headers <- c(
  'X-API-KEY' = 'SUA_CHAVE_API',
  'Content-Type' = 'application/json'
)
```

### 3️⃣ **Executar a Coleta de Publicações Acadêmicas**

```r
source("01_scholar_download_pdf.R")
```

Os PDFs dos artigos disponíveis serão baixados na pasta `downloads/`.

### 4️⃣ **Executar a Coleta de Notícias**

```r
source("02_news.R")
```

Os resultados serão exibidos no console e armazenados para análise.

---

## 📊 Estrutura do Arquivo de Saída (`downloads/` e `news_data.csv`)

A saída incluirá:

- **Artigos Acadêmicos:** PDFs baixados no diretório `downloads/`.
- **Notícias:** Um CSV contendo as notícias coletadas, com colunas:

| Título | Link | Fonte | Data Publicação |
|--------|------|-------|----------------|
| Título da Notícia | URL da Notícia | Nome da Fonte | Data `YYYY-MM-DD` |

---

## 🛑 Possíveis Problemas e Soluções

### ⚠️ **Erro na API SerperAPI**  
Se a API não retornar resultados, verifique se sua **chave de API está correta** e se **atingiu o limite de requisições**.

### 🔄 **Erro ao baixar PDFs**  
Nem todos os links do **Google Scholar** fornecem acesso direto ao PDF. O código verifica se a URL termina em `.pdf` antes de tentar o download.

---

## 👨‍💻 Autor

👤 **José Tenório Abs Junior**  
📧 [Seu Email]  
🏛 **IBPAD - Instituto Brasileiro de Pesquisa e Análise de Dados**  

🚀 **Agora você pode monitorar publicações acadêmicas e notícias automaticamente!** Qualquer dúvida, me avise! 😊

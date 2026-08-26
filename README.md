# 🤖 BStech Caption Agent — Automação com n8n, Python e IA

Agente de automação que gera legendas de Instagram para produtos/serviços da BStech, usando IA generativa (Google Gemini), com notificação automática por e-mail.

## 🎯 Problema

Criar legendas de Instagram para cada novo produto manualmente é repetitivo: é preciso seguir sempre o mesmo padrão (título, descrição, características, preço, forma de pagamento, hashtags). Este projeto automatiza esse processo do início ao fim.

## 🧭 Como funciona

1. **Trigger** — uma nova linha é adicionada numa planilha do Google Sheets com os dados do produto (nome, preço, categoria, características).
2. **Python (Code node)** — organiza e limpa os dados recebidos.
3. **IA (Google Gemini)** — gera a legenda seguindo o padrão definido da empresa.
4. **Python (Code node)** — valida o texto (tamanho, hashtags obrigatórias, formatação).
5. **Gmail** — envia a legenda pronta automaticamente por e-mail.
6. **Google Sheets** — marca o produto como processado.

## 🛠️ Stack

| Camada | Ferramenta |
|---|---|
| Orquestração | [n8n](https://n8n.io) |
| Lógica / validação | Python |
| Geração de texto | Google Gemini API |
| Banco de dados | Google Sheets |
| Notificação | Gmail |

## 📂 Estrutura do repositório

# 🤖 BStech Caption Agent — Automação com n8n, Python e IA

Agente de automação que gera legendas de Instagram para produtos/serviços da BStech, usando IA generativa (Google Gemini), com notificação automática por e-mail.

## 🎯 Problema

Criar legendas de Instagram para cada novo produto manualmente é repetitivo: é preciso seguir sempre o mesmo padrão (título, descrição, características, preço, forma de pagamento, hashtags). Este projeto automatiza esse processo do início ao fim.

## 🧭 Como funciona

1. **Trigger** — uma nova linha é adicionada numa planilha do Google Sheets com os dados do produto (nome, preço, categoria, características).
2. **Python (Code node)** — organiza e limpa os dados recebidos.
3. **IA (Google Gemini)** — gera a legenda seguindo o padrão definido da empresa.
4. **Python (Code node)** — valida o texto (tamanho, hashtags obrigatórias, formatação).
5. **HTTP Request** — cria o container de mídia no Instagram (imagem + legenda).
6. **HTTP Request** — publica o container criado, tornando o post público.
7. **Gmail** — envia a legenda pronta automaticamente por e-mail, como confirmação.
8. **Google Sheets** — marca o produto como processado.

## 🛠️ Stack
| Camada | Ferramenta |
|---|---|
| Orquestração | [n8n](https://n8n.io) |
| Lógica / validação | Python |
| Geração de texto | Google Gemini API |
| Banco de dados | Google Sheets |
| Publicação | Meta Graph API (Instagram) |
| Notificação | Gmail |

## 📂 Estrutura do repositório

## ▶️ Como rodar

1. Clone este repositório.
2. Importe o arquivo `workflow/caption-agent.json` no seu n8n.
3. Configure suas próprias credenciais (Google Sheets, Google Gemini, Gmail).
4. Crie um app no [Meta for Developers](https://developers.facebook.com) e gere seu próprio token de acesso do Instagram, substituindo `SEU_TOKEN_AQUI` nos nós de HTTP Request.
5. Ajuste a referência da planilha para a sua própria.
6. Publique o workflow e adicione um produto na planilha para testar.

## 🚧 Próximos passos

- Fluxo de aprovação antes da publicação (revisar a legenda antes de ir ao ar)
- Vincular a imagem de cada produto dinamicamente (hoje usa uma imagem fixa de teste)
- Trocar o token de acesso de curta duração por um token de longa duração

## 📄 Licença

Este projeto é livre para uso e estudo (MIT License).

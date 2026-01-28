# 🚗 AutoVIP - Assistente de Vendas com IA (WhatsApp)

Projeto desenvolvido como Teste Técnico. Trata-se de um sistema de automação de vendas de veículos utilizando **n8n**, **Google Gemini (IA)** e **WhatsApp (Z-API)**.

## 🛠️ Tecnologias Utilizadas
- **n8n:** Orquestração dos fluxos de trabalho.
- **Google Gemini 1.5 Flash:** Cérebro da IA para negociação e persuasão.
- **Z-API:** Gateway para envio e recebimento de mensagens no WhatsApp.
- **Google Sheets:** "Banco de dados" para CRM e controle de estoque.
- **Gmail SMTP:** Notificações de leads quentes para a equipe de vendas.

## 🧠 Arquitetura da Solução

O projeto foi modularizado em 4 workflows principais para garantir escalabilidade e manutenção (Princípio SOLID):

1. **Main:** O "Guarda de Trânsito". Recebe o Webhook, identifica o cliente e decide para qual sub-fluxo enviar.
2. **VendaIA:** O núcleo de inteligência. Utiliza um Agente de IA com *Structured Output Parser* para conversar, negociar e decidir o próximo passo (Agendar Test Drive ou Passar para Humano).
3. **AgendaTestDrive:** Fluxo específico para capturar dados de agendamento.
4. **Atendimento:** Fluxo de transbordo (Handover). Bloqueia o robô e notifica a equipe humana via e-mail.

## 🚀 Como Rodar o Projeto

### Pré-requisitos
Você precisará de uma instância do n8n (local ou cloud) e das seguintes credenciais:
- Google Gemini API Key
- Z-API Instance ID & Token
- Google Service Account (para Sheets)

### Instalação
1. Clone este repositório.
2. No n8n, vá em **Menu > Import from File**.
3. Importe os arquivos da pasta `/workflows`.
4. Configure as credenciais nos nós indicados.

---
*Projeto desenvolvido para Teste Técnico*
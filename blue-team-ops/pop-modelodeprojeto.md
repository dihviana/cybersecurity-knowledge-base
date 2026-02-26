# 🛡️ Procedimento Operacional Padrão (POP)
## Auditoria de Segurança Externa e Reconhecimento

Este documento estabelece a metodologia de **Reconhecimento Passivo** baseada no framework **CIS Controls v8**.

---

### 1. Preparação do Ambiente (Docker)
Para cada cliente, iniciamos um container isolado para garantir a segregação de dados.

```bash
# Criar diretório e subir container
mkdir -p ~/auditorias/projeto-exemplo
sudo docker run -it --name audit-lab -v ~/auditorias/projeto-exemplo:/root/outputs kalilinux/kali-rolling /bin/bash
---

## 2. Workflow Técnico (Fases e Prazos)

Fase,Ação,Objetivo,Prazo
01,Enumeração,Mapear subdomínios e IPs ativos.,1 Dia
02,Identidade,Checar riscos de phishing e clones.,1 Dia
03,GRC,Validar Políticas e LGPD no frontend.,2 Dias

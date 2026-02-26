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

# 🛡️ Procedimento Operacional Padrão (POP)
## Auditoria de Segurança Externa e Reconhecimento (Blue Team Ops)

Este documento estabelece a metodologia de **Reconhecimento Passivo** baseada no framework **CIS Controls v8**. O objetivo é realizar um diagnóstico de segurança com **zero impacto** na operação do cliente.

---

### 1. Preparação do Ambiente (Docker)
Para garantir a segregação de dados e um ambiente limpo para cada cliente, utilizamos containers isolados.

```bash
# Criar diretório de persistência no Host
mkdir -p ~/auditorias/projeto-exemplo

# Subir container Kali Linux com volume compartilhado
sudo docker run -it --name audit-lab \
-v ~/auditorias/projeto-exemplo:/root/outputs \
kalilinux/kali-rolling /bin/bash
```

2. Instalação do Toolkit Essencial
Após acessar o terminal do container, execute a instalação das ferramentas de auditoria:
```bash
apt update && apt install -y \
nmap theharvester curl dnsutils dirb ffuf whatweb dnstwist wordlists
```

### 3. Workflow Técnico (Fases e Prazos)

* **Fase 01 - Enumeração (1 Dia):**
    * Objetivo: Mapear subdomínios e ativos ativos.
* **Fase 02 - Identidade (1 Dia):**
    * Objetivo: Checar riscos de phishing e domínios clones.
* **Fase 03 - Fingerprinting (2 Dias):**
    * Objetivo: Identificar tecnologias e versões expostas.
* **Fase 04 - GRC (2 Dias):**
    * Objetivo: Validar Políticas e conformidade LGPD.

4. Comandos de Referência (Ação Sem Impacto)
Mapeamento de Tecnologias (Fingerprinting):
```bash
whatweb [https://alvo.com.br](https://alvo.com.br) -v

```
Auditoria de Identidade de Domínio:
```bash
dnstwist --registered alvo.com.br
```
Busca de Diretórios Sensíveis (Rate Limited):
```bash
ffuf -u [https://alvo.com.br/FUZZ](https://alvo.com.br/FUZZ) -w /usr/share/wordlists/dirb/common.txt -p 0.1
```

5. Estrutura de Entrega de Consultoria
Ao final da execução técnica, os seguintes artefatos devem ser gerados:

Documento 01: Proposta Comercial, Escopo e ROI.

Documento 02: Relatório Técnico de Vulnerabilidades (Severidade CVSS).

Documento 03: Questionário de Maturidade e Processos Internos.

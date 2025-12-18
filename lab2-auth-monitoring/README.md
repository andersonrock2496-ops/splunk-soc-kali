# Lab 02 — Auth Monitoring (SSH Failed Password) com Splunk

## Objetivo
Monitorar e detectar tentativas de autenticação falhas via SSH utilizando logs do Linux (`/var/log/auth.log`) ingeridos no Splunk.

## Ambiente
- Kali Linux
- Splunk Enterprise
- Fonte de dados: `/var/log/auth.log`

## Evidências

### 🔹 Eventos "Failed password" no Splunk
![Splunk Failed Password](evidence/splunk_index.png)

### 🔹 Contagem de falhas por host
Busca SPL utilizada:
```spl
index=* source="/var/log/auth.log" "Failed password"
| stats count by host
| where count >= 3


# Lab 02 — Auth Monitoring (SSH Failed Password) com Splunk

## Objetivo
Monitorar e detectar tentativas de autenticação falhas via SSH utilizando logs do Linux (`/var/log/auth.log`) ingeridos no Splunk.

## Ambiente
- Kali Linux
- Splunk Enterprise
- Fonte de dados: `/var/log/auth.log`

## Evidências

### 🔹 1. Eventos "Failed password" no Splunk
Visualização dos eventos de falha de autenticação SSH ingeridos a partir do
`/var/log/auth.log`.

![Eventos Failed Password](evidence/splunk_index.png)

---

### 🔹 2. Contagem de falhas por host
Busca SPL utilizada para identificar hosts com múltiplas falhas de autenticação:

```spl
index=* source="/var/log/auth.log" "Failed password"
| stats count by host
| where count >= 3


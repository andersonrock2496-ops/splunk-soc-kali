# Lab 02 — Auth Monitoring (SSH Failed Password) com Splunk

## Objetivo
Monitorar e detectar tentativas de autenticação falhas via SSH utilizando logs do Linux (`/var/log/auth.log`) ingeridos no Splunk.

## Ambiente
- Kali Linux
- Splunk Enterprise
- Fonte de dados: `/var/log/auth.log`

## Evidências

### 1) Eventos "Failed password" no Splunk
![Eventos Failed Password](evidence/splunk_index.png)

### 2) Contagem de falhas por host
![Contagem por host](evidence/splunk_count.png)

### 3) Simulação do cenário (tentativas SSH)
![Brute Force SSH](evidence/Brute_force.png)


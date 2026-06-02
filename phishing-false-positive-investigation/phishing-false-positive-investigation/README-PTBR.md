# Investigação de Falso Positivo - Phishing

## Visão Geral

Esta investigação foi realizada em um ambiente de simulação SOC utilizando o Splunk SIEM.

O alerta foi gerado devido a um e-mail externo contendo uma URL considerada suspeita.

O objetivo da investigação foi determinar se o destinatário interagiu com o link incorporado e identificar qualquer possível atividade maliciosa.

---

## Informações do Alerta

| Campo | Valor |
|---|---|
| ID do Alerta | 8814 |
| Severidade | Média |
| Tipo de Incidente | Phishing |
| Destinatário | j.garcia@thetrydaily.thm |
| Remetente | onboarding@hrconnex.thm |

---

## URL Suspeita

```text
https://hrconnex.thm/onboarding/15400654060/j.garcia
```

---

## Processo de Investigação

### 1. Análise Inicial do E-mail
- Revisão do alerta de phishing
- Identificação da URL externa de onboarding
- Confirmação de ausência de anexos maliciosos

### 2. Investigação no SIEM
Foram realizadas pesquisas no Splunk SIEM para identificar atividades relacionadas.

#### Consultas utilizadas

```spl
j.garcia AND hrconnex
```

```spl
hrconnex NOT datasource=email
```

### 3. Descobertas
- Apenas logs relacionados a e-mails foram encontrados
- Nenhum log de proxy, firewall, DNS ou navegação web foi identificado
- Nenhuma evidência indicou que o usuário acessou a URL incorporada
- A atividade observada aparenta estar relacionada a um processo legítimo de onboarding

---

## Entidades Relacionadas

- j.garcia@thetrydaily.thm
- onboarding@hrconnex.thm
- hrconnex.thm
- https://hrconnex.thm/onboarding/15400654060/j.garcia

---

## Conclusão

O alerta foi classificado como falso positivo porque não foram identificadas evidências de atividade maliciosa ou interação do usuário com a URL incorporada.

A investigação indicou que a atividade observada provavelmente estava relacionada a um processo legítimo de onboarding.

---

## Habilidades Demonstradas

- Investigação em SIEM
- Análise de Logs no Splunk
- Triagem de Phishing
- Correlação de Logs
- Validação de Falso Positivo
- Documentação SOC

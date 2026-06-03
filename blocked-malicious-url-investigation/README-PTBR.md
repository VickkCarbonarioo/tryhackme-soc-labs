# Investigação de URL Maliciosa Bloqueada pelo Firewall

## Visão Geral

Esta investigação foi realizada em um ambiente de simulação SOC utilizando o Splunk SIEM.

O alerta foi gerado após uma tentativa de acesso a uma URL maliciosa identificada pelas regras de segurança da organização.

O objetivo da investigação foi determinar a origem da tentativa de acesso, validar os indicadores de comprometimento (IOCs) envolvidos e verificar se houve comprometimento do host.

---

## Informações do Alerta

| Campo | Valor |
|---|---|
| ID do Alerta | 8816 |
| Severidade | Alta |
| Tipo de Incidente | Firewall |
| Ação | Bloqueado |
| IP de Origem | 10.20.2.17 |
| IP de Destino | 67.199.248.11 |

---

## Indicadores de Comprometimento (IOCs)

### URL Maliciosa

```text
http://bit.ly/3sHkX3da12340
```

### Remetente do E-mail

```text
urgents@amazon.biz
```

### Assunto do E-mail

```text
Your Amazon Package Couldn't Be Delivered - Action Required
```

### IP de Destino

```text
67.199.248.11
```

---

## Processo de Investigação

### 1. Análise Inicial

Foi identificado um alerta de firewall indicando tentativa de acesso a uma URL presente em listas de bloqueio.

### 2. Correlação de Logs

Foram realizadas buscas no Splunk para identificar:

- Origem da URL
- Atividades do host de origem
- Eventos relacionados ao endereço IP de destino
- Possível origem da tentativa de acesso

### 3. Descobertas

Foi identificado um e-mail de phishing enviado por:

```text
urgents@amazon.biz
```

contendo a URL:

```text
http://bit.ly/3sHkX3da12340
```

A investigação confirmou que o usuário tentou acessar a URL presente no e-mail.

O firewall detectou a URL como maliciosa e bloqueou a conexão utilizando a regra:

```text
Blocked Websites
```

Também foi identificado um acesso anterior legítimo ao Google, sem relação com a atividade maliciosa.

---

## Conclusão

O incidente foi classificado como Verdadeiro Positivo.

Foi confirmada a tentativa de acesso a uma URL maliciosa distribuída por meio de um e-mail de phishing.

A conexão foi bloqueada com sucesso pelo firewall da organização e não foram identificadas evidências de comprometimento do host durante a investigação.

---

## Recomendações

- Manter o IOC bloqueado nos controles de segurança.
- Monitorar o host para atividades suspeitas.
- Revisar políticas de proteção contra phishing.
- Realizar conscientização de usuários sobre phishing.
- Considerar redefinição preventiva de senha caso atividades suspeitas sejam identificadas.

---

## Habilidades Demonstradas

- Investigação de Firewall
- Análise de IOC
- Correlação de Logs
- Splunk SIEM
- Phishing Analysis
- Incident Triage
- Threat Validation

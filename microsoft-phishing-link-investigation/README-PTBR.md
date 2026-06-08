
---

# README-PTBR.md

```markdown
# Investigação de Phishing Falso Microsoft

## Visão Geral

Esta investigação foi realizada em um ambiente de simulação SOC utilizando Splunk SIEM.

Um alerta foi gerado após um usuário receber um email de phishing que se passava pela equipe de segurança da Microsoft.

O email continha uma URL maliciosa projetada para direcionar a vítima para uma página falsa de login.

O objetivo da investigação foi verificar se houve interação do usuário com o link malicioso e avaliar o possível impacto do incidente.

---

## Informações do Alerta

| Campo | Valor |
|---------|---------|
| ID do Alerta | 8817 |
| Severidade | Média |
| Tipo de Incidente | Phishing |
| Destinatário | c.allen@thetrydaily.thm |
| Remetente | no-reply@m1crosoftsupport.co |

---

## Linha do Tempo

| Horário | Evento |
|---------|---------|
| 18:48:18 | Email de phishing recebido |
| 18:49:27 | Usuário acessou a URL maliciosa |
| 18:49:27 | Firewall permitiu a conexão |

---

## Indicadores de Comprometimento (IOCs)

### Remetente Malicioso

```text
no-reply@m1crosoftsupport.co

### Domínio Malicioso
m1crosoftsupport.co

### URL Maliciosa
https://m1crosoftsupport.co/login

### IP de Destino
45.148.10.131

### IP Citado no Corpo do Email
102.89.222.143

### Conclusões da Investigação

O email utilizava uma técnica de typosquatting, substituindo a letra "i" pelo número "1" na palavra Microsoft.

Os logs do firewall confirmaram que o usuário acessou a URL maliciosa pouco tempo após receber o email.

A conexão foi permitida pelo firewall, aumentando o risco de comprometimento de credenciais ou outras ações maliciosas.

Durante a investigação não foram encontradas evidências de execução de malware.

### Classificação do Incidente

Verdadeiro Positivo

A URL foi confirmada como maliciosa e houve interação do usuário com o site de phishing.

### Ações Recomendadas
Bloquear o domínio malicioso.
Bloquear a URL maliciosa.
Redefinir a senha do usuário.
Revisar logs de autenticação.
Monitorar o endpoint afetado.
Executar uma varredura de segurança no equipamento.

### Habilidades Demonstradas
Investigação de Phishing
Análise de IOC
Análise de Logs de Firewall
Investigação com Splunk SIEM
Correlação de Eventos
Documentação de Incidentes

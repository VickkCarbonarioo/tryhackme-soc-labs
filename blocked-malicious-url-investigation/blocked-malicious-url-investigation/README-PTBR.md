# Investigação de Tentativa de Acesso a URL Maliciosa

## Visão Geral

Esta investigação foi realizada em um ambiente de simulação SOC utilizando Splunk SIEM.

O alerta foi gerado após uma tentativa de acesso a uma URL maliciosa identificada pelos controles de segurança da organização.

O objetivo da investigação foi determinar a origem da tentativa de acesso, validar os Indicadores de Comprometimento (IOCs) envolvidos e verificar se houve comprometimento do endpoint.

---

## Informações do Alerta

| Campo | Valor |
|--------|--------|
| ID do Alerta | 8816 |
| Severidade | Alta |
| Tipo de Incidente | Firewall |
| Ação | Bloqueado |
| IP de Origem | 10.20.2.17 |
| IP de Destino | 67.199.248.11 |

---

## Linha do Tempo

| Horário | Evento |
|----------|----------|
| 18:46:00 | Usuário recebeu um e-mail de phishing |
| 18:47:14 | Firewall bloqueou o acesso à URL maliciosa |

---

## Indicadores de Comprometimento (IOCs)

### URL

```text
http://bit.ly/3sHkX3da12340
```

### Endereço IP

```text
67.199.248.11
```

### Remetente

```text
urgents@amazon.biz
```

### Destinatário

```text
h.harris@thetrydaily.thm
```

---

## Evidências

Durante a investigação foram identificados os seguintes achados:

- O usuário recebeu um e-mail de phishing se passando pela Amazon Delivery.
- O e-mail continha uma URL encurtada utilizando o serviço bit.ly.
- A URL estava associada ao endereço IP 67.199.248.11.
- A análise da URL/IP classificou o destino como malicioso.
- Os logs do firewall confirmaram que a tentativa de conexão foi bloqueada.
- Não foram encontradas evidências de execução de malware ou comprometimento do endpoint.

---

## Conclusão

O incidente foi classificado como Verdadeiro Positivo.

Foi confirmada uma tentativa de acesso a uma URL maliciosa recebida através de um e-mail de phishing. O firewall bloqueou com sucesso a conexão, impedindo uma possível atividade maliciosa.

Nenhum sinal de comprometimento do endpoint foi identificado durante a investigação.

---

## Ações Recomendadas

- Manter o IOC bloqueado em todas as soluções de segurança.
- Continuar monitorando o endpoint afetado em busca de atividades suspeitas.
- Verificar se outros usuários receberam o mesmo e-mail de phishing.
- Reforçar treinamentos de conscientização sobre phishing.
- Revisar as políticas de filtragem de e-mails para reduzir futuras tentativas de phishing.

# EV ChargeOps – Plataforma Inteligente de Gestão e Rateio de Recarga Compartilhada

## Integrantes
- Nome: ____________________
- RM: ____________________
- Nome: ____________________
- RM: ____________________

---

# 1. Descrição do Problema e Contexto

O crescimento da frota de veículos elétricos tem aumentado a demanda por pontos de recarga compartilhados em condomínios, empresas e universidades. Nesses ambientes, surgem desafios relacionados à identificação dos usuários, controle das sessões de recarga, cálculo do consumo individual e cobrança justa da energia utilizada.

O projeto EV ChargeOps propõe uma plataforma inteligente capaz de integrar os carregadores GoodWe, registrar automaticamente as sessões de recarga, calcular o consumo individual, gerar relatórios gerenciais e utilizar Inteligência Artificial para produzir informações estratégicas.

---

# 2. Frente 1 – Contexto e Problema

## 2.1 Infraestrutura de Recarga Compartilhada

Infraestruturas de recarga compartilhada são ambientes onde vários usuários utilizam os mesmos carregadores.

### Principais desafios

- Controle de acesso aos carregadores.
- Identificação do usuário.
- Rateio justo dos custos.
- Monitoramento de consumo.
- Controle de horários de utilização.
- Prevenção de uso indevido.

## 2.2 Funcionamento de uma Sessão de Recarga

1. Usuário conecta o veículo.
2. Sistema identifica o usuário.
3. Carregador inicia a sessão.
4. Dados são coletados continuamente.
5. Sessão é encerrada.
6. Consumo é calculado.
7. Fatura é gerada.

### Dados gerados

- ID da sessão
- Usuário
- Data e hora de início
- Data e hora de término
- Duração
- Energia consumida (kWh)
- Potência média
- Status da sessão

## 2.3 Modelos de Negócio

### Recarga Gratuita
Vantagem: simplicidade.
Desvantagem: custo absorvido pelo gestor.

### Cobrança por kWh
Vantagem: justiça na cobrança.
Desvantagem: depende de medição precisa.

### Cobrança por Tempo
Vantagem: simples implementação.
Desvantagem: não reflete o consumo real.

### Assinatura Mensal
Vantagem: previsibilidade.
Desvantagem: usuários leves podem pagar mais.

### Rateio Condominial
Vantagem: facilidade administrativa.
Desvantagem: pode gerar injustiça entre usuários.

## 2.4 Aprofundamento – Análise de Mercado

### ChargePoint

Problema resolvido:
Gestão de carregadores compartilhados.

Funcionalidades:
- Monitoramento remoto
- Relatórios
- Controle de acesso

Modelo:
Assinatura e cobrança por uso.

Limitações:
Dependência de infraestrutura compatível.

### Wallbox

Problema resolvido:
Gerenciamento residencial e corporativo.

Funcionalidades:
- Controle via aplicativo
- Monitoramento de consumo
- Controle de potência

Modelo:
Venda de hardware e software.

Limitações:
Recursos avançados dependem de integração.

### Zaptec

Problema resolvido:
Gestão inteligente de múltiplos carregadores.

Funcionalidades:
- Balanceamento de carga
- Controle remoto
- Relatórios

Modelo:
Venda de equipamento e serviços.

Limitações:
Maior custo inicial.

---

# 3. Frente 2 – Base Regulatória e Técnica

## 3.1 Resolução Normativa ANEEL 1000/2021

A resolução regulamenta aspectos relacionados ao fornecimento de energia elétrica e estabelece diretrizes para utilização de infraestrutura de recarga.

Pontos relevantes:

- Possibilidade de exploração comercial da recarga.
- Necessidade de conformidade regulatória.
- Utilização de protocolos abertos quando aplicável.

## 3.2 GoodWe HCA G2

### RS-485
Comunicação industrial para integração com sistemas externos.

### LAN
Integração em redes locais.

### Wi-Fi
Monitoramento remoto.

### Bluetooth
Configuração local.

### RFID
Identificação de usuários.

## 3.3 API GoodWe SEMS

Dados disponíveis:

- Status do carregador
- Potência instantânea
- Energia consumida
- Eventos de sessão
- Histórico operacional

## 3.4 Aprofundamento – APIs Complementares

### Open Charge Map API

Permite consultar:
- Localização de carregadores
- Tipo de conectores
- Disponibilidade

### Google Places API

Permite consultar:
- Localização de estações
- Informações de estabelecimentos
- Recursos relacionados à mobilidade elétrica

---

# 4. Frente 3 – Arquitetura e IA

## 4.1 Arquitetura da Solução

```text
Usuário
   |
   v
Carregador GoodWe
   |
   v
API SEMS Portal
   |
   v
Backend EV ChargeOps
   |
   +--> Banco de Dados
   |
   +--> Módulo de IA
   |
   v
Dashboard Web
```

## 4.2 Fluxo de Dados

1. Usuário inicia recarga.
2. Carregador registra informações.
3. API SEMS envia dados.
4. Backend processa informações.
5. Banco de dados armazena registros.
6. IA analisa padrões.
7. Sistema gera cobrança.
8. Usuário consulta resultados.

## 4.3 Modelo de Rateio

Fórmula:

Valor = kWh Consumido × Tarifa do kWh

Exemplo:

50 kWh × R$ 0,90 = R$ 45,00

### Casos Especiais

Sessão interrompida:
- Cobrança proporcional ao consumo registrado.

Usuário sem utilização:
- Não há cobrança.

Dois veículos:
- Soma dos consumos da unidade.

## 4.4 Papel da Inteligência Artificial

### IA 1 – Previsão de Consumo

Objetivo:
Prever demanda futura.

Benefícios:
- Planejamento energético.
- Redução de custos.

### IA 2 – Detecção de Anomalias

Objetivo:
Identificar comportamentos suspeitos.

Exemplos:
- Consumo fora do padrão.
- Sessões excessivamente longas.
- Possíveis fraudes.

Benefícios:
- Maior segurança.
- Melhor gestão operacional.

---

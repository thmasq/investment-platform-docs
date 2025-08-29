# Plataforma de Análise de Ações com Deep Learning

Engenharia de Produto de Software - 2025.2

## Integrantes

| Grupo | Nome           | Matrícula | Perfil                                             |
| ----- | -------------- | --------- | -------------------------------------------------- |
| 11    | André Silva    | 221007813 | [Hunter104](https:://github.com/Hunter104)         |
| 11    | Thomas Queiroz | 211062526 | [thomasqz](https:://github.com/thomasqz)           |
| 11    | Eduardo Sandes | 221008024 | [DiceRunner714](https:://github.com/DiceRunner714) |

## Visão Geral

### Contexto Acadêmico

Este projeto implementa conceitos de [**Deep Reinforcement Learning (DRL)**](glossario.md#d) e **Processamento de linguagem natural (NLP)** aplicados ao mercado financeiro, baseado em pesquisas recentes que demonstram a eficácia de redes [LSTM](glossario.md#l) combinadas com modelos de linguagem especializados em finanças.

**Fundamentação Teórica:**

- **Veisi et al. (2024)**: Demonstrou que a combinação de análise técnica, fundamental e processamento de notícias com [FinBERT](glossario.md#f) resulta em [Índice de Sharpe](glossario.md#i) de 1.46 e retorno cumulativo de 134.39%
- **Sarlakifar et al. (2024)**: Mostrou que redes [xLSTM](glossario.md#x) superam [LSTM](glossario.md#l) tradicionais em trading automatizado, com melhor captura de dependências temporais

## Escopo

### MVP:

- Sistema educacional de análise de ações (não para trading real)
- Modelo [LSTM](glossario.md#l) simples para previsão de tendências
- Integração com [FinBERT](glossario.md#f) pré-treinado para [análise de sentimento](glossario.md#a)
- Interface web para visualização de resultados
- [Backtesting](glossario.md#b) básico com métricas educacionais
- Análise de 10-15 ações principais (AAPL, GOOGL, MSFT, AMZN, TSLA, etc.)
- Batch processing de dados

### Funcionalidades futuras

- Sistema de trading real
- Implementação de [xLSTM](glossario.md#x) do zero
- Análise de mais de 500 ações
- Sistema de autenticação
- Processamento de dados por WebSockets

## Roadmap de Desenvolvimento

### Fase 1: Fundação (Semanas 1-3)

**Sprint 1.1: Setup do Projeto (Semana 1)**

- Configuração do ambiente de desenvolvimento (Docker, Git, Python)
- Criação da estrutura do repositório
- Setup do pipeline CI/CD básico
- Documentação inicial do projeto

_Critérios de Aceitação:_

- Repositório com estrutura padronizada
- Ambiente Docker funcionando para todos os membros
- README com instruções de setup

**Sprint 1.2: Coleta de Dados (Semanas 2-3)**

- Implementação do coletor de dados usando Yahoo Finance API
- Coleta de dados históricos para 10-15 ações selecionadas (AAPL, GOOGL, MSFT, AMZN, TSLA, etc.)
- Coleta de headlines de notícias financeiras (usando APIs gratuitas)
- Validação e limpeza dos dados

_Critérios de Aceitação:_

- Dataset com 2+ anos de dados OHLCV para ações selecionadas
- Base de notícias com pelo menos 200 headlines por ação
- Script de validação de qualidade dos dados
- Documentação do esquema de dados

### Fase 2: Modelos de ML (Semanas 4-6)

**Sprint 2.1: Modelo de Previsão LSTM (Semana 4)**

- Implementação de [LSTM](glossario.md#l) básico usando TensorFlow/PyTorch
- [Feature engineering](glossario.md#f): [indicadores técnicos](glossario.md#i) ([RSI](glossario.md#r), [MACD](glossario.md#m), Moving Averages)
- Treinamento para predição de movimento de preços (alta/baixa/neutro)

_Critérios de Aceitação:_

- Modelo [LSTM](glossario.md#l) treinado com acurácia > 55% em dados de validação
- [Pipeline de dados](glossario.md#p) de preprocessing reproducível
- Notebooks Jupyter com análise exploratória

**Sprint 2.2: Integração com FinBERT (Semana 5)**

- Integração com modelo [FinBERT](glossario.md#f) pré-treinado via HuggingFace
- Processamento de headlines para scores de [análise de sentimento](glossario.md#a)
- Combinação de features técnicas com sentimento

_Critérios de Aceitação:_

- [Pipeline de dados](glossario.md#p) de análise de sentimento funcionando
- [Análise de correlação](glossario.md#a) entre sentimento e movimentos de preços documentada
- Modelo combinado ([LSTM](glossario.md#l) + sentiment) com performance superior

**Sprint 2.3: Sistema de Backtesting (Semana 6)**

- Implementação de [backtesting](glossario.md#b) simples
- Métricas básicas: retorno total, [Índice de Sharpe](glossario.md#i), [maximum drawdown](glossario.md#m)
- [Cross-validation temporal](glossario.md#c)

_Critérios de Aceitação:_

- Framework de [backtesting](glossario.md#b) com período out-of-sample
- Relatório de performance com visualizações
- Comparação com estratégia [buy-and-hold](glossario.md#b)

### Fase 3: Sistema Web (Semanas 7-9)

**Sprint 3.1: API REST (Semana 7)**

- [API REST](glossario.md#a) usando [FastAPI](glossario.md#f)
- Endpoints para previsões, dados históricos e métricas
- Integração com modelos treinados

_Critérios de Aceitação:_

- API documentada com Swagger
- Testes unitários básicos
- Deploy local funcionando

**Sprint 3.2: Frontend (Semana 8)**

- Dashboard web usando React ou Vue.js
- Gráficos de preços com Chart.js
- Visualização de previsões e métricas

_Critérios de Aceitação:_

- Interface funcionando
- Gráficos interativos funcionando
- Deploy da aplicação completa

**Sprint 3.3: Integração e Testes (Semana 9)**

- Testes de integração
- Otimização de performance
- Documentação final

### Fase 4: Validação (Semana 10)

**Sprint 4.1: Experimentos e Validação (Semana 10)**

- Experimentos comparativos (LSTM vs LSTM+Sentiment)
- Análise estatística dos resultados
- Identificação de limitações

## Recursos Técnicos

### Stack Tecnológico

- **Backend**: Python, [FastAPI](glossario.md#f), SQLite
- **ML**: TensorFlow/PyTorch, HuggingFace Transformers, pandas, scikit-learn
- **Frontend**: React.js, Chart.js
- **Infraestrutura**: [Docker](glossario.md#d), [CI/CD](glossario.md#c) com GitHub Actions
- **Dados**: Yahoo Finance API, NewsAPI (com [rate limiting](glossario.md#r))

### Datasets e Modelos

- **Dados de Mercado**: Yahoo Finance (gratuito, 2+ anos de histórico)
- **Notícias**: NewsAPI ou similar (com limitações de rate)
- **FinBERT**: Modelo pré-treinado do HuggingFace
- **Ações Selecionadas**: Top 10-15 por capitalização de mercado

## Cronograma Resumido

| Fase | Duração     | Foco Principal   | Entregáveis                  |
| ---- | ----------- | ---------------- | ---------------------------- |
| 1    | Semanas 1-3 | Fundação e Dados | Setup + Dataset              |
| 2    | Semanas 4-6 | Modelos ML       | LSTM + FinBERT + Backtesting |
| 3    | Semanas 7-9 | Sistema Web      | API + Frontend + Deploy      |
| 4    | Semana 10   | Validação        | Experimentos                 |

## Recursos

### Repositórios Disponíveis

- **LSTM-PPO DRL Stock Trader**: https://github.com/MahanVeisi8/LSTMppo-DRL-StockTrader
  - Implementação completa do framework LSTM-PPO para trading
  - Integração com FinBERT para análise de sentimento
  - Pipeline de backtesting e métricas de avaliação
  - Código base que pode ser adaptado para o projeto acadêmico

### Utilização dos Recursos

O repositório de Veisi et al. fornece:

- Estrutura do ambiente de trading
- Implementação do algoritmo PPO com redes LSTM
- Pipeline de processamento de dados financeiros
- Sistema de recompensas e penalidades
- Métricas de avaliação padronizadas

## Referências Científicas

1. **Veisi, Mahan, Sadra Berangi, Mahdi Shahbazi Khojasteh, and Armin Salimi-Badr.** "A Deep Reinforcement Learning Approach Combining Technical and Fundamental Analyses with a Large Language Model for Stock Trading." In _2024 14th International Conference on Computer and Knowledge Engineering (ICCKE)_, pp. 224-229. IEEE, 2024.

2. **Sarlakifar, Faezeh, Mohammadreza Mohammadzadeh Asl, Sajjad Rezvani Khaledi, and Armin Salimi-Badr.** "A Deep Reinforcement Learning Approach to Automated Stock Trading, using xLSTM Networks." _arXiv preprint arXiv:2503.09655_ (2025).

3. **Yang, Yi, Mark Christopher Siy UY, and Allen Huang.** "FinBERT: A Pretrained Language Model for Financial Communications." _arXiv preprint arXiv:2006.08097_ (2020).

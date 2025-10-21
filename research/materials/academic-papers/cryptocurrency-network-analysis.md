# Análise: Cryptocurrency Network Analysis

**Data**: 20 de outubro de 2025  
**Artigo**: "Cryptocurrency Network Analysis"  
**Autores**: Natkamon Tovanich, Célestin Coquidé, Rémy Cazabet  
**Journal**: arXiv:2502.03411v1 [cs.SI] (5 Feb 2025)  
**DOI**: 10.48550/arXiv.2502.03411

## Resumo Executivo

Este artigo apresenta uma revisão abrangente sobre análise de redes de criptomoedas, aplicando ferramentas e métodos de análise de redes sociais a dados transacionais de criptomoedas. O estudo foca principalmente em Bitcoin e Ethereum, explorando diferentes representações de rede, técnicas de clustering de endereços, e aplicações em detecção de atividades ilegais e análise de DeFi.

## Definição e Escopo

### Conceito Central
A análise de redes de criptomoedas consiste em aplicar ferramentas e métodos de análise de redes sociais a dados transacionais de criptomoedas. A principal diferença com redes sociais online é que usuários não trocam conteúdo textual, mas valor (em sistemas como Bitcoin) ou itens digitais e serviços (em sistemas baseados em smart contracts como Ethereum).

### Dados Transacionais
- **Acesso livre**: Dados transacionais podem ser acessados e coletados livremente
- **Natureza similar**: Dados similares em natureza às interações de redes sociais online
- **Representação natural**: Dados naturalmente representados como redes
- **Escala dinâmica**: Grande escala e natureza dinâmica
- **Influência social**: Influenciados por e sobre a sociedade como um todo

## Metodologias de Análise

### 1. Representações de Rede Bitcoin

#### Address-Transaction Network
- **Rede bipartida**: Nós representam transações e endereços
- **Arestas direcionadas**: Presença de endereços em input/output de transações
- **Pesos**: Valor que recebem ou contribuem
- **Característica**: Sem perda de informação, mas difícil de estudar

#### Transaction Network
- **Projeção**: Rede bipartida projetada em transações
- **Conexão**: Aresta existe entre Tx1 e Tx2 se output de Tx1 é input de Tx2
- **Peso**: Soma de todas as ocorrências
- **Foco**: Fluxo de moedas, não representa usuários

#### Address Network
- **Projeção**: Rede bipartida projetada em endereços
- **Conexão**: Aresta direcionada entre endereços se um é input e outro output
- **Limitação**: Cada transação pode gerar grande número de arestas
- **Alternativa**: Hipergrafo direcionado ponderado ou rede de ordem superior

#### User Network
- **Representação mais comum**: Rede substituta usando clustering de endereços
- **Nós**: Usuários (grupos de endereços)
- **Arestas**: Transações entre usuários
- **Processo**: Clustering de endereços não-trivial
- **Vantagem**: Mais direto para interpretar
- **Limitação**: Não totalmente fiel ao que ocorreu na blockchain

### 2. Técnicas de Clustering de Endereços

#### Co-Input Heuristic
- **Método mais comum**: Agrega endereços usados como inputs da mesma transação
- **Justificativa**: Múltiplas entidades assinando transação requer alto grau de cooperação
- **Eficácia**: Continuamente mostrado como confiável e eficaz
- **Limitação**: Subestimação do conjunto de endereços do usuário

#### Técnicas Avançadas
- **Heurísticas avançadas**: Para descobrir endereços de troco
- **Machine learning não-supervisionado**: Para clustering
- **Machine learning supervisionado**: Para classificação
- **Padrões de ocultação**: Fork-merge e peeling chain patterns

### 3. Análise de Ethereum

#### Modelo Baseado em Contas
- **Diferença do UTXO**: Ethereum usa modelo baseado em contas
- **Simplificação**: Não é obrigatório fazer clustering de endereços
- **Estado**: Cada nó armazena e sincroniza estado atual da blockchain
- **Tipos de conta**: EOA (Externally Owned Accounts) e CA (Contract Accounts)

#### Redes de Transferência de Tokens
- **Event logs**: Registro de eventos durante execução de smart contracts
- **ERC-20**: Tokens fungíveis com logs de transferência
- **Rede direcionada**: Arestas direcionadas e ponderadas representam transferências
- **Múltiplas arestas**: Contas podem trocar múltiplos tokens

## Aplicações Práticas

### 1. Detecção de Atividades Ilegais
- **Ransomware**: Detecção usando machine learning supervisionado
- **Lavagem de dinheiro**: Tracking de fluxos de dinheiro de contas ilícitas
- **Phishing**: Classificação de contas de phishing usando GNNs
- **Wash trading**: Detecção de transações falsas em mercados NFT

### 2. Análise de DeFi
- **Estratégias de trading**: Análise de atividades financeiras públicas
- **Risco sistêmico**: Avaliação de propagação de efeito dominó
- **MEV (Maximal Extractable Value)**: Identificação de estratégias de arbitragem
- **Building blocks**: Extração de componentes frequentes em protocolos DeFi

### 3. Propriedades de Rede
- **Small world**: Propriedades de mundo pequeno demonstradas
- **Scale-free**: Características de escala livre
- **Bow-tie structure**: Estrutura conhecida da World Wide Web
- **Componente fortemente conectado**: Inclui maioria das transações

## Acessibilidade de Dados

### 1. Executando Próprio Nó
- **Dados completos**: Download direto de dados de toda a blockchain
- **ETL tools**: Transformação de dados brutos em rede
- **Ferramentas**: Blockchain ETL, Cryo para Ethereum

### 2. Node-as-a-Service
- **Provedores**: Infura, QuickNode, Moralis, Alchemy
- **Vantagem**: Sem overhead de manutenção de infraestrutura
- **APIs**: Acesso a dados específicos como detalhes de transações

### 3. APIs de Dados
- **Plataformas**: Blockchain.com, Etherscan, Blockchair, Bitquery, Covalent
- **Limitações**: Limitações de query, possíveis custos
- **Ferramentas especializadas**: The Graph, Dune Analytics

### 4. Datasets Curados
- **BADX, Chartalist, Elliptic dataset, XBlock**: Datasets específicos
- **Aplicações**: Ransomware, contas de phishing, redes de tokens
- **Vantagem**: Dados pré-processados para validação de modelos

## Relevância para Nossa Pesquisa

### Aplicação Direta
1. **Metodologias de análise**: Técnicas comprovadas para análise de dados blockchain
2. **Representações de rede**: Diferentes abordagens para modelar dados transacionais
3. **Técnicas de clustering**: Métodos para agrupar endereços e identificar usuários
4. **Ferramentas de acesso**: Plataformas e APIs para coleta de dados

### Insights para Desenvolvimento do Explorer
1. **Estrutura de dados**: Como organizar e representar dados transacionais
2. **Algoritmos de análise**: Técnicas para identificar padrões e comportamentos
3. **Visualizações**: Métodos para representar redes complexas
4. **Performance**: Otimizações para análise de grandes volumes de dados

### Funcionalidades Essenciais
1. **Clustering de endereços**: Agrupamento de endereços por usuário
2. **Análise de fluxo**: Tracking de movimentação de valores
3. **Detecção de padrões**: Identificação de comportamentos suspeitos
4. **Visualização de rede**: Representação gráfica de conexões

## Limitações e Desafios

### 1. Precisão do Clustering
- **Subestimação**: Métodos podem subestimar conjunto de endereços
- **Padrões de ocultação**: Usuários podem usar esquemas de ocultação
- **Erros de merge**: Usuários podem decidir fazer merge de outputs

### 2. Complexidade Computacional
- **Escala**: Análise de grandes volumes de dados
- **Tempo real**: Processamento de dados em tempo real
- **Armazenamento**: Necessidade de grandes capacidades de armazenamento

### 3. Interpretação de Dados
- **Pseudonimato**: Natureza pseudônima dos usuários blockchain
- **Múltiplos endereços**: Usuários controlam múltiplos endereços
- **Transações complexas**: Transações podem envolver centenas de endereços

## Conclusão

Este artigo fornece uma base sólida de conhecimento sobre análise de redes de criptomoedas, oferecendo metodologias comprovadas e ferramentas práticas para análise de dados blockchain. Os insights são diretamente aplicáveis ao desenvolvimento de nosso block explorer, fornecendo:

1. **Metodologias de análise**: Técnicas comprovadas para processamento de dados
2. **Ferramentas de acesso**: Plataformas e APIs para coleta de dados
3. **Algoritmos de clustering**: Métodos para agrupar endereços e identificar usuários
4. **Técnicas de visualização**: Abordagens para representar redes complexas

A pesquisa confirma que nossa abordagem de análise sistemática de block explorers existentes é adequada e bem fundamentada, fornecendo uma base sólida para o desenvolvimento de nosso explorer específico para nossa blockchain.

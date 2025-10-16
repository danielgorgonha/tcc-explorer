# Guia Rápido de Início

## Para Começar

Este repositório contém pesquisa científica sobre block explorers. Não há código para executar, apenas documentação para ler e usar como base para artigos acadêmicos.

## Primeiros Passos

### 1. Entender o Projeto (5 minutos)
Leia nesta ordem:
1. README.md
2. SUMMARY.md

### 2. Ver o Que Já Foi Feito (10 minutos)
Navegue para:
- `research/explorers-overview.md` - Ver os 12 explorers analisados
- `INDEX.md` - Ver todos os documentos disponíveis

### 3. Entender a Metodologia (15 minutos)
Leia:
- `research/research-plan.md` - Plano completo de 6 meses

### 4. Mergulhar no Conteúdo Técnico (1-2 horas)
Leia o whitepaper principal:
- `docs/whitepaper/block-explorers-state-of-the-art.md`

## Estrutura Resumida

```
README.md              # Comece aqui
SUMMARY.md             # Resumo executivo
INDEX.md               # Navegação completa

research/              # Toda a pesquisa
├── research-plan.md           # Plano de 6 meses
├── explorers-overview.md      # 12 explorers analisados
└── analysis/comparative-analysis.md  # Análise técnica

docs/whitepaper/       # Whitepaper principal (50+ páginas)
docs/articles/         # Templates de artigos
docs/roadmap.md        # Cronograma
```

## Casos de Uso Comuns

### Caso 1: Quero Escrever um Artigo Científico
1. Leia `docs/articles/article-templates.md`
2. Escolha o tipo de artigo (Survey, Technical, Design, etc)
3. Use dados de `research/analysis/comparative-analysis.md`
4. Referencie `research/literature-review/state-of-art.md`

### Caso 2: Quero Entender Block Explorers
1. Leia seções 1-2 do whitepaper
2. Depois leia `research/explorers-overview.md`
3. Veja análise técnica em `research/analysis/comparative-analysis.md`

### Caso 3: Quero Desenvolver um Explorer
1. Leia `research/analysis/comparative-analysis.md` - Padrões identificados
2. Leia `src/architecture/system-design.md` - Arquitetura proposta
3. Veja recomendações no whitepaper seção 7

### Caso 4: Quero Contribuir com a Pesquisa
1. Identifique explorers não mapeados
2. Colete dados técnicos adicionais
3. Adicione referências bibliográficas
4. Abra issue ou PR com contribuições

## Perguntas Frequentes

### P: Este projeto tem código executável?
R: Não. É um projeto de pesquisa acadêmica com documentação e análises.

### P: Preciso instalar algo?
R: Não. Todos os documentos são em Markdown, podem ser lidos em qualquer editor de texto.

### P: Como executo o projeto?
R: Não há execução. Leia os documentos, use-os como base para escrever artigos.

### P: Onde estão os dados de benchmarking?
R: Ainda serão coletados. A estrutura está em `data/benchmarks/` (vazia atualmente).

### P: Posso usar isso para meu TCC?
R: Sim, desde que cite apropriadamente. Use como referência e base para sua própria pesquisa.

### P: Como cito este trabalho?
R: 
```
Gorgonha, D. R. (2024). Block Explorers: Análise Arquitetural e Pesquisa Científica. 
Programa de Pós-Graduação em Blockchain. 
Disponível em: https://github.com/tcc-explorer/tcc-explorer
```

## Documentos por Prioridade

### Alta Prioridade (Ler Primeiro)
1. README.md
2. research/explorers-overview.md
3. docs/whitepaper/block-explorers-state-of-the-art.md

### Média Prioridade (Ler Depois)
1. research/research-plan.md
2. research/analysis/comparative-analysis.md
3. docs/articles/article-templates.md

### Baixa Prioridade (Consulta)
1. research/methodology/research-framework.md
2. research/literature-review/state-of-art.md
3. src/architecture/system-design.md

## Workflow Típico

```
Dia 1: Ler README + SUMMARY + explorers-overview
       ↓
Dia 2-3: Ler whitepaper completo
       ↓
Dia 4-5: Ler análise comparativa
       ↓
Dia 6-10: Escrever primeiro artigo
       ↓
Dia 11+: Coletar dados adicionais, escrever mais artigos
```

## Recursos Externos

### Bases Acadêmicas
- IEEE Xplore: https://ieeexplore.ieee.org
- ACM Digital Library: https://dl.acm.org
- arXiv: https://arxiv.org

### Explorers para Estudar
- Etherscan: https://etherscan.io
- BlockScout: https://blockscout.com
- Mempool.space: https://mempool.space
- Mintscan: https://mintscan.io
- Subscan: https://subscan.io
- Solana Explorer: https://explorer.solana.com

### Ferramentas Úteis
- LaTeX: Para escrever artigos científicos
- Mendeley/Zotero: Para gerenciar referências
- Draw.io: Para diagramas
- GitHub: Para versionar documentos

## Suporte

Para dúvidas sobre a pesquisa:
1. Consulte INDEX.md para encontrar documento relevante
2. Leia STRUCTURE.md para entender organização
3. Abra issue no GitHub se necessário

---

**Versão**: 1.0  
**Atualização**: Janeiro 2024

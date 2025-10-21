# Tradução e Resumo: Método de Recuperação Rápida de Dados usando Explorers
**Data**: 20 de outubro de 2025  
**Artigo**: "Devising a method for rapid data retrieval using explorers for blockchain analysis"  
**Autores**: Yaroslaw Dorogyy, Vadym Kolisnichenko  
**Journal**: Eastern-European Journal of Enterprise Technologies (2023)  
**DOI**: 10.15587/1729-4061.2023.286079

## Resumo Executivo

Este artigo apresenta um método inovador para coleta rápida de dados de block explorers para análise de redes blockchain. O objetivo principal é desenvolver uma abordagem que evite a necessidade de sincronizar nós completos de blockchain, que tradicionalmente requerem recursos computacionais significativos e tempo considerável.

O problema identificado pelos autores é que a análise tradicional de blockchain envolve a implantação e sincronização de um nó blockchain, o que requer recursos computacionais significativos e tempo para sincronização. Analisar múltiplas redes blockchain simultaneamente demanda esforço substancial e requer custos ainda maiores.

A solução proposta envolve utilizar block explorers publicamente acessíveis, o que permite recuperação rápida de dados com recursos computacionais mínimos para análise posterior. Além disso, obter informações suplementares de block explorers fornece detalhes valiosos que podem ser inacessíveis usando métodos tradicionais de recuperação de dados.

## Metodologia Científica

A eficiência do método proposto foi verificada através do desenvolvimento de um sistema protótipo. Os dados foram coletados para 14 redes blockchain especificadas para analisar smart contracts dentro dessas redes. Informações sobre contas (incluindo estatísticas de saldo) foram coletadas, smart contracts foram identificados entre as contas, dados sobre tokens existentes possuídos por smart contracts foram obtidos, e bytecode e código fonte (quando disponível) dos contratos foram coletados e decompilados. O processo levou quase 24 horas em uma máquina de computação em nuvem com configuração mínima.

Com base nos dados coletados, um exemplo de smart contract foi analisado para demonstrar a completude do processo. Os resultados desta pesquisa minimizam as despesas de recursos computacionais e permitem um processo de coleta de dados simplificado e rápido sem configuração manual, permitindo que pesquisadores e analistas se concentrem nas etapas subsequentes de análise.

### Redes Blockchain Analisadas

Foram selecionadas 14 redes blockchain baseadas na máquina virtual Ethereum (EVM) para o experimento de coleta de informações: Acala, Aves, Energy Web, Era Swap, Karura, Kava, MCH-verse, Nahmii, Neatiio, OASYS, Puppynet, Rootstock, SmartBCH e Xiden.

Uma máquina de computação em nuvem da plataforma Vultr com a menor configuração possível para o sistema operacional selecionado foi usada para o estudo. Esta é uma máquina de desempenho normal com os seguintes parâmetros: processador de 1 núcleo virtual Intel Core, RAM de 1 GB, drive SSD de 25 TB, largura de banda de saída de 1 TB, sistema operacional Ubuntu 23.04.

## Resultados Obtidos

Durante o primeiro estágio, informações sobre contas e saldo de criptomoeda para cada conta individual na rede foram obtidas dos block explorers (via endpoint /accounts). A tabela exibe o número total de contas com saldo positivo de criptomoeda recebido na rede, bem como estatísticas de saldo das contas. O saldo total de todas as contas é calculado como a soma dos saldos de cada conta da rede. O valor máximo do saldo é o maior saldo entre todas as contas da rede. O valor médio do saldo é a média aritmética, ou seja, a razão do saldo total pelo número de contas da rede recebidas. Os saldos medianos são o valor localizado no meio da série ordenada de saldos de todas as contas da rede recebidas.

Após receber dados de contas, smart contracts são selecionados para processamento posterior. A tabela exibe as mesmas informações da tabela anterior, mas apenas para um subconjunto de contas - para smart contracts. Os valores são calculados da mesma forma que para a Tabela 2, mas, neste caso, os valores são tomados apenas para smart contracts.

O próximo passo envolve obter os bytecodes dos smart contracts implantados dos block explorers (via endpoint /address/{address}/contracts), bem como seu código fonte, se disponível. Todos os bytecodes são então decompilados usando o decompilador selecionado. A tabela mostra o número de bytecodes implantados em cada rede, seu tamanho médio e o número de códigos fonte recebidos. Também indica quantos bytecodes foram decompilados com sucesso.

O tamanho médio de um smart contract é calculado como a razão da soma dos tamanhos de todos os bytecodes recebidos pelo seu número recebido em uma determinada rede blockchain. Os códigos fonte estão disponíveis apenas para aqueles smart contracts que foram submetidos ao block explorer para verificação. Todos os bytecodes recebidos estão sujeitos ao processo de decompilação, mesmo quando o código fonte correspondente está disponível. Bytecode de smart contract decompilado com sucesso refere-se à execução bem-sucedida do programa decompilador e não leva em conta a qualidade do resultado da decompilação.

No próximo estágio, informações são obtidas do explorer (via endpoint /address/{address}/token-balances) sobre tokens que pertencem a smart contracts.

## Arquitetura do Sistema

O método de usar block explorers para obter rapidamente dados de muitas redes blockchain inclui 4 estágios: escolher um block explorer; análise da arquitetura do sistema existente ou novo de análise de rede blockchain, no qual a implementação de software do método será integrada; determinação da técnica de comunicação com o block explorer; implementação de software de coleta de dados de block explorers.

Para coleta de dados, é possível usar nós públicos comuns e interface JSON-RPC, mas block explorers fornecem vantagens significativas sobre uma interface JSON-RPC simples. Eles fornecem informações adicionais que contribuem para uma análise mais completa, especialmente para entender smart contracts nas redes blockchain sob investigação.

O método de usar block explorers para obter rapidamente dados de muitas redes blockchain inclui as seguintes ações. Passo 1: Escolher um block explorer. A escolha do explorer é o primeiro e principal passo e afeta a eficácia do método. Ao escolher um explorer, é importante levar em conta a tarefa que a análise atual de blockchain resolve, porque isso deixa claro que informações serão coletadas e com que intensidade, o que revelará limitações potenciais e viabilidade de usar o método.

Passo 2: Análise da arquitetura. Uma análise da arquitetura do sistema existente ou novo de análise de rede blockchain, no qual a implementação de software do método será integrada, é realizada. Uma parte importante da análise da arquitetura é a determinação de oportunidades para escalabilidade e paralelização de processos para coletar simultaneamente informações de muitas redes blockchain.

Passo 3: Determinação do método de comunicação com o block explorer. É determinado exatamente como as informações serão obtidas do block explorer: usando uma interface de programação de aplicação (API) ou uma interface web regular (que envolve análise de páginas web). Os endpoints do block explorer também são definidos, que serão usados para obter os dados necessários.

Passo 4: Implementação de software de coleta de dados. Neste estágio, ferramentas de software são analisadas e desenvolvimento de módulos apropriados para comunicação com o block explorer para obter dados com base na arquitetura desenvolvida levando em conta a paralelização é realizada.

### Explorer Escolhido: BlockScout

Após analisar várias redes blockchain e explorers, foi concluído que Blockscout é o melhor candidato para fins de pesquisa posteriores, embora possa não ser ótimo para outras tarefas. Blockscout é uma plataforma projetada para pesquisa aprofundada em sistemas blockchain. Suporte multi-blockchain, extensa customização e código aberto fornecem aos usuários acesso completo a todos os dados e funções para várias redes blockchain. Assim, Blockscout fornece aos usuários uma ampla gama de oportunidades para explorar e entender profundamente o espaço blockchain. Uma característica importante é que Blockscout fornece códigos fonte de contratos verificados e seu bytecode implantado correspondente para ser usado em análises posteriores.

## Análise Técnica Detalhada

Para obter dados do Blockscout, os links que são responsáveis por fornecer certos dados devem ser determinados. Apenas três endpoints do explorer Blockscout são usados neste estudo: /accounts - para obter endereços de contas, saldos de criptomoeda e tipos de conta, seja smart contract ou Conta Externamente Possuída (EOA). Este endpoint fornece apenas contas principais cujo saldo de criptomoeda excede 0. Vale notar que contratos nativos (smart contracts nativos - integrados ao sistema blockchain, e não implantados nele) podem ser reconhecidos como EOA e não como smart contracts; /address/{address}/contracts - para obter o código fonte do smart contract (se disponível) e o bytecode implantado. Também, se o contrato for um contrato proxy, Blockscout o detecta e fornece o endereço de implementação; /address/{address}/token-balances - para obter os tokens possuídos pela conta e sua quantidade.

A recuperação de dados, análise e processamento podem ser paralelizados usando um pool de threads ou pool de processos. Um processo simplificado de aquisição de dados paralelos é mostrado na figura. Isso evitará vários gargalos, entre os quais os principais são latência de rede e decompilação de bytecode de smart contract.

### Processamento de Dados

O sistema protótipo é construído com base na arquitetura desenvolvida no subcapítulo anterior. A arquitetura prevê a aquisição simultânea de dados de várias redes blockchain para análise de smart contracts. A linguagem de programação Python foi usada para o protótipo, bem como a biblioteca Beautiful Soup para análise de HyperText Markup Language (HTML). Essas ferramentas são eficazes para prototipagem e teste de hipóteses.

Como parte deste processo de coleta de dados, é claro que pode haver situações onde o código fonte dos contratos pode não estar disponível. Em tais casos, um método conhecido como decompilação de bytecode é usado para produzir pseudocódigo. A decompilação de bytecode é o processo de engenharia reversa do bytecode executável que representa as instruções de baixo nível de um smart contract. Aplicando ferramentas e algoritmos especializados, o bytecode é transformado de volta em uma forma mais legível por humanos que se assemelha à estrutura e lógica do código fonte original. Isso torna possível obter detalhes sobre a funcionalidade principal, detalhes de implementação e possíveis vulnerabilidades de um smart contract, apesar de não ter o código fonte original.

O decompilador Panoramix foi selecionado porque é ativamente suportado, open-source, estável e produz resultados aceitáveis. Panoramix converte bytecode EVM em pseudocódigo Python.

## Insights Importantes

### Vantagens do Método

Pode-se argumentar que o uso de block explorers é um método justificado para obter dados e informações úteis em um curto período de tempo usando uma pequena quantidade de recursos. Para ser preciso, não há necessidade de alugar servidores poderosos e configurar manualmente nós para cada rede blockchain e sincronizá-los por dias ou semanas.

Usando recursos mínimos, tornou-se possível coletar as informações necessárias, códigos fonte de smart contracts disponíveis e bytecodes implantados de várias redes blockchain para análise posterior. Depois disso, como exemplo, uma análise do contrato foi realizada com base nos dados coletados e no código fonte do contrato. A análise do smart contract forneceu informações sobre seu comportamento e papel, bem como os riscos de seu uso.

### Limitações Identificadas

O método proposto tem desvantagens. Se o servidor no qual o explorer está implantado for lento ou limitar artificialmente a velocidade, você terá que gastar mais tempo coletando os dados necessários. Às vezes, o nó blockchain usado pelo explorer pode não estar totalmente sincronizado e, como resultado, pode fornecer dados desatualizados. Além disso, nem todas as redes blockchain podem ter uma instância publicamente disponível do explorer escolhido.

Se alguma rede na área de pesquisa tiver os problemas listados, pode ser razoável implantar um nó blockchain local e explorer. Isso permitirá usar a mesma abordagem e evitar implementações diferentes. A principal limitação desta abordagem são as grandes redes blockchain, pois envolvem uma quantidade extremamente grande de dados. Neste caso, o block explorer será outra interface intermediária que introduz atraso. Portanto, é racional escolher outra técnica de recuperação de dados ou baixar apenas um conjunto previamente limitado de dados.

### Casos de Uso Ideais

O desenvolvimento desta pesquisa pode consistir em tipos expandidos de fontes de dados públicas, incluindo outros tipos de block explorers. Isso tornará possível suportar um número ainda maior de redes blockchain, receber dados mais rapidamente e ter fontes de backup, em caso de restrições ou desconexão das principais. Além disso, outra área de desenvolvimento desta pesquisa pode ser sua aplicação, nomeadamente, em varredura contínua e recuperação de dados. Isso tornará possível observar os parâmetros definidos de muitas redes blockchain em tempo real e, em caso de qualquer, receber notificações sobre essas mudanças.

## Relevância para Nossa Pesquisa

### Confirmações

Este artigo confirma várias hipóteses importantes para nossa pesquisa. Primeiro, confirma que block explorers são eficientes para análise de blockchain, permitindo coleta rápida de dados com recursos mínimos. Segundo, demonstra que múltiplas redes podem ser analisadas simultaneamente, o que é exatamente o que estamos fazendo em nossa pesquisa. Terceiro, prova que recursos mínimos são suficientes para análise eficaz, contrariando a crença de que são necessários recursos computacionais significativos.

O artigo também confirma que BlockScout é uma escolha sólida para análise, sendo open-source, suportando mais de 200 redes blockchain e fornecendo APIs robustas. Além disso, confirma que APIs são preferíveis ao web scraping, embora este último possa ser usado como fallback quando necessário.

### Gaps Identificados

A análise do artigo revela gaps significativos na literatura acadêmica sobre block explorers. Primeiro, não existem whitepapers técnicos específicos sobre arquitetura de block explorers. Segundo, a documentação arquitetural é limitada, com poucos detalhes sobre como os explorers são construídos internamente. Terceiro, benchmarks de performance são ausentes, dificultando comparações objetivas entre diferentes explorers.

Quarto, não existe análise comparativa sistemática entre explorers, limitando a compreensão de suas diferenças e semelhanças. Quinto, padrões de design não são documentados, dificultando o desenvolvimento de novos explorers ou a compreensão de como otimizar os existentes.

### Oportunidades

Estes gaps representam oportunidades únicas para nossa pesquisa. Podemos ser os primeiros a criar um whitepaper técnico sobre arquitetura de block explorers, fornecendo documentação detalhada sobre como eles funcionam internamente. Podemos realizar a primeira análise comparativa sistemática de block explorers, identificando padrões, diferenças e semelhanças.

Podemos desenvolver benchmarks de performance para diferentes explorers, permitindo comparações objetivas. Podemos documentar padrões de design comuns em block explorers, facilitando o desenvolvimento futuro. Finalmente, podemos criar um framework para desenvolvimento de block explorers, padronizando o processo e facilitando a criação de novos explorers.

## Conclusões do Artigo

### Principais Conclusões

1. Os principais estágios do método de usar block explorers para recuperação rápida simultânea de dados de muitas redes blockchain para análise de blockchain foram definidos, nomeadamente: escolher um block explorer; análise da arquitetura do sistema existente ou novo de análise de rede blockchain, no qual a implementação de software do método será integrada; determinação da técnica de comunicação com o block explorer; implementação de software de aquisição de dados de block explorers.

2. Block explorers existentes foram analisados e Blockscout foi selecionado como o ótimo para uso neste estudo. Este explorer está disponível para mais de 200 redes blockchain, é open-source e pode fornecer dados sobre um smart contract EVM implantado, incluindo seu bytecode, código fonte (se disponível) e detalhes de contrato proxy.

3. A arquitetura do sistema é proposta para obter dados de block explorers sobre smart contracts implantados na rede blockchain e para sua análise posterior. O sistema inclui uma série de blocos para aquisição de dados, processamento e armazenamento. A arquitetura prevê o uso do ChatGPT como assistente para análise de smart contracts.

4. Com base na arquitetura fornecida, um protótipo de sistema multi-threaded foi desenvolvido que torna possível receber dados simultaneamente de muitas redes blockchain usando instâncias publicamente disponíveis de block explorers. O sistema coleta dados sobre smart contracts para sua análise posterior. Os bytecodes dos smart contracts implantados são decompilados no processo.

5. A eficácia do método proposto foi testada usando o protótipo do sistema desenvolvido. Para as 14 redes blockchain fornecidas, dados foram coletados para análise de smart contracts das redes. Dados de contas foram coletados (incluindo estatísticas de saldo), smart contracts foram selecionados entre as contas, dados foram obtidos sobre tokens existentes (possuídos por smart contracts), bytecodes de contratos e seus códigos fonte (quando disponíveis) foram coletados e sua decompilação foi realizada. O processo levou quase 24 horas e custou até USD 1 para uma máquina de computação em nuvem selecionada com configuração mínima. Com base nos dados coletados, um smart contract aleatório foi analisado para ilustrar a completude do processo.

## Impacto Científico

### Validação da Hipótese

Este artigo valida nossa hipótese de que block explorers são viáveis para análise de blockchain. Demonstra que múltiplas redes podem ser analisadas simultaneamente com recursos mínimos, e que APIs são preferíveis ao web scraping. Os resultados mostram que é possível obter dados valiosos de block explorers sem a necessidade de sincronizar nós completos.

### Gaps na Literatura

O artigo revela gaps significativos na literatura acadêmica sobre block explorers. Não existem whitepapers sobre arquitetura de explorers, documentação arquitetural detalhada é limitada, benchmarks de performance são ausentes, e não há análise comparativa sistemática entre diferentes explorers.

### Oportunidade Única

Nossa pesquisa pode ser a primeira a documentar arquiteturas de block explorers, realizar análise comparativa sistemática, criar benchmarks de performance e desenvolver um framework para desenvolvimento de explorers. Esta é uma oportunidade única de contribuir significativamente para o campo.

## Conclusão

Este artigo é uma descoberta valiosa para nossa pesquisa. Confirma nossa hipótese de que block explorers são eficientes para análise de blockchain e identifica gaps únicos na literatura que podemos preencher. Os resultados do artigo fornecem uma base sólida para nossa pesquisa e demonstram que nossa abordagem é cientificamente válida e potencialmente inovadora.

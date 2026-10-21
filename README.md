# Integração e análise do Mundial 2026: jogadores e plantéis

Trabalho Prático I de Integração de Sistemas de Informação (ISI 2026/27)
Licenciatura em Engenharia de Sistemas Informáticos, EST/IPCA

**Autor:** João Castro nº 21143
**Plataforma:** KNIME Analytics Platform 5.12
**Enquadramento:** o tema é partilhado com um colega, que trata seleções e jogos
noutra plataforma. Este repositório contém apenas a minha parte (jogadores e plantéis).

## Problema
Integrar e analisar dados de jogadores e plantéis do Mundial de futebol de 2026
(golos, clubes, idades, melhores marcadores) através de um processo de ETL.

## Fontes de dados
Dataset *FIFA World Cup 2026* (MD Mominul Islam), licença CC0,
DOI 10.5281/zenodo.21592427.

| Formato | Ficheiro | Conteúdo |
|---|---|---|
| CSV | squads_and_players.csv | Jogadores e plantéis |
| CSV | teams.csv | Seleções |
| CSV | match_events.csv | Golos, cartões e outros eventos |
| CSV | match_lineups.csv | Convocatórias por jogo |
| CSV | player_stats.csv | Estatísticas por jogador |
| JSON | real_match_details.json | Detalhes dos jogos |

## Processo
1. **Extração (E):** leitura de CSV e JSON no KNIME.
2. **Transformação (T):** joins (jogadores + seleções, eventos + jogadores),
   conversão de tipos, cálculo da idade à data do torneio, deteção de duplicados,
   expressões regulares, filtros, agregações e ordenações.
3. **Carregamento (L):** exportação para CSV e JSON e persistência numa base
   de dados SQLite.

## Resultados
- Melhores marcadores do torneio (golos por jogador)
- Idade média por seleção

## Estrutura do repositório
- `Workflow_Final.knwf`: workflow completo (importar no KNIME)
- `Trabalho/Exports/`: ficheiros gerados (CSV, JSON e `mundial2026.db`)
- Ficheiros CSV e JSON na raiz: dados de origem
- `Fase1_...knwf` e `Fase2_...knwf`: versões intermédias do workflow

## Como abrir o workflow
1. No KNIME, importar o `Workflow_Final.knwf`.
2. Reapontar os nós de leitura (CSV e JSON) para os ficheiros deste repositório,
   porque os caminhos originais são do meu computador.
3. Executar com *Execute all*.

## Links
- https://youtu.be/2dviRSLltqY

## Referências
- MD Mominul Islam, *The FIFA World Cup 2026 Master Dataset*, Zenodo,
  DOI 10.5281/zenodo.21592427
- KNIME Analytics Platform: https://www.knime.com

# Integração e análise do Mundial 2026: jogadores e plantéis

**Unidade curricular:** Integração de Sistemas de Informação (ISI 2026/27)  
**Curso:** Licenciatura em Engenharia de Sistemas Informáticos, EST/IPCA  
**Autor:** João Castro — nº 21143  
**Plataforma:** KNIME Analytics Platform 5.12

## Objetivo
Integrar e analisar dados de jogadores e plantéis do Mundial de futebol de 2026 através de um processo ETL.

## Estrutura da entrega
- `doc/21143_doc.pdf` — relatório final.
- `doc/21143_relatorio_fonte.docx` — versão editável do relatório.
- `dataintegration/Workflow_Final.knwf` — workflow final do KNIME (transformações e orquestração do ETL).
- `data/input/` — dados de entrada: `squads_and_players.csv`, `teams.csv`, `match_events.csv`, `match_lineups.csv`, `player_stats.csv` e `real_match_details.json`.
- `data/output/` — dados de saída: `melhores_marcadores.csv`, `idade_media_selecoes.csv`, `idade_media_selecoes_0.json` e a base de dados SQLite `mundial2026.db`.
- `evidencias/` — capturas de ecrã, QR code e vídeo de demonstração.
- `src/` — não aplicável: a solução foi desenvolvida em KNIME e o workflow está em `dataintegration/`.

## Dados de entrada
Dataset *FIFA World Cup 2026* (MD Mominul Islam), licença CC0, DOI 10.5281/zenodo.21592427.

| Formato | Ficheiro | Conteúdo |
|---|---|---|
| CSV | `squads_and_players.csv` | Jogadores e plantéis |
| CSV | `teams.csv` | Seleções |
| CSV | `match_events.csv` | Golos, cartões e outros eventos |
| CSV | `match_lineups.csv` | Convocatórias por jogo |
| CSV | `player_stats.csv` | Estatísticas por jogador |
| JSON | `real_match_details.json` | Detalhes dos jogos |

## Como executar
1. Abrir o KNIME Analytics Platform 5.12 (ou versão compatível).
2. Importar `dataintegration/Workflow_Final.knwf`.
3. Nos nós de leitura (CSV Reader e JSON Reader), apontar os caminhos para os ficheiros de `data/input/`. Os caminhos originais são do computador do autor.
4. Nos nós de escrita (CSV Writer, JSON Writer e SQLite Connector), apontar os caminhos para `data/output/`.
5. Executar todos os nós (*Execute all*) e confirmar que os resultados são gerados sem erros.

## Resultados
- Melhores marcadores do torneio (golos por jogador).
- Idade média por seleção.
- Resultados exportados em CSV e JSON e guardados numa base de dados SQLite.

## Vídeo de demonstração
Link: https://youtu.be/2dviRSLltqY

## Referências
- MD Mominul Islam, *The FIFA World Cup 2026 Master Dataset*, Zenodo, DOI: 10.5281/zenodo.21592427.
- KNIME Analytics Platform: https://www.knime.com

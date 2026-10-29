# Fora da Curva 2026

Análise independente dos boletins de urna, dos logs e dos arquivos de recebimento publicados pelo TSE para o 1º turno (4/10/2026) e o 2º turno (25/10/2026) da eleição presidencial.

O trabalho separa o que é incomum do que seria prova. Site: https://foradacurva2026.github.io/eleicao2026

Todas as contas podem ser refeitas a partir dos arquivos públicos do TSE, seguindo o passo a passo em `metodo/COMO_REFAZER.md`.

## O que tem no pacote

| Pasta | Conteúdo |
|---|---|
| `index.html` | O site completo num arquivo só. Funciona sem internet, basta abrir no navegador. As fontes tipográficas usam o Google Fonts quando há conexão e, sem ela, caem nas fontes do sistema. |
| `dados/` | As tabelas usadas no site, em CSV com vírgula como separador e codificação UTF-8. Ver a lista abaixo. |
| `metodo/METODO.md` | Como cada número foi calculado, as hipóteses de cada item e os limites da análise. |
| `metodo/COMO_REFAZER.md` | Passo a passo para baixar os arquivos do TSE e refazer as contas principais. |
| `scripts/` | Scripts em Python para baixar os arquivos de recebimento, somar os totais e ler um boletim de urna. |

## Os dados

| Arquivo | O que é |
|---|---|
| `secoes_2026_dois_turnos.csv.zip` | Compactado por causa do tamanho (69 MB descompactado). Uma linha por seção (497.897): aptos, comparecimento e votos dos dois turnos, forma de liberação do eleitor no 2º turno, hora de encerramento da urna no 2º turno, data e hora de recebimento nos dois turnos e status do 2º turno. É a tabela-base. |
| `boletins_por_minuto.csv` | Boletins recebidos por minuto e região, e o placar acumulado, nos dois turnos. |
| `placar_ordem_inversa_por_minuto.csv` | O mesmo placar somando do último boletim para o primeiro. |
| `regioes_por_quarto_da_apuracao.csv` | Parte de cada região em cada quarto dos boletins recebidos. |
| `parada_1t_por_estado.csv` | Último boletim antes e primeiro depois da parada do 1º turno, por estado. |
| `secoes_registro_fora_do_padrao.csv` | As 13.383 seções com status "Recebida" no 2º turno ou com data de recebimento nos dias seguintes. |
| `encerramento_por_minuto.csv` | Seções e votos por minuto de encerramento da urna no 2º turno. |
| `prorrogacao_por_encerramento.csv` | Teste da prorrogação por faixa de horário de encerramento. |
| `ordem_de_chegada_decimos.csv` | Teste da ordem de chegada, por décimo dos boletins dentro de cada estado. |
| `fluxos_1t_para_2t.csv` | Estimativa de como os eleitores de cada grupo do 1º turno votaram no 2º. |
| `cenarios_sem_grupos.csv`, `cenarios_sem_grupos_por_estado.csv`, `cenarios_2006_2026.csv` | Simulações sem quem não votou ou votou branco/nulo no 1º turno. |
| `abstencionistas_por_estado.csv`, `estados_crescimento_e_chance.csv`, `estados_resumo.csv` | Indicadores por estado. |
| `itens.csv`, `itens_hipotese_x_observado.csv` | Os 11 itens, com hipótese, chance e valores. |
| `placares_*.csv`, `boletins_identicos_mesmo_local.csv` | Conferência de placares repetidos e boletins idênticos. |
| `secoes_voto_unico.csv` | Seções com votos para um só candidato. |
| `sem_biometria_por_hora.csv` | Votos liberados sem biometria por hora (estimativa a partir de logs). |

## Totais de conferência

- **2º turno, soma das seções no Brasil:** Lula 64.056.078 e Flávio 59.654.544. Com o exterior (200.154 e 171.497), dá exatamente o total oficial do TSE: 64.256.232 e 59.826.041 (arquivo `br-c0001-e006258-u.json`, gerado em 25/10/2026 às 23h27).
- **1º turno, soma das seções no Brasil:** Lula 53.721.918 e Flávio 55.960.361.

## Como citar

Fora da Curva 2026, análise dos arquivos públicos do TSE das eleições de 2026, versão de 29/10/2026.

## Licenças

Os dados de origem são públicos, do TSE. As tabelas derivadas, os textos e os scripts deste pacote estão em domínio público (CC0 1.0): podem ser copiados, alterados e republicados sem pedir permissão. Citar a fonte é bem-vindo, mas não obrigatório. O site inclui d3 (licença ISC) e d3-sankey (licença ISC). O desenho do mapa dos estados é de MapSVG, sob licença CC BY 4.0.

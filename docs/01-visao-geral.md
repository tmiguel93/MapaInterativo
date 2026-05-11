# Visão geral

O Mapa Interativo de Geração Distribuída é uma página estática para consulta rápida de disponibilidade comercial por empresa.

A aplicação permite:

- selecionar a empresa ativa;
- consultar estados atendidos;
- visualizar distribuidoras por UF;
- verificar DDDs;
- conferir disponibilidade e desconto base;
- usar busca por Estado, UF, DDD ou distribuidora;
- operar em desktop e mobile.

## Empresas

O sistema contempla três empresas:

- Matrix;
- Serena Energia;
- Inner Energia.

Cada empresa possui cor, regras comerciais, peculiaridades e conjunto próprio de estados/distribuidoras.

## Arquitetura

O projeto roda sem backend. Toda a lógica fica no arquivo `index.html`.

A estrutura atual usa:

- HTML para marcação;
- CSS interno para layout;
- JavaScript interno para dados, filtros e interação;
- CDN para o mapa vetorial do Brasil.

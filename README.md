# Mapa Interativo de Geração Distribuída

Aplicação estática em **HTML, CSS e JavaScript puro** para consulta comercial de regiões atendidas em Geração Distribuída. O painel permite alternar entre **Matrix**, **Serena Energia** e **Inner Energia**, exibindo dados por estado, distribuidora, DDD, disponibilidade, desconto base e observações comerciais.

O projeto foi pensado para rodar localmente ou publicado no GitHub Pages, sem backend e sem banco de dados.

## Funcionalidades

- Seletor de empresas: Matrix, Serena e Inner.
- Tema visual dinâmico por empresa.
- Mapa vetorial do Brasil com estados interativos.
- Estados atendidos coloridos com a cor da empresa ativa.
- Pop-in no hover/toque com resumo do estado.
- Painel lateral dinâmico por estado.
- Busca por Estado, UF, DDD e Distribuidora.
- Busca fixada em chip e limpeza automática do campo após pesquisar.
- Limpeza de filtro ao trocar de empresa para evitar mistura de dados.
- Tabela operacional para desktop.
- Cards responsivos para mobile.
- Adendo separado de Matrix Fácil, sem percentual automático em todas as regiões.
- Rodapé limpo contendo somente a data de atualização da empresa ativa.

## Empresas cadastradas

### Matrix

Critérios e observações principais:

- Consumo mínimo de 260 kWh sem considerar taxa de disponibilidade.
- Score mínimo 500.
- Fatura mínima de R$ 300,00.
- Matrix Fácil pode existir nas regiões atendidas pela Matrix.
- Percentual especial de Matrix Fácil aparece somente para:
  - CPFL Paulista: 20%.
  - COPEL: 20%.
  - Equatorial Alagoas: 25%.

### Serena Energia

Critérios e observações principais:

- Consumo mínimo de 250 kWh sem considerar taxa de disponibilidade.
- Sem fatura mínima.
- Necessário envio de login e senha da distribuidora.
- Necessário envio de RG ou CNH no ato do contrato.
- Condições variam por região, consumo e fidelidade.

### Inner Energia

Critérios e observações principais:

- Consumo mínimo de 300 kWh.
- Necessário envio de RG ou CNH.
- Distribuidoras atendidas: CPFL Paulista, CPFL Piratininga e Elektro.
- Desconto progressivo: 20% nos 3 primeiros meses, 15% do 4º ao 6º mês e 10% após o 6º mês.

## Como executar localmente

1. Baixe ou clone o repositório.
2. Abra o arquivo `index.html` no navegador.

```bash
git clone https://github.com/tmiguel93/MapaInterativo.git
cd MapaInterativo
```

Depois abra `index.html`.

> Observação: o mapa vetorial é carregado por CDN. Para o mapa aparecer com todos os estados, abra com internet ativa. Caso a CDN não carregue, o sistema mostra um fallback por UF.

## Como publicar no GitHub Pages

1. Acesse o repositório no GitHub.
2. Vá em **Settings > Pages**.
3. Em **Build and deployment**, selecione:
   - Source: `Deploy from a branch`.
   - Branch: `main`.
   - Folder: `/root`.
4. Salve.
5. O GitHub Pages irá gerar uma URL pública.

## Estrutura do projeto

```text
.
├── index.html
├── README.md
├── CHANGELOG.md
├── LICENSE.md
├── .gitignore
└── docs/
    ├── 01-visao-geral.md
    ├── 02-requisitos-funcionais.md
    ├── 03-modelo-de-dados.md
    ├── 04-guia-de-atualizacao.md
    ├── 05-guia-de-uso.md
    ├── 06-deploy-github-pages.md
    ├── 07-checklist-de-publicacao.md
    └── 08-prompt-codex-manutencao.md
```

## Manutenção dos dados

Os dados comerciais ficam dentro do objeto `companiesData`, no arquivo `index.html`. Para atualizar descontos, distribuidoras, disponibilidade ou observações, edite esse objeto com cuidado.

Principais pontos de atenção:

- **Baixa disponibilidade não significa ocupação total.**
- Não atribuir percentual de Matrix Fácil automaticamente para todos os estados.
- Percentual especial de Matrix Fácil deve aparecer apenas nos três casos definidos.
- Ao incluir uma distribuidora nova, revisar também o estado/UF, DDDs e observação comercial.

## Status

Versão estática funcional, pronta para publicação e uso comercial interno.

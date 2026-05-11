# Guia de atualização dos dados

Os dados ficam no objeto `companiesData`, dentro do `index.html`.

## Onde alterar

Procure por:

```js
const companiesData = {
```

Dentro dele existem os blocos:

- `matrix`
- `serena`
- `inner`

Cada empresa possui:

- `name`
- `color`
- `updatedAt`
- `desc`
- `tags`
- `peculiarities`
- `states`

## Como adicionar uma distribuidora

Dentro de `states`, adicione ou edite a UF desejada.

Exemplo conceitual:

```js
SP: [
  d('Nome da Distribuidora', 'Operando', 'alta', '20%', 'Observação comercial.')
]
```

## Disponibilidades aceitas

- `alta`
- `media`
- `baixa`
- `indisponivel`

## Cuidados importantes

- Baixa disponibilidade não deve ser tratada como ocupação total.
- Matrix Fácil deve aparecer como possibilidade, sem percentual automático.
- Percentual especial de Matrix Fácil deve aparecer somente nos casos mapeados.
- Após alterar dados, atualize também `updatedAt` da empresa.

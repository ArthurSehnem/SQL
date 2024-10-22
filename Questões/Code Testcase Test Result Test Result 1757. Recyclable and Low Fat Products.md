# Problema: Produtos

## Tabela: Products

| Column Name | Type    |
|-------------|---------|
| product_id  | int     |
| low_fats    | enum    |
| recyclable   | enum    |

- **product_id**: é a chave primária (coluna com valores únicos) para esta tabela.
- **low_fats**: é um ENUM (categoria) do tipo ('Y', 'N'), onde 'Y' significa que este produto é baixo em gordura e 'N' significa que não é.
- **recyclable**: é um ENUM (categoria) dos tipos ('Y', 'N'), onde 'Y' significa que este produto é reciclável e 'N' significa que não é.

## Objetivo

Escreva uma solução para encontrar os IDs dos produtos que são tanto baixos em gordura quanto recicláveis.

Retorne a tabela de resultados em qualquer ordem.

## Exemplo

**Entrada:**

Tabela Products:

| product_id | low_fats | recyclable |
|-------------|----------|------------|
| 0           | Y        | N          |
| 1           | Y        | Y          |
| 2           | N        | Y          |
| 3           | Y        | Y          |
| 4           | N        | N          |

**Saída:**

| product_id |
|-------------|
| 1           |
| 3           |

**Explicação:** Apenas os produtos 1 e 3 são ambos baixos em gordura e recicláveis.

## Solução

```sql
SELECT product_id 
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';

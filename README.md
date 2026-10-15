# TP1 — Pesquisa externa (Estrutura de Dados II)

> Trabalho prático em grupo da disciplina **BCC203 — Estrutura de Dados II** (Ciência da Computação, UFOP).
> Repositório original: [pedrosouzag/tp1-ED2](https://github.com/pedrosouzag/tp1-ED2).

Implementação e comparação de quatro métodos de **pesquisa em memória secundária** sobre um arquivo binário de registros. Para cada método, o programa mede o número de transferências (leituras), comparações de chaves e tempo de execução, nas fases de criação do índice e de pesquisa.

**Stack:** C (C99) · arquivos binários · gcc

## Métodos

| # | Método | Arquivo |
|---|---|---|
| 1 | Acesso sequencial indexado (índice de páginas) | `acessoSequencial.c` |
| 2 | Árvore binária de pesquisa em arquivo | `arvorebinaria.c` |
| 3 | Árvore B | `arvoreb.c` |
| 4 | Árvore B* | `arvorebestrela.c` |

Cada registro (`registro.h`) tem uma chave inteira, um `long` e um campo de texto de 5000 bytes, o que força o uso de disco em vez de memória.

## Compilar e executar

```bash
gcc *.c -o programa
./programa <metodo> <quantidade> <situacao> <chave> [-p]
./programa <metodo> <quantidade> <situacao> -t     # modo de testes
```

- `metodo`: 1 a 4 (tabela acima)
- `quantidade`: número de registros do arquivo
- `situacao`: 1 ordenado ascendente, 2 ordenado descendente, 3 aleatório
- `-p`: imprime as chaves do arquivo

Os arquivos de entrada estão no link de `arquivos/linkarquivos.txt`. Os resultados dos testes ficam em `testes/`, e a análise completa em `relatórioTP1.pdf`.

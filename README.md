# Tetris-em-HTML
Um clássico atemporal que todo mundo já ouviu falar.

## Como jogar

1. Baixe o arquivo `tetris.html`.
2. Abra no navegador (dois cliques no arquivo).
3. Clique em **Começar**.

Não precisa instalar nada nem ter internet.

## Controles

| Tecla | Ação |
|---|---|
| ← → | Mover a peça |
| ↑ | Girar |
| ↓ | Descer mais rápido (+1 ponto por linha descida) |
| Espaço | Queda direta (+2 pontos por linha descida) |
| P | Pausar / continuar |

Em telas de toque, use os botões abaixo do painel lateral.

## Regras

- O tabuleiro tem **10 colunas x 20 linhas**.
- Existem **7 peças**: I, O, T, S, Z, J e L, cada uma com uma cor.
- Uma linha completa some e as de cima descem.
- Uma "sombra" mostra onde a peça vai cair.
- O jogo termina quando uma peça nova não cabe no topo.

### Pontuação

| Linhas de uma vez | Pontos (x nível) |
|---|---|
| 1 | 100 |
| 2 | 300 |
| 3 | 500 |
| 4 (Tetris) | 800 |

### Níveis e velocidade

- O nível sobe a cada **10 linhas** eliminadas.
- A cada nível, a peça cai cerca de **18% mais rápido**:

```
intervalo_ms = max(50, 800 * 0.82 ** (nivel - 1))
```

## Como o código funciona

| Parte | O que faz |
|---|---|
| `board` | Matriz 20x10 com as peças já fixadas (`null` = vazio) |
| `SHAPES` | Matriz de cada peça (1 = bloco, 0 = vazio) |
| `hit()` | Checa colisão com as paredes, o chão e outras peças |
| `rot()` | Gira a matriz da peça em 90° |
| `lock()` | Fixa a peça, remove linhas completas e sorteia a próxima |
| `loop()` | Laço principal: faz a peça cair no ritmo do nível e redesenha a tela |

## Próximos Updates

- [ ] Guardar a maior pontuação
- [ ] Adicionar sons
- [ ] Criar tela de menu

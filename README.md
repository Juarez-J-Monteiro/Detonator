# Detonator

Jogo 2D baseado em grade, executado em interface de linha de comando (CLI), desenvolvido em Python como primeiro projeto com Programação Orientada a Objetos.

O jogador deve sobreviver o maior número possível de turnos em um campo explosivo, posicionando bombas e evitando inimigos.

---

## Como executar

Requer Python 3.

```bash
python main.py
```

---

## Como jogar

| Comando | Ação |
|--------|------|
| `w` `a` `s` `d` | Mover para cima, esquerda, baixo, direita |
| `b` | Posicionar bomba na célula atual |
| `r` | Ver resumo de partidas anteriores (apenas no início) |
| `q` | Sair |

### Símbolos do mapa

| Símbolo | Significado |
|---------|-------------|
| `J` | Jogador |
| `I` | Inimigo |
| `B` | Bomba |
| `#` | Obstáculo indestrutível |
| `$` | Obstáculo destrutível |
| `.` | Espaço vazio |

---

## Mecânicas

- **Bombas** explodem em cruz (cima, baixo, esquerda, direita), bloqueadas por obstáculos indestrutíveis
- **Inimigos** se movem automaticamente a cada turno e novos podem surgir ao longo da partida
- A partida termina em **fracasso** se o jogador for atingido por uma explosão ou inimigo
- A partida termina em **sucesso** se o jogador sobreviver todos os turnos

---

## Estado Persistente

O jogo mantém um arquivo `estado.json` que registra informações entre partidas:

- Número total de partidas jogadas
- Média de turnos sobrevividos
- Média de bombas utilizadas por partida
- Causa do término
- Turno em que o jogador foi eliminado
- Taxa de destruição de obstáculos

Com base nessas informações, o jogo ajusta automaticamente a dificuldade a cada nova execução, modificando:

- Quantidade inicial de inimigos
- Alcance das bombas
- Chance de surgimento de inimigos por turno
- Proporção de obstáculos destrutíveis no mapa

---

## Estrutura do projeto

```
├── main.py       # Ponto de entrada
├── jogo.py       # Lógica principal do jogo
├── jogador.py    # Classe do jogador
├── inimigo.py    # Classe do inimigo
├── bomba.py      # Classe da bomba
├── mapa.py       # Classe do mapa
└── estado.py     # Estado persistente entre partidas
```

---

## Sobre

Desenvolvido como projeto da disciplina de Programação com Interfaces Gráficas.

Primeiro projeto desenvolvido com Programação Orientada a Objetos.

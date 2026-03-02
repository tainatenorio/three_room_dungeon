# Three Room Dungeon

Jogo FPS em C++ com OpenGL/GLUT, com mapa em texto, inimigos com IA simples, boss e efeitos visuais.

## Requisitos
- `g++`
- `make`
- `freeglut`
- `glew`
- `OpenGL` (`libGL`, `libGLU`)
- `OpenAL`

No Ubuntu/Debian (exemplo):
```bash
sudo apt install build-essential freeglut3-dev libglew-dev libopenal-dev
```

## Build
```bash
make
```

Executável gerado em:
- `build/DoomLike`

## Executar
```bash
make run
```

## Controles
- `W A S D`: mover
- `I J K L`: olhar (teclado)
- Mouse: mirar
- Clique esquerdo / `U`: atacar
- `R` ou `O`: recarregar
- `Espaço`: pausar/retomar (em jogo)
- `Alt+Enter`: fullscreen
- `Esc`: sair

## Estados principais
- Menu inicial
- Jogando
- Pausado
- Cutscene de morte do boss
- Vitória

## Mapa (`maps/map1.txt`)
Cada caractere representa um elemento.

### Terreno
- `1`, `2`: parede
- `0`: chão
- `L`: lava
- `B`: sangue
- `9`: spawn do jogador

### Entidades
- Inimigos: `J`, `T`, `M`, `K`, `G`, `X` (boss)
- Itens: `H` (vida), `A` (munição), `Y` (chave)
- Portas: `D` (abre por kills), `Q` (abre com chave)

## Estrutura
- `src/core`: loop principal, estados, câmera, movimentação
- `src/graphics`: renderização 3D/HUD/menu
- `src/audio`: OpenAL
- `src/level`: carregamento de mapa e spawn de entidades
- `src/input`: teclado/mouse
- `assets`: texturas e áudio
- `shaders`: GLSL

## Limpeza de assets
Foi feita limpeza de arquivos não referenciados pelo código atual.

Resumo:
- Antes: `88` arquivos em `assets/`
- Depois: `51` arquivos em `assets/`
- Removidos: `37` arquivos não utilizados

Critério usado:
- referências explícitas em `src/`, `include/`, `main.cpp`, `Makefile`, `maps/` e scripts.


# Three Room Dungeon

Jogo FPS em C++ com OpenGL/GLUT, inimigos para enfrentar, três fases.

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/fc5ba30e-9ccc-4f39-9d6a-bd1c414ecfc5" />


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

## Gameplay
https://drive.google.com/drive/folders/19Y856qOWCtaGGsLoTb_sOsaIHNkFiL4y?usp=sharing

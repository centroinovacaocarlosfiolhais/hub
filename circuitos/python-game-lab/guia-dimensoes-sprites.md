# 🎨 Guia Completo: Sprites e Backgrounds Customizados

## 📐 DIMENSÕES RECOMENDADAS

### Tamanho Base das Células
**64x64 pixels** - Este é o tamanho de cada quadrado no mapa
- Podes mudar alterando `CELL_SIZE` no código
- Dimensões comuns: 32x32, 48x48, 64x64, 128x128

---

## 🖼️ SPRITES INDIVIDUAIS

### 1. **Player (Herói)** 
```
Dimensão recomendada: 48x48px (dentro de célula 64x64)
Offset: 8px do canto (para centralizar)
Formato: PNG com transparência
```

**Dicas:**
- Deixa margem de 8px em cada lado para não encostar nas bordas
- Usa transparência (alpha channel) para forma irregular
- Se for personagem, centrado e olhando para baixo/direita

### 2. **Treasure (Tesouro)**
```
Dimensão recomendada: 56x56px
Offset: 4px do canto
Formato: PNG com transparência
```

**Dicas:**
- Pode ser ligeiramente maior que o player
- Adiciona brilho ou efeito dourado
- Baú, troféu, coroa, estrela, etc.

### 3. **Gem (Gema/Colecionável)**
```
Dimensão recomendada: 40x40px
Offset: 12px do canto (bem centrado)
Formato: PNG com transparência
```

**Dicas:**
- Mais pequeno que outros objetos
- Cores vibrantes para destacar
- Cristal, moeda, fruta, diamante

### 4. **Wall (Parede)**
```
Dimensão recomendada: 64x64px (preenche toda a célula)
Offset: 0px
Formato: PNG ou JPG
```

**Dicas:**
- Deve preencher completamente o quadrado
- Padrão tileable (repete sem costuras)
- Pedra, tijolo, árvore, rocha

### 5. **Floor (Chão)**
```
Dimensão recomendada: 64x64px
Offset: 0px
Formato: PNG ou JPG
```

**Dicas:**
- Padrão tileable para repetir
- Textura subtil (grama, pedra, areia)
- Não muito chamativo (fundo neutro)

---

## 🗺️ MAPA DE FUNDO (Background)

### Opção 1: Padrão Repetido (Tile)
```
Dimensão: 64x64px, 128x128px ou 256x256px
Configuração: repeat: true
```

**Exemplo:**
```javascript
background: {
  url: 'https://exemplo.com/grass-tile.png',
  repeat: true  // Repete como padrão
}
```

**Ideal para:**
- Texturas de grama
- Piso de pedra
- Água
- Areia

### Opção 2: Imagem Completa (Esticada)
```
Dimensão: Largura do mapa × Altura do mapa em pixels
Para mapa 7×3: 448×192px (7×64 por 3×64)
Configuração: repeat: false
```

**Exemplo:**
```javascript
background: {
  url: 'https://exemplo.com/dungeon-background.png',
  repeat: false  // Estica para cobrir tudo
}
```

**Ideal para:**
- Cenário específico do nível
- Dungeon completa
- Paisagem custom

---

## 🛠️ COMO ADICIONAR AS TUAS SPRITES

### Método 1: URLs Online (Mais Fácil)

1. Faz upload das imagens para um host:
   - Imgur.com (grátis, fácil)
   - GitHub (se tiveres repo)
   - Google Drive (com link público)
   - Cloudinary (grátis até certo limite)

2. Copia o link direto da imagem

3. Cola no código:

```javascript
const SPRITE_CONFIG = {
  player: {
    url: 'https://i.imgur.com/SEU_LINK_AQUI.png',
    fallback: '🦸',
    size: { width: 48, height: 48 },
    offset: { x: 8, y: 8 }
  },
  treasure: {
    url: 'https://i.imgur.com/OUTRO_LINK.png',
    fallback: '🏆',
    size: { width: 56, height: 56 },
    offset: { x: 4, y: 4 }
  },
  // ... resto das sprites
}
```

### Método 2: Ficheiros Locais (Para desenvolvimento)

Se estiveres a correr localmente:

```javascript
player: {
  url: '/assets/sprites/hero.png',
  fallback: '🦸',
  size: { width: 48, height: 48 },
  offset: { x: 8, y: 8 }
}
```

Estrutura de pastas:
```
projeto/
├── public/
│   └── assets/
│       └── sprites/
│           ├── hero.png
│           ├── treasure.png
│           ├── gem.png
│           ├── wall.png
│           └── floor.png
└── src/
    └── aventura-python.jsx
```

---

## 🎨 FERRAMENTAS PARA CRIAR SPRITES

### Gratuitas e Online:
1. **Piskel** (piskelapp.com) - Pixel art, super fácil
2. **Photopea** (photopea.com) - Como Photoshop, grátis
3. **GIMP** - Download grátis, muito poderoso
4. **Pixlr** - Editor online rápido

### Para Pixel Art:
1. **Lospec** (lospec.com/pixel-editor)
2. **Make Pixel Art** (makepixelart.com)

### Para Criar Patterns/Tiles:
1. **Seamless Pattern Maker** (pycheung.com/checker)
2. **Pattern Ninja** (patterninja.com)

---

## 📦 RECURSOS GRÁTIS DE SPRITES

### Sites com sprites prontas:
1. **OpenGameArt.org** - Enorme biblioteca grátis
   - Procura: "64x64 sprites", "tileset", "character"
   
2. **Kenney.nl** - Assets de alta qualidade
   - Secção "Game Assets" → completamente grátis
   
3. **Itch.io** - Secção "Game Assets"
   - Muitos packs grátis de pixel art
   
4. **CraftPix.net** - Alguns assets grátis

### Packs recomendados para iniciantes:
- "Kenney's 1-Bit Pack" - minimalista
- "Tiny Dungeon" - temática medieval
- "Platformer Pack" - personagens simples

---

## 📋 TEMPLATE DE CONFIGURAÇÃO

### Tema Floresta Completo:
```javascript
const SPRITE_CONFIG = {
  player: {
    url: 'https://exemplo.com/fairy.png',
    fallback: '🧚',
    size: { width: 48, height: 48 },
    offset: { x: 8, y: 8 }
  },
  treasure: {
    url: 'https://exemplo.com/mushroom.png',
    fallback: '🍄',
    size: { width: 56, height: 56 },
    offset: { x: 4, y: 4 }
  },
  gem: {
    url: 'https://exemplo.com/flower.png',
    fallback: '🌸',
    size: { width: 40, height: 40 },
    offset: { x: 12, y: 12 }
  },
  wall: {
    url: 'https://exemplo.com/tree.png',
    fallback: '🌲',
    size: { width: 64, height: 64 },
    offset: { x: 0, y: 0 }
  },
  floor: {
    url: 'https://exemplo.com/grass.png',
    fallback: '🟩',
    size: { width: 64, height: 64 },
    offset: { x: 0, y: 0 }
  },
  background: {
    url: 'https://exemplo.com/forest-bg.png',
    repeat: true
  }
};
```

---

## ✅ CHECKLIST PARA SPRITES PERFEITAS

### Antes de usar:
- [ ] Imagem tem fundo transparente (PNG)?
- [ ] Dimensões corretas (64x64 ou conforme config)?
- [ ] Margem adequada para não encostar bordas?
- [ ] Cores se destacam no fundo?
- [ ] Se for tile, repete sem costuras?
- [ ] Testei no jogo e está centralizada?

### Otimização:
- [ ] Ficheiro < 100KB (para carregar rápido)
- [ ] Formato PNG para transparência
- [ ] JPG apenas para backgrounds sem transparência
- [ ] Comprimi as imagens (tinypng.com)

---

## 🎯 EXEMPLOS PRÁTICOS

### Exemplo 1: Dungeon Clássica
```javascript
// Sprites em tons de cinza/pedra
player: 48x48px - Cavaleiro com armadura
treasure: 56x56px - Baú de ouro
gem: 40x40px - Cristais azuis brilhantes
wall: 64x64px - Parede de pedra escura
floor: 64x64px - Piso de ladrilhos
background: Textura de pedra antiga (repeat: true)
```

### Exemplo 2: Espaço Sideral
```javascript
player: 48x48px - Nave espacial
treasure: 56x56px - Estrela dourada
gem: 40x40px - Asteroides coloridos
wall: 64x64px - Asteroides grandes
floor: 64x64px - Espaço estrelado (preto)
background: Nebulosa colorida (repeat: false)
```

### Exemplo 3: Oceano
```javascript
player: 48x48px - Peixe tropical
treasure: 56x56px - Âncora ou tesouro submerso
gem: 40x40px - Pérolas ou conchas
wall: 64x64px - Coral ou algas
floor: 64x64px - Areia do fundo do mar
background: Água azul com bolhas (repeat: true)
```

---

## 🚀 PRÓXIMOS PASSOS

1. **Escolhe um tema** (floresta, espaço, oceano, medieval, etc.)
2. **Procura sprites** nos sites recomendados ou cria as tuas
3. **Ajusta dimensões** para 64x64 (ou escolhido)
4. **Faz upload** para Imgur ou host da tua escolha
5. **Cola URLs** no SPRITE_CONFIG
6. **Testa** e ajusta offset se necessário
7. **Adiciona background** para dar vida ao jogo!

---

## 💡 DICAS FINAIS

**Para iniciantes:**
- Começa só com o player customizado
- Usa emojis para o resto inicialmente
- Vai adicionando sprites gradualmente

**Para melhor desempenho:**
- Mantém imagens pequenas (<50KB cada)
- Usa sprite sheets se tiveres muitas imagens
- Comprime PNGs com TinyPNG

**Para visual profissional:**
- Mantém estilo consistente entre sprites
- Usa paleta de cores coerente
- Adiciona pequenas animações (próximo passo!)

---

## 🎓 RECURSOS DE APRENDIZAGEM

**Tutoriais de Pixel Art:**
- YouTube: "Pixel Art Tutorial for Beginners"
- Blog: blog.studiominiboss.com/pixelart

**Teoria de Cores:**
- lospec.com/palette-list (paletas prontas)
- coolors.co (gerador de paletas)

**Inspiração:**
- Pinterest: "64x64 pixel art game"
- Dribbble: "game sprites"

---

**Boa sorte com o revamp visual! 🎨✨**

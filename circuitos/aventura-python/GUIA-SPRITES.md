# 🎨 Guia: Adicionar Sistema de Sprites Customizáveis

## 📋 O Que Vais Fazer

Transformar o jogo de emojis para suportar **sprites customizáveis** (imagens PNG/JPG).

**Tempo estimado:** 10-15 minutos  
**Dificuldade:** Fácil (copiar e colar)  
**Ficheiro a modificar:** `aventura-python-ALUNOS.html`

---

## 🔧 PASSO 1: Adicionar Configuração de Sprites

### Onde: Logo após a linha com `let isRunning = false;`

**Procura esta secção no código:**
```javascript
let isRunning = false;
let showInstr = true;
```

**Adiciona LOGO A SEGUIR:**
```javascript
// 🎨 CONFIGURAÇÃO DE SPRITES
const SPRITE_CONFIG = {
    player: {
        url: '',  // Deixa vazio para usar emoji, ou: 'https://i.imgur.com/abc123.png'
        emoji: '🦸',
        size: { w: 48, h: 48 },
        offset: { x: 1, y: 1 }
    },
    treasure: {
        url: '',
        emoji: '🏆',
        size: { w: 56, h: 56 },
        offset: { x: -3, y: -3 }
    },
    gem: {
        url: '',
        emoji: '💎',
        size: { w: 40, h: 40 },
        offset: { x: 5, y: 5 }
    },
    wall: {
        url: '',
        emoji: '🧱',
        size: { w: 64, h: 64 },
        offset: { x: -7, y: -7 }
    },
    floor: {
        url: '',
        emoji: '⚪',
        size: { w: 64, h: 64 },
        offset: { x: -7, y: -7 }
    },
    key: {
        url: '',
        emoji: '🔑',
        size: { w: 40, h: 40 },
        offset: { x: 5, y: 5 }
    },
    door: {
        url: '',
        emoji: '🚪',
        size: { w: 56, h: 56 },
        offset: { x: -3, y: -3 }
    },
    background: {
        url: '',  // Opcional: imagem de fundo
        mode: 'repeat'  // ou 'stretch'
    }
};

// Cache de imagens carregadas
const loadedSprites = {};

// Carregar sprites
function loadSprite(key, url) {
    if (!url || loadedSprites[key]) return;
    
    const img = new Image();
    img.onload = () => {
        loadedSprites[key] = img;
        drawGame(); // Re-render quando imagem carregar
    };
    img.onerror = () => {
        console.warn(`Falha ao carregar sprite: ${key}`);
    };
    img.src = url;
}

// Carregar todos os sprites ao iniciar
Object.keys(SPRITE_CONFIG).forEach(key => {
    const config = SPRITE_CONFIG[key];
    if (config.url) {
        loadSprite(key, config.url);
    }
});
```

---

## 🔧 PASSO 2: Modificar Função drawGame()

### Onde: Procura a função `function drawGame()`

**Procura esta linha:**
```javascript
function drawGame() {
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
```

**SUBSTITUI a função COMPLETA por esta versão:**

```javascript
function drawGame() {
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');
    const level = currentLevelData();
    const cellSize = 50;
    
    canvas.width = level.map[0].length * cellSize;
    canvas.height = level.map.length * cellSize;

    // Background
    if (SPRITE_CONFIG.background.url && loadedSprites.background) {
        if (SPRITE_CONFIG.background.mode === 'stretch') {
            ctx.drawImage(loadedSprites.background, 0, 0, canvas.width, canvas.height);
        } else {
            const pattern = ctx.createPattern(loadedSprites.background, 'repeat');
            ctx.fillStyle = pattern;
            ctx.fillRect(0, 0, canvas.width, canvas.height);
        }
    } else {
        ctx.fillStyle = '#1a1a2e';
        ctx.fillRect(0, 0, canvas.width, canvas.height);
    }

    // Função auxiliar para desenhar sprite ou emoji
    function drawSprite(key, x, y) {
        const config = SPRITE_CONFIG[key];
        const sprite = loadedSprites[key];
        
        if (sprite) {
            // Desenhar imagem
            const spriteX = x + config.offset.x;
            const spriteY = y + config.offset.y;
            ctx.drawImage(sprite, spriteX, spriteY, config.size.w, config.size.h);
        } else {
            // Fallback para emoji
            ctx.font = '32px Arial';
            ctx.textAlign = 'center';
            ctx.textBaseline = 'middle';
            ctx.fillText(config.emoji, x + cellSize/2, y + cellSize/2);
        }
    }

    // Desenhar mapa
    level.map.forEach((row, y) => {
        row.forEach((cell, x) => {
            const posX = x * cellSize;
            const posY = y * cellSize;

            // Sombra
            ctx.fillStyle = 'rgba(0,0,0,0.3)';
            ctx.fillRect(posX + 2, posY + 2, cellSize - 4, cellSize - 4);

            // Célula
            if (cell === 1) {
                // Parede
                drawSprite('wall', posX, posY);
            } else {
                // Chão
                drawSprite('floor', posX, posY);
            }

            // Gema (se não coletada)
            if (cell === 2 && !collected.includes(`${x},${y}`)) {
                drawSprite('gem', posX, posY);
            }

            // Tesouro
            if (cell === 3) {
                drawSprite('treasure', posX, posY);
            }

            // Chave (se não coletada)
            if (cell === 4 && !hasKey) {
                drawSprite('key', posX, posY);
            }

            // Porta
            if (cell === 5) {
                drawSprite('door', posX, posY);
            }
        });
    });

    // Desenhar jogador
    const centerX = playerPos.x * cellSize;
    const centerY = playerPos.y * cellSize;
    drawSprite('player', centerX, centerY);
}
```

---

## 🔧 PASSO 3: (Opcional) Adicionar Instruções no HTML

### Onde: Dentro da div com classe "instructions"

**Procura:**
```html
<div class="instructions" id="instructions">
```

**Adiciona ANTES do fechamento `</div>` das instruções:**
```html
<p style="color: #718096; font-size: 0.85em; margin-top: 10px;">
    🎨 Para usar sprites customizados, edita SPRITE_CONFIG no código
</p>
```

---

## ✅ PASSO 4: Testar

### Teste 1: Verificar que Ainda Funciona com Emojis
1. Guarda o ficheiro
2. Abre no browser
3. Joga um nível
4. Deve continuar a funcionar normalmente com emojis

### Teste 2: Adicionar Uma Sprite de Teste
1. No SPRITE_CONFIG, modifica o player:
```javascript
player: {
    url: 'https://i.imgur.com/yourimagehere.png',  // ← Coloca URL real aqui
    emoji: '🦸',
    size: { w: 48, h: 48 },
    offset: { x: 1, y: 1 }
},
```

2. Recarrega o browser
3. Se a imagem carregar, verás ela em vez do emoji
4. Se não carregar, volta ao emoji automaticamente

---

## 🎨 COMO USAR SPRITES

### Passo a Passo para Customizar:

#### 1. Prepara as Imagens
- **Herói:** 48×48 px (PNG transparente recomendado)
- **Tesouro:** 56×56 px
- **Gema:** 40×40 px
- **Parede/Chão:** 64×64 px
- **Chave:** 40×40 px
- **Porta:** 56×56 px

#### 2. Upload para Imgur (ou outro host)
1. Vai a https://imgur.com
2. Faz upload da imagem
3. Copia o link direto (termina em .png ou .jpg)
4. Exemplo: `https://i.imgur.com/abc123.png`

#### 3. Edita o SPRITE_CONFIG
```javascript
const SPRITE_CONFIG = {
    player: {
        url: 'https://i.imgur.com/abc123.png',  // ← Cola aqui
        emoji: '🦸',  // Mantém como fallback
        size: { w: 48, h: 48 },
        offset: { x: 1, y: 1 }
    },
    // ... resto
};
```

#### 4. Ajusta Offset (se necessário)
Se a imagem não fica centrada:
```javascript
offset: { x: 5, y: 5 }  // Move 5px para direita e baixo
offset: { x: -5, y: -5 }  // Move 5px para esquerda e cima
```

---

## 📐 DIMENSÕES RECOMENDADAS

### Tamanhos Ideais:
| Elemento | Tamanho | Offset Padrão |
|----------|---------|---------------|
| Herói | 48×48 | {x: 1, y: 1} |
| Tesouro | 56×56 | {x: -3, y: -3} |
| Gema | 40×40 | {x: 5, y: 5} |
| Parede | 64×64 | {x: -7, y: -7} |
| Chão | 64×64 | {x: -7, y: -7} |
| Chave | 40×40 | {x: 5, y: 5} |
| Porta | 56×56 | {x: -3, y: -3} |

### Formato:
- ✅ **PNG** com transparência (recomendado)
- ✅ **JPG** (para backgrounds)
- ✅ **GIF** animado (funciona!)

---

## 🖼️ EXEMPLO COMPLETO

```javascript
const SPRITE_CONFIG = {
    player: {
        url: 'https://i.imgur.com/player.png',
        emoji: '🦸',
        size: { w: 48, h: 48 },
        offset: { x: 1, y: 1 }
    },
    treasure: {
        url: 'https://i.imgur.com/treasure.png',
        emoji: '🏆',
        size: { w: 56, h: 56 },
        offset: { x: -3, y: -3 }
    },
    gem: {
        url: 'https://i.imgur.com/gem.png',
        emoji: '💎',
        size: { w: 40, h: 40 },
        offset: { x: 5, y: 5 }
    },
    wall: {
        url: 'https://i.imgur.com/wall.png',
        emoji: '🧱',
        size: { w: 64, h: 64 },
        offset: { x: -7, y: -7 }
    },
    floor: {
        url: 'https://i.imgur.com/floor.png',
        emoji: '⚪',
        size: { w: 64, h: 64 },
        offset: { x: -7, y: -7 }
    },
    key: {
        url: 'https://i.imgur.com/key.png',
        emoji: '🔑',
        size: { w: 40, h: 40 },
        offset: { x: 5, y: 5 }
    },
    door: {
        url: 'https://i.imgur.com/door.png',
        emoji: '🚪',
        size: { w: 56, h: 56 },
        offset: { x: -3, y: -3 }
    },
    background: {
        url: 'https://i.imgur.com/background.jpg',
        mode: 'stretch'  // ou 'repeat'
    }
};
```

---

## 🎯 SPRITES PRONTAS PARA USAR

### Opção 1: Pixel Art (Retro)
```
Herói: https://opengameart.org/content/...
Tesouro: https://opengameart.org/content/...
```

### Opção 2: Cartoon Style
```
Kenny Assets: https://kenney.nl/assets
(Grátis para uso educacional)
```

### Opção 3: Criar as Tuas
- **Piskel:** https://www.piskelapp.com (online, grátis)
- **Aseprite:** https://www.aseprite.org (pago)
- **Photopea:** https://www.photopea.com (grátis, tipo Photoshop)

---

## 🔍 TROUBLESHOOTING

### Sprite não aparece
**Problema:** URL errado ou imagem não carrega  
**Solução:**
1. Abre console (F12)
2. Vê mensagem: `Falha ao carregar sprite: player`
3. Verifica URL está correto
4. Testa URL no browser diretamente

### Sprite descentrada
**Problema:** Imagem não alinha com célula  
**Solução:**
Ajusta offset:
```javascript
offset: { x: 10, y: 5 }  // Tenta diferentes valores
```

### Sprite muito grande/pequena
**Problema:** Tamanho errado  
**Solução:**
Ajusta size:
```javascript
size: { w: 40, h: 40 }  // Reduz tamanho
size: { w: 60, h: 60 }  // Aumenta tamanho
```

### Emojis voltam a aparecer
**Motivo:** Fallback automático quando sprite não carrega  
**É normal!** O jogo funciona com ou sem sprites.

---

## 💡 DICAS AVANÇADAS

### Modo Offline
Se quiseres que funcione sem internet:
1. Descarrega as imagens
2. Coloca na mesma pasta do HTML
3. Usa URLs relativas:
```javascript
url: './sprites/player.png'
```

### Animações
GIFs animados funcionam:
```javascript
player: {
    url: 'https://i.imgur.com/animated-player.gif',
    // ... resto
}
```

### Background Pattern
Para padrão repetido:
```javascript
background: {
    url: 'https://i.imgur.com/tile-pattern.png',
    mode: 'repeat'  // Repete como tile
}
```

---

## ✅ CHECKLIST DE IMPLEMENTAÇÃO

- [ ] Passo 1: Adicionar SPRITE_CONFIG
- [ ] Passo 2: Modificar drawGame()
- [ ] Passo 3: (Opcional) Adicionar instruções HTML
- [ ] Passo 4: Testar com emojis
- [ ] Passo 5: Adicionar URL de teste
- [ ] Passo 6: Verificar que carrega
- [ ] Passo 7: Ajustar offset se necessário
- [ ] Passo 8: Adicionar todas as sprites
- [ ] Passo 9: Testar todos os níveis
- [ ] Passo 10: Partilhar com alunos!

---

## 🎨 RECURSOS ÚTEIS

### Sites de Sprites Grátis:
- **OpenGameArt:** https://opengameart.org
- **Kenney:** https://kenney.nl/assets
- **itch.io:** https://itch.io/game-assets/free
- **Craftpix:** https://craftpix.net/freebies

### Editores:
- **Piskel:** https://www.piskelapp.com
- **Photopea:** https://www.photopea.com
- **GIMP:** https://www.gimp.org

### Upload de Imagens:
- **Imgur:** https://imgur.com (recomendado)
- **ImgBB:** https://imgbb.com
- **Cloudinary:** https://cloudinary.com

---

## 📞 PRECISAS DE AJUDA?

### Se ficares preso:
1. Abre console (F12)
2. Vê mensagens de erro
3. Verifica URLs das imagens
4. Testa uma sprite de cada vez

### Exemplo de Debug:
```javascript
// No console do browser:
console.log(SPRITE_CONFIG);
console.log(loadedSprites);
```

---

## 🎉 ESTÁ FEITO!

Agora tens um jogo com:
- ✅ Sistema de sprites customizáveis
- ✅ Fallback automático para emojis
- ✅ Suporte para imagens online ou offline
- ✅ Fácil de personalizar

**Diverte-te a customizar o teu jogo! 🎨**

---

**Versão:** Guia de Sprites v1.0  
**Compatível com:** aventura-python-ALUNOS.html v2.1  
**Tempo de implementação:** 10-15 min  
**Dificuldade:** ⭐⭐☆☆☆ (Fácil)

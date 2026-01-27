# 🏆 Aventura Python - CICF

![Python](https://img.shields.io/badge/Python-Game-blue)
![HTML5](https://img.shields.io/badge/HTML5-CSS3-orange)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)
![Status](https://img.shields.io/badge/Status-Ready-green)

**Jogo educativo interativo para ensinar Python a jovens dos 10-15 anos através de desafios progressivos de programação.**

Criado para o **CICF - Clube de Código** | Professor: **Carlos Fiolhais**

---

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Características](#características)
- [Estrutura do Programa](#estrutura-do-programa)
- [Ficheiros do Projeto](#ficheiros-do-projeto)
- [Como Usar](#como-usar)
- [Credenciais e Passwords](#credenciais-e-passwords)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Guia do Professor](#guia-do-professor)
- [Troubleshooting](#troubleshooting)
- [Changelog](#changelog)
- [Créditos](#créditos)
- [Licença](#licença)

---

## 📖 Sobre o Projeto

**Aventura Python** é um jogo educativo que ensina programação Python de forma visual e interativa, inspirado em jogos como Ozaria/CodeCombat. Os alunos controlam um herói num mundo virtual escrevendo código Python real.

### 🎯 Objetivos Pedagógicos

- Introduzir conceitos de programação de forma lúdica
- Ensinar Python através da prática
- Desenvolver pensamento computacional
- Progressão gradual de dificuldade (scaffolding)
- Feedback imediato visual

### 👥 Público-Alvo

- **Idade:** 10-15 anos
- **Nível:** Iniciantes em programação
- **Contexto:** Clube de programação escolar
- **Duração:** 4 sessões × 1h30 = 6 horas totais

---

## ✨ Características

### Para Alunos (aventura-python-ALUNOS.html)

- ✅ **9 níveis progressivos** organizados em 4 sessões
- ✅ **Editor Python integrado** com syntax highlighting
- ✅ **Mundo visual** renderizado em canvas
- ✅ **Sistema de passwords** para saltar níveis
- ✅ **Password visível** no placeholder do nível atual
- ✅ **Feedback imediato** via console de jogo
- ✅ **Mecânicas especiais**: chave e porta
- ✅ **Celebração final** com confetti e modal
- ✅ **Funciona offline** sem necessidade de servidor

### Para Professores (aventura-python-PROFESSOR.html)

- ✅ **Sistema de login** seguro (user: `cicf`, pass: `CarlosFiolhais`)
- ✅ **Interface profissional** com navegação por níveis
- ✅ **Soluções completas** de todos os níveis
- ✅ **Explicações passo a passo** detalhadas
- ✅ **Conceitos pedagógicos** a ensinar por nível
- ✅ **Erros comuns** dos alunos identificados
- ✅ **Dicas de ensino** específicas
- ✅ **Durações estimadas** por nível
- ✅ **Acesso via botão** no jogo dos alunos

---

## 📚 Estrutura do Programa

### Sessão 1: Movimento Básico (1h30)
**Conceitos:** Comandos, sequências, ciclos for

| Nível | Título | Password | Duração | Conceito Principal |
|-------|--------|----------|---------|-------------------|
| 1 | Primeiro Passo | `INICIO2025` | 20 min | Comandos básicos |
| 2 | Caminho em L | `CURVA2025` | 25 min | Combinação de direções |
| 3 | Usa Ciclos | `LOOP2025` | 45 min | Ciclos for, range() |

### Sessão 2: Ciclos e Repetição (1h30)
**Conceitos:** Loops complexos, coleção de items

| Nível | Título | Password | Duração | Conceito Principal |
|-------|--------|----------|---------|-------------------|
| 4 | Padrão em Escada | `ESCADA2025` | 35 min | Múltiplos comandos no loop |
| 5 | Coleta Todas as Gemas | `GEMAS2025` | 55 min | Loops + ações combinadas |

### Sessão 3: Condições e Decisões (1h30)
**Conceitos:** If/else, booleanos, verificações

| Nível | Título | Password | Duração | Conceito Principal |
|-------|--------|----------|---------|-------------------|
| 6 | Decisão no Caminho | `DECISAO2025` | 40 min | Condições if |
| 7 | Chave e Porta | `PORTA2025` | 50 min | Estado, interação com objetos |

### Sessão 4: Funções e Desafios (1h30)
**Conceitos:** Definição de funções, abstração

| Nível | Título | Password | Duração | Conceito Principal |
|-------|--------|----------|---------|-------------------|
| 8 | Cria uma Função | `FUNCAO2025` | 45 min | Definição e reutilização |
| 9 | Desafio Final | `MESTRE2025` | 45 min | Integração de todos conceitos |

---

## 📁 Ficheiros do Projeto

```
aventura-python/
│
├── 🎮 FICHEIROS PRINCIPAIS
│   ├── aventura-python-ALUNOS.html          # Jogo principal (1338 linhas)
│   └── aventura-python-PROFESSOR.html       # Guião interativo (768 linhas)
│
├── 📖 DOCUMENTAÇÃO
│   ├── README.md                            # Este ficheiro
│   ├── MANUAL-COMPLETO.md                   # Manual detalhado
│   ├── GUIAO-PROFESSOR.md                   # Guião em Markdown
│   ├── PASSWORDS.md                         # Lista de passwords
│   ├── CELEBRACAO-FINAL.md                  # Info sobre celebração
│   ├── TROUBLESHOOTING.md                   # Resolução de problemas
│   └── VERSAO-FINAL-COMPLETA.md            # Resumo de features
│
├── 🔧 FICHEIROS DE REFERÊNCIA
│   ├── README-VERSOES.md                    # Diferenças entre versões
│   ├── IMPLEMENTACAO.md                     # Notas técnicas
│   ├── MELHORIAS-SESSAO3.md                # Documentação Sessão 3
│   └── CORRECAO-BUG.md                     # Histórico de bugs
│
└── 🗂️ BACKUP
    └── aventura-python.html                 # Versão original (referência)
```

---

## 🚀 Como Usar

### Para Alunos

1. **Abrir o Jogo**
   - Duplo-clique em `aventura-python-ALUNOS.html`
   - OU arrasta para o browser
   - OU browser → File → Open

2. **Jogar**
   - Lê o objetivo do nível
   - Escreve código Python no editor
   - Clica "▶️ Executar"
   - Vê o resultado no mundo e no console

3. **Avançar de Nível**
   - Completa o objetivo → Avança automaticamente
   - OU usa password para saltar: escreve no campo → Enter

4. **Ver Password do Nível Atual**
   - Está visível no placeholder: `Password deste nível: PORTA2025`

### Para Professores

**Opção A: Via Botão no Jogo**
1. Abrir `aventura-python-ALUNOS.html`
2. Clicar botão "👨‍🏫 Guião Professor"
3. Login: `cicf` / `CarlosFiolhais`
4. Navegar pelos níveis na barra lateral

**Opção B: Direto**
1. Abrir `aventura-python-PROFESSOR.html`
2. Login: `cicf` / `CarlosFiolhais`
3. Aceder a todas as soluções e dicas

---

## 🔑 Credenciais e Passwords

### Guião de Professor
```
Utilizador: cicf
Password:   CarlosFiolhais
```
**Nota:** Case-sensitive! `cicf` em minúsculas, `C` e `F` maiúsculas.

### Passwords dos Níveis

| Nível | Password | Sessão |
|-------|----------|---------|
| Primeiro Passo | `INICIO2025` | 1 |
| Caminho em L | `CURVA2025` | 1 |
| Usa Ciclos | `LOOP2025` | 1 |
| Padrão em Escada | `ESCADA2025` | 2 |
| Coleta Todas as Gemas | `GEMAS2025` | 2 |
| Decisão no Caminho | `DECISAO2025` | 3 |
| Chave e Porta | `PORTA2025` | 3 |
| Cria uma Função | `FUNCAO2025` | 4 |
| Desafio Final | `MESTRE2025` | 4 |

**Todas em MAIÚSCULAS, ano 2025.**

---

## 🛠️ Tecnologias Utilizadas

### Frontend
- **HTML5** - Estrutura
- **CSS3** - Estilização (gradientes, animações)
- **JavaScript ES6** - Lógica do jogo
- **Canvas API** - Renderização gráfica

### Bibliotecas Externas
- **canvas-confetti** v1.6.0 - Celebração final
  - CDN: `jsdelivr.net`
  - Tamanho: ~10KB
  - Opcional (funciona sem se offline)

### Features Técnicas
- ✅ Interpretador Python simplificado em JS
- ✅ Sistema de detecção de colisões
- ✅ State management para chave/porta
- ✅ Animações CSS puras
- ✅ Responsive design
- ✅ Zero dependências críticas

---

## 💾 Instalação

### Requisitos
- ✅ Browser moderno (Chrome, Firefox, Edge, Safari)
- ✅ JavaScript habilitado
- ⚠️ Ligação à internet (opcional, só para confetti)

### Passos

1. **Download**
   ```bash
   # Opção 1: Clone do repositório (se aplicável)
   git clone [url-do-repo]
   
   # Opção 2: Download direto
   # Descarrega os ficheiros HTML
   ```

2. **Abrir**
   - Navega até à pasta
   - Duplo-clique em `aventura-python-ALUNOS.html`
   - Ou arrasta para o browser

3. **Começar**
   - Jogo abre imediatamente
   - Não precisa de instalação
   - Funciona offline (exceto confetti)

### Para Sala de Aula

**Opção A: Individual**
- Cada aluno abre no seu PC/tablet
- Ficheiros podem estar numa pen USB
- Ou em pasta partilhada da rede

**Opção B: Servidor Local**
```bash
# Python 3
python -m http.server 8000

# Ou Node.js
npx http-server
```
Aceder via: `http://localhost:8000`

---

## 👨‍🏫 Guia do Professor

### Antes da Aula

1. **Preparação** (15 min)
   - Abrir `aventura-python-PROFESSOR.html`
   - Login: `cicf` / `CarlosFiolhais`
   - Rever nível que vai ensinar
   - Ler conceitos e dicas

2. **Material Necessário**
   - PCs/tablets para alunos (1 por aluno ideal)
   - Projetor (opcional, para demonstrações)
   - Ficheiro `aventura-python-ALUNOS.html` distribuído

### Durante a Aula

1. **Introdução** (10 min)
   - Explicar objetivo do nível
   - Demonstrar conceitos novos
   - Mostrar exemplo simples

2. **Prática Guiada** (20-30 min)
   - Alunos tentam resolver
   - Circular pela sala
   - Dar dicas sem revelar solução

3. **Suporte** (conforme necessário)
   - Alunos presos → dar password
   - Erros comuns → explicar
   - Consultar guião para dicas

4. **Discussão** (10 min)
   - Rever soluções diferentes
   - Destacar boas práticas
   - Consolidar conceitos

### Gestão de Passwords

**Estratégia Recomendada:**
- ✅ NÃO dar todas as passwords no início
- ✅ Password visível = fácil de partilhar entre alunos
- ✅ Incentivar colaboração
- ✅ Usar passwords para desbloquear alunos muito presos
- ✅ Últimos 10 min → dar password para garantir progresso

---

## 🔧 Troubleshooting

### Jogo não abre
**Problema:** Duplo-clique não funciona  
**Solução:** 
- Botão direito → Abrir com → Browser
- Ou arrasta ficheiro para janela do browser

### Código não executa
**Problema:** Clicar "Executar" não faz nada  
**Solução:**
- Abre console (F12) → vê erros
- Verifica sintaxe Python (indentação!)
- Reset do nível pode ajudar

### Password não funciona
**Problema:** Escrevo password mas nada acontece  
**Solução:**
- Verifica MAIÚSCULAS: `PORTA2025` não `porta2025`
- Pressiona Enter ou clica botão
- Sem espaços antes/depois

### Login do professor não funciona
**Problema:** Credenciais rejeitadas  
**Solução:**
- User: `cicf` (minúsculas)
- Password: `CarlosFiolhais` (C e F maiúsculas)
- Case-sensitive!

### Celebração final não aparece
**Problema:** Completo último nível mas sem confetti/modal  
**Solução:**
- Abre console (F12)
- Verifica mensagens de erro
- Testa manual: `celebrateVictory()` no console
- Confetti precisa de internet (CDN)

### Detalhes Técnicos
Ver `TROUBLESHOOTING.md` para mais detalhes.

---

## 📝 Changelog

### Versão 2.1 (Final) - 27/01/2026
- ✅ Celebração final com confetti
- ✅ Modal de vitória ao completar todos níveis
- ✅ Logs de debug no console
- ✅ Fallback para confetti offline

### Versão 2.0 - 27/01/2026
- ✅ Sistema de passwords por nível
- ✅ Password visível no placeholder
- ✅ Guião de professor em HTML
- ✅ Sistema de login integrado
- ✅ Botão para aceder guião no jogo
- ✅ Todos os bugs corrigidos

### Versão 1.2 - 27/01/2026
- ✅ Mecânica de chave e porta
- ✅ Nível "Chave e Porta" completamente redesenhado
- ✅ Novas funções API: pegar_chave(), tem_chave(), abrir_porta()

### Versão 1.1 - 27/01/2026
- ✅ Correção bug Sessão 2 Nível 2 (tesouro em falta)
- ✅ Mapa expandido de 7×3 para 8×3

### Versão 1.0 - 27/01/2026
- ✅ Jogo base funcional
- ✅ 9 níveis em 4 sessões
- ✅ Editor Python integrado
- ✅ Renderização canvas

---

## 🎨 Funcionalidades Especiais

### Sistema de Chave e Porta 🔑🚪
- Nível 7 introduz mecânica de estado
- Chave deve ser coletada antes
- Porta muda de cor (vermelho → verde)
- Ensina persistência de estado

### Celebração Final 🎉
- Dispara ao completar nível 9
- Confetti por 5 segundos
- Modal com mensagem motivadora
- Estatísticas do jogo
- Música/som (futuro)

### Sistema de Passwords 🔐
- Password única por nível
- Visível no placeholder
- Salto direto para qualquer nível
- Facilita testes e demos

---

## 📊 Estatísticas do Projeto

- **Linhas de Código:** ~2100+ (HTML + CSS + JS)
- **Níveis:** 9 distribuídos em 4 sessões
- **Comandos Python:** 12+ (direita, baixo, coletar, ver_*, etc)
- **Tempo Estimado:** 6 horas (4 sessões × 1.5h)
- **Idade-Alvo:** 10-15 anos
- **Mecânicas:** Movimento, coleção, chave/porta, ciclos, condições, funções
- **Browser Compatibility:** Chrome, Firefox, Edge, Safari
- **Offline:** ✅ Funciona (exceto confetti)

---

## 🎓 Objetivos de Aprendizagem

Ao completar o programa, os alunos conseguem:

### Conceitos Fundamentais
- ✅ Escrever e executar código Python
- ✅ Usar comandos sequenciais
- ✅ Compreender ordem de execução

### Estruturas de Controlo
- ✅ Criar e usar ciclos `for`
- ✅ Utilizar `range()` corretamente
- ✅ Aplicar condições `if/else`
- ✅ Combinar múltiplas estruturas

### Funções e Abstração
- ✅ Definir funções com `def`
- ✅ Chamar funções
- ✅ Reutilizar código
- ✅ Compreender abstração

### Resolução de Problemas
- ✅ Decompor problemas complexos
- ✅ Planear antes de codificar
- ✅ Debug e correção de erros
- ✅ Testar soluções

---

## 👥 Créditos

### Desenvolvimento
- **Criado por:** Claude (Anthropic)
- **Professor Responsável:** Carlos Fiolhais
- **Instituição:** CICF - Clube de Código
- **Data:** Janeiro 2026

### Inspiração
- **CodeCombat** - Mecânicas de jogo
- **Ozaria** - Interface e progressão
- **Scratch** - Pedagogia visual

### Bibliotecas
- **canvas-confetti** by Kiril Vatev
- **Canvas API** (Web Standard)

### Testadores
- Alunos do CICF (futuros)

---

## 📄 Licença

**Uso Educacional Livre**

Este projeto foi criado especificamente para o CICF e pode ser usado livremente em contextos educacionais:

✅ **Permitido:**
- Usar em sala de aula
- Modificar para necessidades específicas
- Partilhar com outros educadores
- Adaptar conteúdos

❌ **Não Permitido:**
- Uso comercial sem autorização
- Redistribuição sem créditos
- Remoção de atribuições

**Contacto para outras utilizações:** [via CICF]

---

## 🚀 Roadmap Futuro (Opcional)

Possíveis melhorias para versões futuras:

### Versão 3.0 (Potencial)
- [ ] Sistema de save/load de progresso
- [ ] Leaderboard de turma
- [ ] Mais níveis e desafios
- [ ] Som e música
- [ ] Modo multiplayer
- [ ] Certificado digital de conclusão
- [ ] Analytics de tempo/tentativas
- [ ] Tema escuro/claro
- [ ] Suporte para outras línguas
- [ ] Mobile-first design melhorado

### Features Pedagógicas
- [ ] Vídeos explicativos por conceito
- [ ] Quiz de compreensão
- [ ] Badges de conquistas
- [ ] Sistema de hints progressivos
- [ ] Modo "desafio" com tempo limite

---

## 📞 Suporte e Contacto

### Para Bugs/Problemas
1. Consulta `TROUBLESHOOTING.md`
2. Abre console do browser (F12)
3. Reporta com screenshots/logs

### Para Dúvidas Pedagógicas
1. Consulta `GUIAO-PROFESSOR.md`
2. Lê secção de "Dicas para o Professor"
3. Contacta via CICF

### Para Melhorias/Sugestões
- Feedback bem-vindo!
- Testa com alunos e reporta
- Ideias para novos níveis sempre apreciadas

---

## 🎉 Agradecimentos

Obrigado por usar **Aventura Python**!

Esperamos que este jogo inspire a próxima geração de programadores. 🐍✨

**Boas aulas e boa sorte! 🚀**

---

<div align="center">

**Versão 2.1 Final**

Criado com ❤️ para o CICF

Janeiro 2026

![Python](https://img.shields.io/badge/Made%20with-Python-blue)
![Education](https://img.shields.io/badge/For-Education-green)
![Fun](https://img.shields.io/badge/Learning-Fun-yellow)

</div>

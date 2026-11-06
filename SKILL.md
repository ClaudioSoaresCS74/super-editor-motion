---
name: super-editor-motion
description: >-
  Use before any motion, video, Reel, animated carousel, typography motion, 3D,
  camera prompt or reference-style job: picks the right specialist skills
  without overlap, builds one combined plan, and runs production with public
  tools (HyperFrames, Remotion, ffmpeg, Whisper).
---
# Super Editor Motion

Skill mestre de audiovisual. Escolhe só as especialistas necessárias, sem repetir função, e monta um plano único. Feita para quem cria com IA sem programar: o agente orquestra, as skills e CLIs fazem o trabalho pesado.

## 0. Como rodar (economia de esforço)

- O agente só orquestra: define o caminho, manda a tarefa e revisa.
- Roteiro, código de animação, HTML/GSAP e render vão para um CLI de código (Claude Code, Codex ou equivalente) no seu computador, citando as skills escolhidas pelo nome.
- Reaproveite imagens e render em código antes de gerar mídia nova.
- Prefira HyperFrames (Apache 2.0) para motion graphics. Remotion é alternativa válida (licença paga para empresas com mais de 3 pessoas; use se já tiver licença ou for uso individual).
- Corte, concatenação e queima de legenda final: ffmpeg.
- Transcrição: faster-whisper (ou Whisper), com timestamps por palavra.

## 1. Antes de começar

- Formato (Reel 9:16, carrossel 4:5, vídeo longo, web), duração, objetivo, público.
- Checklist de pronto: voz limpa, fatos conferidos, paleta e fonte da sua marca (veja `efeitos-por-comando/brand-kit.md` e troque pelos seus valores).

## 2. Roteamento (uma principal por função)

Use skills públicas quando estiverem instaladas. Uma principal por função; complementos só se precisar.

| Trabalho | Principal | Complementos só se precisar |
|---|---|---|
| Roteiro e gancho de Reel | briefing próprio / copy | motion-design (timing) |
| Tipografia em movimento | motion-design + gsap-timeline | gsap-plugins (SplitText) em HTML |
| Carrossel animado / slides HTML | gsap-core + stageshow | gsap-timeline, genjutsu, motion-design |
| Animação de interface | genjutsu ou animate | gsap-scrolltrigger, gsap-react, gsap-performance, apple-design |
| Timing, easing e revisão | animate | improve-animations, review-animations, motion-design, choreograph |
| Animar logo PNG/SVG em loop | wiggle | (nenhum) |
| Interativo com estado | rive | genjutsu |
| Motion graphics em vídeo React | remotion-best-practices | claude-motion, review-loop, sound-design |
| Vídeo a partir de HTML/CSS/GSAP | HyperFrames | gsap-core, gsap-timeline |
| Remover fundo de foto/vídeo | CLI `rembg` | (nenhum) |
| Identidade visual do zero | frontend-design ou hallmark | genjutsu, impeccable, prototype |
| Extrair estilo de referência | design-dna | taste |
| Ideia técnica como objeto | anatomy | (nenhum) |
| Efeito de Reel via comando fixo (/vidro, /trava, /particulas, /colagem, /letreiro) | esta skill, seção 5 | HyperFrames + brand-kit |

Grupos que fazem a mesma coisa (use um só): hallmark / frontend-design / genjutsu paint; animate / improve-animations; remotion-best-practices / HyperFrames. Escolha uma e siga.

Não rode demos destrutivas (publicar galeria em massa, gerar dezenas de variantes sem pedido) sem pedido explícito da pessoa.

Ferramentas e skills públicas recomendadas (todas com link no README): HyperFrames, Remotion, ffmpeg, Whisper / faster-whisper, rembg, GSAP skills, Emil Kowalski skills, LottieFiles motion-design, wiggle, rive, design-dna, taste, genjutsu, hallmark, impeccable, stageshow, anatomy, claude-motion.

## 3. Plano combinado

Um plano com: conceito, roteiro por cena ou slide (tempo, texto, imagem/vídeo, câmera, movimento, transição), estilo, ferramentas, e o que reaproveitar. De cada especialista, leia só a seção usada.

## 4. Produção e revisão

- Ordem: texto, imagens/cenas, animação, áudio, render.
- Revise o render (frames ou player) contra o plano e o checklist; corrija só o que falhou, no máximo duas tentativas por etapa.
- Entregue com preview; publique só depois que a pessoa aprovar.

## 5. Receitas por comando (efeitos fixos de Reel)

Comandos curtos e reutilizáveis que produzem um efeito visual específico sobre um vídeo cru. Sempre use o brand kit do projeto como fonte única de cor e fonte (exemplo em `efeitos-por-comando/brand-kit.md`; troque pelos valores da sua marca).

Regras gerais de todas as receitas:

- Entrada padrão: vídeo vertical cru (9:16), 1080x1920, 30fps, 15 a 90 segundos, voz limpa.
- Transcrição sempre com Whisper (timestamps por palavra) antes de legenda ou highlight de termo.
- Render de motion graphics preferencialmente em HyperFrames (Apache 2.0). Remotion é alternativa válida.
- Corte, concatenação e queima de legenda final: ffmpeg.
- Toda animação entra com easing, nunca com "pop" instantâneo (opacidade ou escala indo de 0 para 1 em 1 frame).
- Checklist mínimo antes de entregar: (1) preview de 3 segundos renderizado e revisado, (2) cores e fontes vindas do brand kit, nunca fixas no código, (3) texto sem erro de transcrição, (4) export final 1080x1920 30fps, (5) técnica pública apenas; não copie visual de produtos pagos de terceiros.

### /vidro

- Objetivo: placa de vidro fosco (glassmorphism) sobreposta ao vídeo, geralmente com um gráfico ou número de destaque.
- Entrada: vídeo cru + texto ou número a destacar (ex.: métrica, comparação antes/depois).
- Passos: 1) transcrever; 2) montar a composição no HyperFrames com blur de fundo e painel semi transparente; 3) desenhar o gráfico ou número com as cores do brand kit; 4) renderizar preview de 3s; 5) revisar contraste do texto sobre o vidro; 6) render final e composição com ffmpeg sobre o vídeo base.
- Parâmetros: entrada do painel em 10 a 12 frames, easing tipo spring suave (sem overshoot forte), opacidade do vidro entre 60% e 80%, blur de fundo entre 12px e 20px.
- Exemplo de cores (troque pelas suas): fundo do painel `#123356`, destaque `#2ae19e`, fonte `Raleway Bold`.

### /trava

- Objetivo: efeito de "página travada": o vídeo para e um termo específico ganha destaque (highlight).
- Entrada: vídeo cru + lista de termos a destacar quando ditos.
- Passos: 1) transcrever; 2) localizar timestamps dos termos; 3) no frame correspondente, congelar por alguns frames e aplicar o highlight; 4) preview de 3s; 5) revisar se a trava não cai no meio da frase; 6) render final.
- Parâmetros: congelamento de 6 a 10 frames, highlight entra em 4 a 6 frames, pisca no máximo 1 vez.
- Exemplo: highlight `#2ae19e`, fonte `Raleway`.

### /particulas

- Objetivo: partículas preenchendo uma forma (ex.: contorno de celular) até revelar um texto ou imagem final.
- Entrada: vídeo cru ou tela estática + texto final + forma de referência (mockup, logo, etc).
- Passos: 1) definir a máscara; 2) gerar partículas no HyperFrames (sistema simples, sem física pesada); 3) animar o preenchimento; 4) revelar o texto; 5) preview de 3s; 6) render final.
- Parâmetros: preenchimento de 20 a 30 frames, partículas de 2px a 6px, revelação do texto só depois de 90% da máscara preenchida.
- Exemplo: partículas `#2ae19e`, texto branco em `Raleway Bold`.

### /colagem

- Objetivo: leque de cards mostrando variações de estilo sobre o mesmo vídeo.
- Entrada: um ou mais vídeos crus da própria pessoa + lista de estilos por card.
- Passos: 1) recortar o trecho comum; 2) montar cada card no HyperFrames; 3) animar entrada em leque (rotação leve); 4) legenda com cores do brand kit; 5) preview de 3s; 6) render final.
- Parâmetros: stagger de 3 a 5 frames entre cards, rotação de -8 a 8 graus, assentamento em 15 a 18 frames.
- Exemplo: fundo `#123356` (variação `#7543b4`), legenda `Raleway Medium`.

### /letreiro

- Objetivo: texto em estilo painel de LED sobre o vídeo, para uma frase de efeito.
- Entrada: vídeo cru + frase curta.
- Passos: 1) quebrar a frase em linhas se preciso; 2) montar a grade de LED no HyperFrames; 3) animar letra por letra ou linha por linha; 4) preview de 3s; 5) revisar legibilidade no celular; 6) render final.
- Parâmetros: atraso de 2 a 3 frames entre caracteres, brilho pulsando 5% a 10% de opacidade a cada 20 frames.
- Exemplo: LED `#2ae19e`, fundo `#1d1d1d`, fonte `Raleway` no peso máximo.

Pacote pronto: pasta `efeitos-por-comando/` (brand-kit.md de exemplo e `.claude/skills/` com vidro, trava, particulas, colagem, letreiro). Para usar, copie `brand-kit.md` e `.claude/` para a pasta do projeto do vídeo e troque as cores/fontes pelas da sua marca.

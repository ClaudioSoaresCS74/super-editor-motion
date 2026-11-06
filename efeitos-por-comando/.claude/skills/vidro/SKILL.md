---
name: vidro
description: Cria uma placa de vidro fosco (glassmorphism) sobre o vídeo, com gráfico ou número em destaque, usando as cores do brand kit.
---

# /vidro

Objetivo: sobrepor um painel de vidro fosco ao vídeo recebido, com um gráfico ou número de destaque desenhado por cima.

Entrada esperada: caminho do vídeo cru e o texto, número ou comparação a destacar no painel.

Passos:
1. Leia brand-kit.md na raiz do projeto. Se algum valor estiver como [VOCÊ COMPLETA], pare e peça o valor antes de continuar.
2. Transcreva o áudio com Whisper (ou faster-whisper), com timestamps por palavra.
3. Monte a composição em HyperFrames (preferencial, Apache 2.0) ou Remotion: camada de blur de fundo, painel semi transparente, gráfico ou número com as cores do brand kit.
4. Anime a entrada do painel em 10 a 12 frames com easing suave, sem pop instantâneo.
5. Renderize um preview de 3 segundos do trecho do efeito e mostre antes de seguir.
6. Depois de aprovado, renderize o efeito completo e componha com ffmpeg sobre o vídeo base.
7. Exporte em 1080x1920, 30fps.

Checklist antes de entregar:
- Cores e fonte vieram do brand kit, não foram inventadas.
- Preview de 3 segundos foi revisado antes do render final.
- Contraste do texto sobre o vidro está legível em tela de celular.

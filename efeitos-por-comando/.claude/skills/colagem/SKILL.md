---
name: colagem
description: Monta um leque de cards com variações de estilo sobre o mesmo vídeo (tela dividida, estúdio, palco), usando as cores do brand kit.
---

# /colagem

Objetivo: mostrar o mesmo trecho em vários cards de estilo, entrando em leque.

Entrada esperada: um ou mais vídeos crus da própria pessoa e a lista de estilos de cada card.

Passos:
1. Leia brand-kit.md na raiz do projeto. Se algum valor estiver como [VOCÊ COMPLETA], pare e peça o valor antes de continuar.
2. Transcreva o áudio com Whisper (ou faster-whisper), com timestamps por palavra.
3. Recorte o trecho comum a usar em cada card com ffmpeg.
4. Monte cada card como composição independente em HyperFrames (preferencial, Apache 2.0) ou Remotion, fundo dos cards na cor de painel do brand kit (variação na cor de selo), legenda com a fonte do brand kit.
5. Anime a entrada em leque: stagger de 3 a 5 frames entre cards, rotação de entrada entre -8 e 8 graus, assentamento em 15 a 18 frames.
6. Renderize um preview de 3 segundos e mostre antes de seguir.
7. Depois de aprovado, renderize e componha com ffmpeg.
8. Exporte em 1080x1920, 30fps.

Checklist antes de entregar:
- Cores e fontes vieram do brand kit.
- Só vídeos da própria pessoa foram usados nos cards.
- Preview de 3 segundos foi revisado antes do render final.

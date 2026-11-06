---
name: trava
description: Congela o vídeo por alguns frames e destaca um termo dito (trava de leitura), usando as cores do brand kit.
---

# /trava

Objetivo: congelar o vídeo no momento em que um termo da lista é dito e destacar a palavra com highlight.

Entrada esperada: caminho do vídeo cru e a lista de termos a destacar.

Passos:
1. Leia brand-kit.md na raiz do projeto. Se algum valor estiver como [VOCÊ COMPLETA], pare e peça o valor antes de continuar.
2. Transcreva o áudio com Whisper (ou faster-whisper), com timestamps por palavra.
3. Localize os timestamps exatos dos termos da lista.
4. No frame correspondente, congele o vídeo por 6 a 10 frames e aplique o highlight (cor de destaque do brand kit, fonte do brand kit), entrando em 4 a 6 frames, piscando no máximo 1 vez. Monte em HyperFrames (preferencial, Apache 2.0) ou Remotion.
5. Renderize um preview de 3 segundos do trecho e mostre antes de seguir.
6. Depois de aprovado, renderize e componha com ffmpeg sobre o vídeo base.
7. Exporte em 1080x1920, 30fps.

Checklist antes de entregar:
- Cor do highlight e fonte vieram do brand kit.
- A trava não cai no meio de uma frase.
- Preview de 3 segundos foi revisado antes do render final.

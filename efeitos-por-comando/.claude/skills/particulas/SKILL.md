---
name: particulas
description: Preenche uma forma (mockup de celular, logo, etc) com partículas até revelar um texto ou imagem final, usando as cores do brand kit.
---

# /particulas

Objetivo: animar partículas preenchendo uma forma de referência até revelar um texto ou imagem final por trás.

Entrada esperada: caminho do vídeo ou imagem base, a forma de referência (mockup de celular, logo ou contorno) e o texto ou imagem final a revelar.

Passos:
1. Leia brand-kit.md na raiz do projeto. Se algum valor estiver como [VOCÊ COMPLETA], pare e peça o valor antes de continuar.
2. Defina a máscara da forma de referência.
3. Monte o sistema de partículas em HyperFrames (preferencial, Apache 2.0) ou Remotion, com partículas entre 2px e 6px, cor vinda do brand kit.
4. Anime o preenchimento da máscara em 20 a 30 frames.
5. Revele o texto ou imagem final só depois que a máscara estiver com 90% ou mais de preenchimento.
6. Renderize um preview de 3 segundos e mostre antes de seguir.
7. Depois de aprovado, renderize o efeito completo e componha com ffmpeg sobre o vídeo base.
8. Exporte em 1080x1920, 30fps.

Checklist antes de entregar:
- Cor das partículas e cor/fonte do texto revelado vieram do brand kit.
- A forma de referência é reconhecível antes do preenchimento terminar.
- Preview de 3 segundos foi revisado antes do render final.

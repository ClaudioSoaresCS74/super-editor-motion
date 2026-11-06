---
name: letreiro
description: Cria um texto em estilo painel de LED (letreiro) sobre o vídeo, com entrada letra por letra, usando as cores do brand kit.
---

# /letreiro

Objetivo: exibir uma frase curta em estilo painel de LED sobre o vídeo recebido.

Entrada esperada: caminho do vídeo cru e a frase a exibir no letreiro.

Passos:
1. Leia brand-kit.md na raiz do projeto. Se algum valor estiver como [VOCÊ COMPLETA], pare e peça o valor antes de continuar.
2. Quebre a frase em linhas, se necessário, respeitando a largura do painel.
3. Monte a grade de LED em HyperFrames (preferencial, Apache 2.0) ou Remotion: matriz de pontos ou retângulo com textura de painel, cor de fundo e cor de LED do brand kit.
4. Anime a frase letra por letra, com atraso de 2 a 3 frames entre caracteres, e um brilho pulsando levemente (variação de 5% a 10% de opacidade) a cada 20 frames.
5. Renderize um preview de 3 segundos e mostre antes de seguir.
6. Depois de aprovado, renderize o efeito completo e componha com ffmpeg sobre o vídeo base.
7. Exporte em 1080x1920, 30fps.

Checklist antes de entregar:
- Cor de LED, cor de fundo e fonte vieram do brand kit.
- Frase está legível em tela de celular, sem corte nas bordas.
- Preview de 3 segundos foi revisado antes do render final.

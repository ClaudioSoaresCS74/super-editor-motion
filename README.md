# Super Editor Motion

Skill aberta para agentes de IA (Grok Bot, Claude, Cursor e afins) que orquestra edição de vídeo e motion graphics sem você precisar programar.

Feita por **Cláudio Soares** (@claudiosoares.creator) para a comunidade Be Media Class e quem cria conteúdo com IA.

## O que ela faz

- Escolhe as skills certas para cada trabalho (Reel, carrossel animado, tipografia, Lottie, 3D, etc.), sem sobrepor função.
- Monta um plano único: conceito, cenas, estilo, ferramentas.
- Entrega receitas prontas de efeito de Reel: `/vidro`, `/trava`, `/particulas`, `/colagem`, `/letreiro`.
- Prefere ferramentas públicas e gratuitas ou open source: HyperFrames, ffmpeg, Whisper, GSAP, Remotion (quando a licença permitir).

## O que ela NÃO faz

- Não publica nada sozinha.
- Não inventa cores ou fontes: usa o `brand-kit.md` do seu projeto.
- Não copia visual de produtos pagos de terceiros: só a técnica.

## Como instalar (depois que o repo estiver público)

Peça para o seu agente:

> instala essa skill a partir deste link: https://github.com/ClaudioSoaresCS74/super-editor-motion

Ou, se o seu agente aceita o CLI de skills:

```bash
npx skills add ClaudioSoaresCS74/super-editor-motion
```

Se não quiser terminal: mande o link do GitHub para o agente e diga **"instala essa skill a partir deste link"**.

## Como usar

1. Copie `efeitos-por-comando/brand-kit.md` para a pasta do seu projeto de vídeo.
2. Troque as cores e fontes de exemplo pelas da sua marca.
3. Diga ao agente, por exemplo:
   - "usa a skill super-editor-motion e aplica /vidro neste vídeo destacando o número 87%"
   - "aplica /trava nestes termos: IA, skill, automação"
   - "faz /letreiro com a frase: Sem programar"
4. Peça um preview de 3 segundos antes do render final.

## Estrutura

```
super-editor-motion/
├── SKILL.md
├── README.md
├── LICENSE
└── efeitos-por-comando/
    ├── brand-kit.md
    └── .claude/skills/
        ├── vidro/
        ├── trava/
        ├── particulas/
        ├── colagem/
        └── letreiro/
```

## Ferramentas públicas citadas

- HyperFrames: https://github.com/heygen-com/hyperframes
- Remotion skills: https://github.com/remotion-dev/skills
- GSAP skills: https://github.com/greensock/gsap-skills
- Motion design (LottieFiles): https://github.com/LottieFiles/motion-design-skill
- Wiggle: https://github.com/talknerdytome-labs/wiggle-claude-skill
- Rive: https://github.com/bowtiedswan/rive-skills
- Design DNA: https://github.com/zanwei/design-dna
- ffmpeg, Whisper / faster-whisper, rembg (CLIs abertos)

## Licença

MIT. Veja `LICENSE`.

## Status

Publicado em https://github.com/ClaudioSoaresCS74/super-editor-motion

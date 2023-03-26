![logo do projeto](assets/logo.png){ width="300" .center}
# Notas musicais

Notas musicais é um CLI para ajudar na formação de escalas e acordes.

Temos dois comandos diponíveis: `escala` e `acorde`.

## Como usar?

### Escalas

Você pode chamar as escalas via linha de comando. Por exemplo:

```bash
poetry run notas-musicais escala
```

Retornando os graus e as notas correpondentes a essa escala:

```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ D# │ F  │ G   │ G# │ A# │ C  │ D   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

#### Alteração da tônica da escala

O primeiro parâmetro do CLI é a tônica da escala que deseja exibir. Desta forma, você pode alterar a escala retornada. Por exemplo , a escala de `F#`:
```bash
poetry run notas-musicais escala F#
```

Resultando em:
```
┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ F# │ G# │ A#  │ B  │ C# │ D# │ F   │
└────┴────┴─────┴────┴────┴────┴─────┘
```

#### Alteração na tonilidade da escala

Você pode alterar a tonalidade da escala também! Esse é o segundo parâmetro da linha de comanda. Por exemplo, a escala de `D#` maior:

```bash
poetry run notas-musicais escala D# menor

┏━━━━┳━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ I  ┃ II ┃ III ┃ IV ┃ V  ┃ VI ┃ VII ┃
┡━━━━╇━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ D# │ F  │ F#  │ G# │ A# │ B  │ C#  │
└────┴────┴─────┴────┴────┴────┴─────┘
```

### Acordes

Uso básico

```bash
poetry run notas-musicais acorde
┏━━━┳━━━━━┳━━━┓
┃ I ┃ III ┃ V ┃
┡━━━╇━━━━━╇━━━┩
│ C │ E   │ G │
└───┴─────┴───┘
```

#### Variações na cifra

```bash
poetry run notas-musicais acorde C+
┏━━━┳━━━━━┳━━━━┓
┃ I ┃ III ┃ V+ ┃
┡━━━╇━━━━━╇━━━━┩
│ C │ E   │ G# │
└───┴─────┴────┘
```

Até o momento você pode usar acordes maiores, menores, diminutos e aumentados


## Mais informações sobre o CLI

Para descobrir outras opções, você pode usar a flag `--help`:

```bash
poetry run notas-musicais --help
 Usage: notas-musicais [OPTIONS] COMMAND [ARGS]... 
╭─ Commands ──────────────────────────────────────────────────────────────────╮
│ acorde                                                                      │
│ escala                                                                      │
╰─────────────────────────────────────────────────────────────────────────────╯
```

### Escala
```bash
poetry run notas-musicais escala --help
 Usage: escalas [OPTIONS] [TONICA] [TONALIDADE]
                      
╭─ Arguments──────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica da escala [default: c]               │
│   tonalidade      [TONALIDADE]  Tonalidade da escala [default: maior]       │
╰─────────────────────────────────────────────────────────────────────────────╯
```

### Acorde
```bash
poetry run notas-musicais acorde --help
 Usage: notas-musicais acorde [OPTIONS] [CIFRA]     
╭─ Arguments ─────────────────────────────────────────────────────────────────╮
│   cifra      [CIFRA]  Cifra de um acorde [default: C]                       │
╰─────────────────────────────────────────────────────────────────────────────╯
```
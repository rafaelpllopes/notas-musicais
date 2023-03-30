![logo do projeto](assets/logo.png){ width="300" .center}
# Notas musicais

Notas musicais é um CLI para ajudar na formação de escalas, acordes e campos harmônicos.

Toda a aplicação é baseada em um comando `notas-musicais`. Esse comando tem um subcomando relacionado a cada ação que a aplicação pode realizar. Como `escala`, `acorde` e `campo-harmonico`.

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

### Campo Harmónico

Você pode chamar os campos harmônico via o subcomando `campo-harmonico`. Por exemplo:

```bash
poetry run notas-musicais campo-harmonico
┏━━━┳━━━━┳━━━━━┳━━━━┳━━━┳━━━━┳━━━━━━┓
┃ I ┃ ii ┃ iii ┃ IV ┃ V ┃ vi ┃ vii° ┃
┡━━━╇━━━━╇━━━━━╇━━━━╇━━━╇━━━━╇━━━━━━┩
│ C │ Dm │ Em  │ F  │ G │ Am │ B°   │
└───┴────┴─────┴────┴───┴────┴──────┘
```

Por padrão os parâmetros utilizados são a tônico de `C` e o campo hormônico `maior`.

#### Alterações nos campos harmônicos

Você pode alterar os parâmetros da tônica e da tonalidade

```bash
poetry run notas-musicais campo-harmonico [TONICA] [TONALIDADE]
```

#### Alteração na tônica do campo

Um exemplo com o campo harmônico de `E`:

```bash
poetry run notas-musicais campo-harmonico E
┏━━━┳━━━━━┳━━━━━┳━━━━┳━━━┳━━━━━┳━━━━━━┓
┃ I ┃ ii  ┃ iii ┃ IV ┃ V ┃ vi  ┃ vii° ┃
┡━━━╇━━━━━╇━━━━━╇━━━━╇━━━╇━━━━━╇━━━━━━┩
│ E │ F#m │ G#m │ A  │ B │ C#m │ D#°  │
└───┴─────┴─────┴────┴───┴─────┴──────┘
```

#### Alteração da tonalidade do campo

Um exemplo com o campo harmônico de `E` na tonalidade `menor`:

```bash
poetry run notas-musicais campo-harmonico E menor
┏━━━━┳━━━━━┳━━━━━┳━━━━┳━━━━┳━━━━┳━━━━━┓
┃ i  ┃ ii° ┃ III ┃ iv ┃ v  ┃ VI ┃ VII ┃
┡━━━━╇━━━━━╇━━━━━╇━━━━╇━━━━╇━━━━╇━━━━━┩
│ Em │ F#° │ G   │ Am │ Bm │ C  │ D   │
└────┴─────┴─────┴────┴────┴────┴─────┘
```

## Mais informações sobre o CLI

Para descobrir outras opções, você pode usar a flag `--help`:

```bash
poetry run notas-musicais --help
 Usage: notas-musicais [OPTIONS] COMMAND [ARGS]... 
╭─ Commands ──────────────────────────────────────────────────────────────────╮
│ acorde                                                                      │
│ campo-harmonico                                                             │
│ escala                                                                      │
╰─────────────────────────────────────────────────────────────────────────────╯
```
### Mais informações sobre os subcomandos

As informações sobre os subcomandos podem ser acessadas usando a flag `--help` após o nome do parâmetro. Um exemplo do uso do help.

#### Escala
```bash
poetry run notas-musicais escala --help
 Usage: escalas [OPTIONS] [TONICA] [TONALIDADE]
                      
╭─ Arguments──────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica da escala [default: c]               │
│   tonalidade      [TONALIDADE]  Tonalidade da escala [default: maior]       │
╰─────────────────────────────────────────────────────────────────────────────╯
```

#### Acorde
```bash
poetry run notas-musicais acorde --help
 Usage: notas-musicais acorde [OPTIONS] [CIFRA]     
╭─ Arguments ─────────────────────────────────────────────────────────────────╮
│   cifra      [CIFRA]  Cifra de um acorde [default: C]                       │
╰─────────────────────────────────────────────────────────────────────────────╯
```

#### Campo Harmônico
```bash
poetry run notas-musicais campo-harmonico --help
 Usage: notas-musicais campo-harmonico [OPTIONS] [TONICA] [TONALIDADE]
╭─ Arguments ─────────────────────────────────────────────────────────────────────╮
│   tonica          [TONICA]      Tônica do campo harmônico [default: c]          │
│   tonalidade      [TONALIDADE]  Tonalidade do campo harmônico [default: maior]  │
╰─────────────────────────────────────────────────────────────────────────────────╯
```

# Claudio 🧀

Plugin para o [Claude Code](https://claude.com/claude-code) que faz o Claude se apresentar como **Claudio** e conversar com jeito mineiro: *uai*, *trem*, *sô*, *bão*.

O sotaque fica só na conversa. Código, commits, arquivos e comandos continuam em linguagem normal. Avisos de segurança e ações destrutivas também são ditos de forma séria e direta.

## Instalação

No Claude Code:

```
/plugin marketplace add alanzdr/claudio
/plugin install claudio@claudio
```

Depois, abra uma sessão nova. O Claudio entra automaticamente.

## Desinstalar

```
/plugin uninstall claudio@claudio
```

Para pausar só na sessão atual, peça: "fala normal" ou "desliga o Claudio".

## Como funciona

São dois hooks, sem nenhuma dependência:

| Hook | Arquivo | O que faz |
|---|---|---|
| `SessionStart` | `persona.md` | Carrega a persona completa quando a sessão começa (e de novo após `/compact`). |
| `UserPromptSubmit` | `lembrete.md` | Injeta um lembrete curto a cada mensagem, para o Claudio não sumir em sessões longas. |

Para mudar o jeito do Claudio, edite `persona.md`. Para mudar a força do reforço, edite `lembrete.md`.

## Usar no claude.ai (navegador)

O plugin só funciona no Claude Code. No claude.ai, crie um Projeto e cole o conteúdo de [`persona.md`](persona.md) nas instruções do projeto.

## Testar localmente

Na pasta do repositório, dentro do Claude Code:

```
/plugin marketplace add ./
/plugin install claudio@claudio
```

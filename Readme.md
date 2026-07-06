# Learn Extension v1.0 — Guia de Instalação e Uso

Extensão do VS Code para estudar de forma interativa: você importa um arquivo de lição (`.json`) e a extensão guia você aula por aula, direto no editor.

---

## 1. Instalar a extensão

1. Baixe o arquivo `learn-extension-0.0.1.vsix` (o professor vai te enviar o link).
2. Abra o VS Code.
3. Instale de um dos dois jeitos:

**Instalação: Pela interface:**
- Abra a aba de Extensões (`Ctrl+Shift+X`)
- Clique nos três pontinhos (`...`) no topo do painel
- Escolha **Install from VSIX...**
- Selecione o arquivo `learn-extension-0.0.1.vsix`

**Instalação: Pelo terminal:**
```bash
code --install-extension learn-extension-0.0.1.vsix
```

Depois de instalar, recarregue o VS Code (`Ctrl+Shift+P` → `Developer: Reload Window`) se o ícone da extensão não aparecer de primeira.

Para visualizar a extensão no vscode:
### Ícone na barra lateral
**O ícone da extensão aparecerá na barra lateral esquerda com o nome Learn Extension. Dê um duplo clique nele para fixá-lo na interface do VS Code.**
### Extensão na barra lateral a direita
**A extensão será exibida na barra lateral esquerda. Recomenda-se mantê-la fixada no lado esquerdo do VS Code para facilitar o acesso.**
---

## 2. Baixar as lições

As lições ficam na pasta **[`lições`](#)** do repositório do curso. Essa pasta é atualizada aos poucos — sempre que uma aula nova for lançada, um novo arquivo `.json` aparece lá.

> 💡 Salve os arquivos `.json` que baixar em uma pasta fácil de achar no seu computador (ex: `Downloads` ou uma pasta `lições-baixadas`). Você vai precisar selecionar esse arquivo na hora do upload.

Para saber quando tem lição nova, dê uma olhada de vez em quando na pasta `lições` do repositório.

---

## 3. Importar uma lição na extensão

1. Abra a extensão no VS Code (ícone dela na barra lateral).
2. Vá até a aba **Playground**.
3. Clique em **Upload arquivo**.
4. Selecione o `.json` da lição que você baixou na pasta `lições`.
5. Pronto — a extensão vai te guiar aula por aula, com os botões de navegação (◀ Voltar / Próximo ▶).

---

## 4. Para usuários avançados: criando sua própria lição com IA

Se você quiser estudar um assunto que ainda não tem lição pronta, dá pra gerar a sua própria usando uma IA (ChatGPT, Claude, etc).

1. Vá até a aba **Criar Arquivo**.
2. Clique em **📋 Copiar Prompt**.
3. Cole o prompt em uma IA de sua preferência.
4. Antes de enviar, substitua o campo `[TEMA AQUI]` pelo assunto que você quer aprender (ex: `Manipulação de arrays em JavaScript`).
5. A IA vai devolver um arquivo `.json` pronto, seguindo a estrutura que a extensão espera.
6. Baixe esse `.json`.
7. Volte na aba **Playground**, clique em **Upload arquivo** e selecione o arquivo que a IA gerou.

### Estrutura esperada do arquivo `.json`

```json
{
  "levels": [
    {
      "id": "junior",
      "name": "Júnior",
      "themes": [
        {
          "id": "tema-do-assunto",
          "name": "Nome do Tema",
          "lines": [
            {
              "id": "identificador-unico",
              "question": "Pergunta da aula",
              "comment": "Dica curta",
              "answer": "resposta ou código esperado",
              "workspace": {
                "activeFilePath": "src/arquivo.js",
                "tree": [
                  {
                    "type": "folder",
                    "name": "src",
                    "children": [
                      { "type": "file", "name": "arquivo.js" }
                    ]
                  }
                ]
              }
            }
          ]
        }
      ]
    }
  ]
}
```

O campo `workspace` é opcional — se a IA não gerar ele, a lição funciona normalmente, só sem abrir arquivos automaticamente no editor.

---

## Dúvidas frequentes

**A extensão não aparece na barra lateral depois de instalar.**
Recarregue a janela: `Ctrl+Shift+P` → `Developer: Reload Window`.

**O upload do `.json` deu erro.**
Confira se o arquivo é um `.json` válido (abra num editor de texto e veja se não tem vírgula sobrando ou chave faltando). Se foi gerado por IA, às vezes ela adiciona texto antes/depois do JSON — remova tudo que não for o JSON em si antes de salvar.

**Meu progresso se perde?**
Não — a extensão salva automaticamente em qual aula você parou. Pode fechar o VS Code e continuar de onde parou depois.
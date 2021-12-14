# Manual

[Clique aqui para acessar um material sobre markdown](https://markdown.net.br/sintaxe-basica/)

[Clique aqui para acessar um material sobre yaml](https://markdown.net.br/sintaxe-basica/https://miyake-akio.medium.com/introdu%C3%A7%C3%A3o-b%C3%A1sica-ao-yaml-para-ansiosos-2ac4f91a4443)

## Como criar uma página pessoal

### Passo 1:

Crie um arquivo markdown (".md") na pasta "equipe" neste repositório

### Passo 2:

Insira o frontmatter (cabeçalho) em YAML. Ele deve conter os seguintes dados:

- nome: Seu nome
- links: Links que você quer colocar na página, eles devem ser um lista, cada item com os atributos icone (os icones dão provenientes do [Font Awesome v6](https://fontawesome.com/v6.0/icons?m=free&s=solid%2Cbrands)) e url
- descrição: Uma breve descrição sobre você
- foto: Link para sua foto (a foto pode ser um link para uma imagem ou o caminho para ela caso ela esteja neste repositório)
- cargo: (Aluno, Professor, etc)

O frontmatter deve ser parecer com isso:

```yaml
---
nome: Vitor Daniel
links: 
  - icone: github
    url: https://github.com/vadolasi
descrição: Aluno do IFRN
foto: https://avatars.githubusercontent.com/u/39351572?v=4
cargo: Aluno
---
```

### Passo 3:

Escreva o que você quiser sobre você, em markdown

## Como inserir uma aula

### Passo 1:

Crie um arquivo markdown (".md") na pasta "aulas" neste repositório

### Passo 2:

Insira o frontmatter (cabeçalho) em YAML. Ele deve conter os seguintes dados:

- nome: Nome da aula
- número: Número da aula
- matéria: Matéria (Geografia, Ciências, etc)
- conteúdo_propedêutico: Conteúdo propedêutico
- descrição: Uma breve descrição do conteúdo da aula
- slides: Link para o slides da aula
- tinkercard: Link para o circuito no Tinkercard da aula

O frontmatter deve ser parecer com isso:

```yaml
---
nome: Curso básico de Arduíno
número: 2
matéria: Geografia
conteúdo_propedêutico: Redes de trasporte
descrição: Introdução ao Mundo Maker
slides: https://docs.google.com/presentation/d/1J6umxqqafGLMLCPCdloBklrk7hnCiPPe
tinkercard: https://www.tinkercad.com/things/astJNqeTH3u
---
```

### Passo 3:

Insira o conteúdo do manual da aula, em markdown

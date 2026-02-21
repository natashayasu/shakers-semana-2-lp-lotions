# Desafio Semana 2 — Lotion Landing Page (Shopify + Liquid)

## 📌 Sobre o projeto

Este projeto foi desenvolvido como parte do desafio técnico de Shopify + Liquid, com o objetivo de criar uma Landing Page exclusiva para uma campanha de loções, seguindo boas práticas de:

* Fluxo de desenvolvimento em Shopify (template → section → schema)
* Uso correto dos objetos `page`, `product` e `collection`
* Versionamento com Git (branch, commits e Pull Request)

A landing page permite que o cliente configure o produto principal e a coleção diretamente pelo Editor de Temas, sem necessidade de alterar o código.

---

## 🎯 Objetivo do desafio

Construir uma Landing Page que contenha:

* Título da página (via `page.title`)
* Conteúdo da página (via `page.content`)
* Produto principal em destaque (selecionável pelo Admin)
* Lista de produtos de uma coleção (selecionável pelo Admin)

Tudo de forma dinâmica e configurável pelo painel da Shopify.

---

## 🛠️ O que foi implementado

* Template exclusivo da página: `page.lotion-lp.json`
* Section personalizada da landing page: `lotion-lp.liquid`
* Schema configurável com:

  * Produto principal (type: product)
  * Coleção principal (type: collection)
* Renderização dinâmica usando objetos Liquid:

  * `page`
  * `all_products`
  * `collections`
* Estilização separada em arquivo CSS (`lotion-lp.css`)

---

## 🧩 Estrutura do projeto

```
shakers-semana-2-lp-lotions/
├── assets/
│   └── lotion-lp.css
├── config/
│   ├── settings_data.json
│   └── settings_schema.json
├── layout/
│   └── theme.liquid
├── sections/
│   ├── home.liquid
│   └── lotion-lp.liquid
├── templates/
│   ├── index.json
│   └── page.lotion-lp.json
└── README.md
```

---

## 📄 Template da Landing Page

Arquivo:

```
templates/page.lotion-lp.json
```

Responsável por renderizar a section exclusiva da landing page, conectando corretamente o template à section conforme o fluxo recomendado da Shopify.

---

## 🧱 Section da Landing Page

Arquivo:

```
sections/lotion-lp.liquid
```

Funcionalidades:

* Exibe o título da página (`page.title`)
* Exibe o conteúdo da página (`page.content`)
* Exibe o produto principal configurado no schema:

  * Título
  * Preço com filtro `money`
  * Imagem principal
  * Link para o produto
* Exibe a coleção selecionada:

  * Loop em `collection.products`
  * Título do produto
  * Preço
  * Imagem
  * Link do produto

---

## ⚙️ Configuração no Admin da Shopify

1. Acesse **Online Store > Pages**
2. Crie ou edite uma página
3. No campo de template, selecione:

   ```
   page.lotion-lp
   ```
4. Vá em **Online Store > Customize**
5. Abra a página criada
6. No editor de temas:

   * Selecione o Produto Principal
   * Selecione a Coleção Principal

Assim, o cliente pode alterar os conteúdos sem precisar de um desenvolvedor.

---

## 💻 Como testar localmente (Shopify CLI)

Caso utilize Shopify CLI:

```bash
shopify theme dev
```

Depois, acesse a loja de desenvolvimento e visualize a página utilizando o template `page.lotion-lp`.

---

## 🔀 Fluxo de versionamento (Git)

* Repositório: `shakers-semana-2-lp-lotions`
* Desenvolvimento realizado em branch dedicada:

  ```
  feat/lotion-landing-page
  ```
* Padrão de commits utilizado:

  * feat: create page template for lotion lp
  * feat: add lotion lp section with schema
  * feat: render featured product and collection
  * fix: handle empty product or collection

Pull Request aberto da branch `feat/lotion-landing-page` para `main`.

---

## 🎥 Vídeo de demonstração (obrigatório)

O vídeo apresenta:

* A landing page funcionando no front
* Seleção do produto principal no Editor de Temas
* Seleção da coleção no Editor de Temas
* Explicação do código (template + section + schema)
* Fluxo de Git (branch, commits e PR)

Link do vídeo:
https://drive.google.com/file/d/1iytEnzZco2vG3fWr9VpbwS3YxAFChHvb/view?usp=drive_link

## 📊 Critérios técnicos atendidos

* Uso correto dos objetos `page`, `product` e `collection`
* Section com schema dinâmico (sem hardcode)
* Template exclusivo para landing page
* Organização clara do código
* Estrutura compatível com temas Shopify
* Configuração editável pelo Admin

---

## ✅ Status do projeto

Landing Page funcional, dinâmica e alinhada com os requisitos do desafio técnico, permitindo total configuração pelo Editor de Temas da Shopify sem necessidade de alterações no código.

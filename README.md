# Postman-API-Tests

# 🧪 Projeto de Testes de API - Múltiplas APIs REST
> Projeto de estudos em **Quality Assurance**, utilizando **Postman** para testar APIs públicas e operações CRUD completas.

---

## 🧭 Índice
- [Sobre o Projeto](#-sobre-o-projeto)
- [Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Como Executar os Testes](#-como-executar-os-testes)
- [Cobertura de Testes](#-cobertura-de-testes)
- [Validações Realizadas](#-validações-realizadas)
- [Exemplos de Requisições](#-exemplos-de-requisições)
- [Aprendizados](#-aprendizados)
- [Desafios Enfrentados](#-desafios-enfrentados)
- [Melhorias Futuras](#-melhorias-futuras)
- [APIs Utilizadas](#-apis-utilizadas)
- [Autora](#-autora)
- [Licença](#-licença)

---

## 📋 Sobre o Projeto

Este projeto foi desenvolvido como parte dos meus estudos em **Quality Assurance**, com foco em testes de **API REST**.  
Foram testadas 3 APIs diferentes para demonstrar conhecimento em diversos tipos de requisições, métodos HTTP e validações de resposta.

### 🔹 APIs Testadas:

1. **Last.fm API** — Consultas musicais (artistas, álbuns, faixas)
2. **Open Library API** — Consultas de livros e autores
3. **JSONPlaceholder API** — Operações CRUD completas (Create, Read, Update, Delete)

---

## 🛠️ Tecnologias Utilizadas

- **Postman** → Ferramenta principal para testes de API  
- **Last.fm API** → Dados musicais públicos  
- **Open Library API** → Dados de livros e autores  
- **JSONPlaceholder** → API fake para testes CRUD  
- **JSON** → Formato de dados utilizado nas respostas

---

## 📁 Estrutura do Projeto

```bash
postman-api-tests/
├── collections/
│   ├── lastfm_collection.json           # Testes Last.fm
│   ├── openlibrary_collection.json      # Testes Open Library
│   └── jsonplaceholder_collection.json  # Testes CRUD
├── environments/
│   └── lastfm_environment.json          # API Key Last.fm
├── screenshots/
│   ├── jsonplaceholder/                 # Prints das requisições CRUD
│   ├── lastfm/                          # Prints das consultas musicais
│   └── openlibrary/                     # Prints das consultas de livros
└── README.md                            # Este arquivo
🚀 Como Executar os Testes
📦 Pré-requisitos:

Postman instalado (Download aqui
)

API Key do Last.fm (Criar conta aqui
) — 📎 Requerida apenas para as requisições do Last.fm

▶️ Passo a Passo:

Clone ou baixe este repositório

Importe as Collections no Postman:

Abra o Postman

Clique em Import

Selecione os arquivos da pasta /collections/

Clique em Import

Para Last.fm (📎 Requer API Key):

Importe o environment lastfm_environment.json

Adicione sua chave na variável api_key

Selecione o environment antes de rodar

Execute os testes:

Abra cada requisição e clique em Send

Ou use o Collection Runner para executar todas em sequência
📊 Cobertura de Testes
🎵 Last.fm API (Consultas Musicais)
Endpoint	Método	Descrição	Status Esperado
artist.getinfo	GET	Buscar informações de artista	200 OK
artist.gettopalbums	GET	Top álbuns de um artista	200 OK
album.getinfo	GET	Informações de álbum específico	200 OK
artist.gettoptracks	GET	Top músicas de um artista	200 OK
artist.getsimilar	GET	Artistas similares	200 OK

Total: 5 requisições GET

📚 Open Library API (Consultas de Livros)
Endpoint	Método	Descrição	Status Esperado
/isbn/{isbn}.json	GET	Buscar livro por ISBN	200 OK
/authors/{id}.json	GET	Buscar informações de autor	200 OK
/works/{id}.json	GET	Buscar obra literária	200 OK
/search.json?title={title}	GET	Buscar livros por título	200 OK
/search.json?author={author}	GET	Buscar livros por autor	200 OK

Total: 5 requisições GET

🧩 JSONPlaceholder API (CRUD Completo)
Endpoint	Método	Descrição	Status Esperado
/posts	GET	Listar todos os posts	200 OK
/posts/1	GET	Buscar post específico	200 OK
/posts	POST	Criar novo post	201 Created
/posts/101	GET	Verificar post criado	200 OK
/posts/1	PUT	Atualizar post completo	200 OK
/posts/1	PATCH	Atualizar post parcialmente	200 OK
/posts/1	DELETE	Deletar post	200 OK
/posts?userId=1	GET	Filtrar posts por usuário	200 OK

Total: 8 requisições (GET, POST, PUT, PATCH, DELETE)

TOTAL GERAL: 18 testes cobrindo 3 APIs diferentes.

✅ Validações Realizadas
Todas as APIs

✅ Status codes corretos (200, 201)

✅ Estrutura JSON válida

✅ Dados esperados presentes

✅ Query parameters funcionais

Last.fm

✅ Informações de artistas (nome, bio, ouvintes)

✅ Listagem de álbuns e faixas

✅ Similaridade entre artistas

Open Library

✅ Dados de livros (título, autor, ISBN)

✅ Informações de autores

✅ Busca por diferentes parâmetros

JSONPlaceholder (CRUD)

✅ Criação de recursos (POST → 201)

✅ Leitura (GET → 200)

✅ Atualização completa (PUT)

✅ Atualização parcial (PATCH)

✅ Deleção (DELETE)

✅ Filtros com query parameters

✅ Validação de dados criados

📝 Exemplos de Requisições
Open Library - Buscar Livro por ISBN

Request

GET https://openlibrary.org/isbn/9780140328721.json


Response (200 OK)

{
  "title": "Fantastic Mr Fox",
  "authors": [
    { "key": "/authors/OL34184A" }
  ],
  "publish_date": "1988",
  "isbn_13": ["9780140328721"]
}

JSONPlaceholder - Criar Post

Request

POST https://jsonplaceholder.typicode.com/posts
Content-Type: application/json

{
  "title": "Aprendendo Testes de API",
  "body": "Este é meu primeiro teste POST!",
  "userId": 1
}


Response (201 Created)

{
  "title": "Aprendendo Testes de API",
  "body": "Este é meu primeiro teste POST!",
  "userId": 1,
  "id": 101
}

JSONPlaceholder - Verificar Post Criado

Request

GET https://jsonplaceholder.typicode.com/posts/101


Response (200 OK)

{
  "title": "Aprendendo Testes de API",
  "body": "Este é meu primeiro teste POST!",
  "userId": 1,
  "id": 101
}

🎯 Aprendizados

Durante este projeto, pratiquei e aprendi:

✅ Requisições HTTP (GET, POST, PUT, PATCH, DELETE)

✅ Status codes e significados (200, 201, 404, etc.)

✅ Estrutura de APIs REST

✅ Uso de query parameters e body

✅ Diferença entre PUT (completo) e PATCH (parcial)

✅ Validação de respostas JSON

✅ Uso de environments no Postman

✅ Organização de collections

✅ Testes em múltiplas APIs públicas

✅ Documentação e análise de respostas

✅ Fluxo completo de CRUD

🔍 Desafios Enfrentados
Last.fm — Erro 403
Problema: API retornava 403 Forbidden
Causa: API Key inválida ou limite de requisições
Solução: Geração de nova API Key e uso moderado de requisições

APIs Públicas — Limitações
Aprendizado: APIs de leitura (Last.fm, Open Library) não permitem POST/PUT/DELETE
Solução: Uso do JSONPlaceholder para demonstrar operações completas de CRUD

📚 APIs Utilizadas
[Last.fm API]: (https://www.last.fm/api)
[Open Library API]: (https://openlibrary.org/dev/docs/api)
[JSONPlaceholder]: (https://jsonplaceholder.typecode.com/)

Autora
Nayane Rocha
[GitHub]:(https://github.com/nayanerocha)
[Linkedin]:(https://www.linkedin.com/in/nayanerocha/)

📄 Licença
Este projeto é de código aberto e foi criado para fins educacionais.

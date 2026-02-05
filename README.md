# 🧪 Projeto de Testes de API - Múltiplas APIs REST

Projeto focado em Quality Assurance para validação de APIs REST, utilizando o **Postman** para cobrir consultas complexas e operações completas de CRUD.

## 📊 Plano de Testes e Cobertura

Abaixo estão as APIs testadas e o status das validações:

| API | Tipo de Teste | Status | Cobertura |
|:---|:---|:---:|:---|
| **Last.fm** | Consultas Musicais | ✅ Passou | GET (Informações de Artistas/Álbuns) |
| **Open Library** | Dados Literários | ✅ Passou | GET (Busca por ISBN, Autor e Obra) |
| **JSONPlaceholder** | CRUD Completo | ✅ Passou | GET, POST, PUT, PATCH, DELETE |

---

## 🛠️ Tecnologias Utilizadas

* **Postman**: Ferramenta principal para criação e execução das collections.
* **JSON**: Formato de intercâmbio de dados.
* **Environments**: Gerenciamento de variáveis e chaves de API.

---

## 🚀 Como Executar os Testes

### 1. Pré-requisitos
* Ter o [Postman](https://www.postman.com/downloads/) instalado.
* (Opcional) API Key do [Last.fm](https://www.last.fm/api) para as requisições musicais.

### 2. Importação
1. Clone este repositório.
2. No Postman, clique em **Import**.
3. Selecione os arquivos JSON da pasta `/collections/`.
4. Importe o arquivo da pasta `/environments/` caso vá utilizar a API do Last.fm.

### 3. Execução
* Selecione a Collection desejada no menu lateral.
* Clique em **Send** em cada requisição individualmente.
* Ou utilize o **Collection Runner** do Postman para rodar todas as validações de uma única vez.

---

## ✅ Validações Realizadas (Checklist)

* [x] **Status Codes**: Validação de retornos esperados como 200 OK e 201 Created.
* [x] **Contrato**: Verificação se a estrutura do JSON de resposta está correta.
* [x] **Dados**: Conferência de campos obrigatórios e integridade das informações retornadas.
* [x] **Métodos**: Teste de verbos HTTP distintos (GET, POST, PUT, PATCH, DELETE).

---

## 📝 Detalhes Técnicos

### 🎵 Last.fm (Consultas)
Validação de parâmetros de consulta (Query Parameters) para buscar informações detalhadas de artistas, álbuns e faixas similares.

### 📚 Open Library (Consultas)
Busca de acervo literário com foco em validação de dados de autores e livros via ISBN e títulos.

### 🧩 JSONPlaceholder (CRUD)
Demonstração de persistência de dados simulada, cobrindo criação de recursos, atualização total e parcial, além da exclusão de dados.

---

## 🔍 Desafios e Aprendizados
* **Gestão de Ambientes**: Uso de *environments* para proteger e organizar chaves de API de forma segura.
* **Diferenciação de Verbos**: Prática real da diferença entre `PUT` (substituição total) e `PATCH` (atualização pontual).
* **Tratamento de Erros**: Resolução de erros `403 Forbidden` através da configuração adequada de Headers.

---
**Autora: Nayane Rocha** [GitHub](https://github.com/nayanerocha) | [Linkedin](https://www.linkedin.com/in/nayanerocha/)

---
*Este projeto é de código aberto e foi criado para fins educacionais.*
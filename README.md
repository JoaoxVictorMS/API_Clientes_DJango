<h1 align="center" style="font-weight: bold;">API Clientes Django REST</h1>

<p align="center">
  API RESTful desenvolvida em Django e Django REST Framework para gerenciamento de clientes, com validação de documentos, filtros, ordenação e paginação.
</p>

[JAVASCRIPT__BADGE]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[HTML__BADGE]: https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white
[JQUERY__BADGE]: https://img.shields.io/badge/Django_REST-ff1744?style=for-the-badge&logo=django&logoColor=white

<p align="center">
  • <a href="#technologies">Tecnologias</a> •
  <a href="#started">Iniciando</a> •
  <a href="#routes">API Endpoints</a> •
  <a href="#colab">Colaboradores</a> •
  <a href="#contribute">Contribua</a>
</p>

<h2 id="technologies">💻 Tecnologias</h2>

<div>

![Python][JAVASCRIPT__BADGE]
![Django][HTML__BADGE]
![Django REST Framework][JQUERY__BADGE]

</div>

<h2 id="started">🚀 Iniciando</h2>

Siga as instruções abaixo para rodar o projeto em seu ambiente local.

<h3>Pré-requisitos</h3>

- [Python 3.10+](https://www.python.org/)
- [Git](https://git-scm.com/)

<h3>Clonando</h3>

```bash
git clone url-do-seu-projeto-no-github
cd API_Clientes_DJango
```

<h3>Criando e ativando o ambiente virtual</h3>

```bash
# Criar ambiente virtual
python -m venv .venv

# Ativar no Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

# Ativar no Linux / macOS
source .venv/bin/activate
```

<h3>Instalando dependências</h3>

```bash
pip install -r requirements.txt
```

<h3>Executando as migrações e popular banco de dados</h3>

```bash
python manage.py makemigrations
python manage.py migrate
python populate_script.py
```

<h3>Executando a aplicação</h3>

```bash
python manage.py runserver
```

A API estará disponível no endereço `http://127.0.0.1:8000/`.

<h2 id="routes">📍 API Endpoints</h2>

Aqui estão listadas as principais rotas da API de clientes, incluindo parâmetros de busca, paginação e os corpos de requisição/resposta esperados.

> **Nota de Autenticação:** Esta API utiliza autenticação básica (`BasicAuthentication`). É necessário enviar as credenciais de um usuário válido do sistema nas requisições.

| rota                              | descrição                                                                                    |
| --------------------------------- | -------------------------------------------------------------------------------------------- |
| <kbd>GET /clientes/</kbd>         | Retorna a lista paginada de clientes, veja os [detalhes da resposta](#get-clientes-list)     |
| <kbd>POST /clientes/</kbd>        | Cadastra um novo cliente no sistema, veja os [detalhes da requisição](#post-clientes-detail) |
| <kbd>GET /clientes/{id}/</kbd>    | Retorna os detalhes de um cliente específico pelo ID                                         |
| <kbd>PUT /clientes/{id}/</kbd>    | Atualiza os dados completos de um cliente específico                                         |
| <kbd>DELETE /clientes/{id}/</kbd> | Remove um cliente do sistema                                                                 |

> **Filtros, Busca e Ordenação disponíveis no `GET /clientes/`:**
>
> - **Filtro (`?ativo=`):** Permite filtrar por status (ex: `?ativo=true` ou `?ativo=false`).
> - **Busca (`?search=`):** Realiza busca por nome ou CPF (ex: `?search=João`).
> - **Ordenação (`?ordering=`):** Ordena os registros (ex: `?ordering=nome` ou `?ordering=-nome`).

<h3 id="get-clientes-list">GET /clientes/</h3>

**RESPOSTA (Exemplo paginado)**

```json
{
  "count": 1,
  "next": null,
  "previous": null,
  "results": [
    {
      "id": 1,
      "nome": "João da Silva",
      "cpf": "12345678901",
      "rg": "123456789",
      "celular": "11 91234-1234",
      "ativo": true
    }
  ]
}
```

<h3 id="post-clientes-detail">POST /clientes/</h3>

**REQUISIÇÃO**

```json
{
  "nome": "Maria Souza",
  "cpf": "98765432109",
  "rg": "987654321",
  "celular": "11 98765-4321",
  "ativo": true
}
```

**RESPOSTA (201 Created)**

```json
{
  "id": 2,
  "nome": "Maria Souza",
  "cpf": "98765432109",
  "rg": "987654321",
  "celular": "11 98765-4321",
  "ativo": true
}
```

<h2 id="colab">🤝 Colaboradores</h2>

Um agradecimento especial a todas as pessoas que contribuíram para este projeto.

<table>
  <tr>
    <td align="center">
      <a href="#">
        <img src="https://avatars.githubusercontent.com/u/98715957?v=4" width="100px;" alt="Foto de perfil"/><br>
        <sub>
          <b>Seu Nome</b>
        </sub>
      </a>
    </td>
  </tr>
</table>

<h2 id="contribute">📫 Contribua</h2>

Para contribuir com o projeto:

1. Faça o fork do projeto
2. Crie uma nova branch com a sua funcionalidade (`git checkout -b feature/minha-feature`)
3. Faça commit das suas alterações (`git commit -m 'feat: Adiciona minha funcionalidade'`)
4. Faça o push para a branch (`git push origin feature/minha-feature`)
5. Abra um Pull Request

<h3>Documentações que podem ajudar</h3>

[📝 Como criar um Pull Request](https://www.atlassian.com/br/git/tutorials/making-a-pull-request)

[💾 Padrão de commit](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)

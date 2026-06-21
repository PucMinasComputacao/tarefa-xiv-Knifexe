[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/SpndmZ6Q)

# BMG Transportes — Back end com CRUD no JSON Server

Projeto acadêmico da disciplina de Desenvolvimento Web que evolui o site de destinos turísticos **BMG Transportes**, substituindo os dados estáticos por um back end simulado com **JSON Server**, oferecendo uma API RESTful completa (GET, POST, PUT e DELETE) para a entidade principal do projeto: **Lugares**.

## Informações Gerais

- **Nome:** Gabriel Henrique de Souza Rodrigues
- **Matrícula:** 913558
- **Curso:** Engenharia de Software

## Sobre o Projeto

O site apresenta destinos turísticos internacionais (Paris, Kyoto, Rio de Janeiro, Bali, etc.), cada um com descrição, país, atrações e tags. A aplicação permite:

- **Listar** todos os destinos na página inicial (`index.html`), com carrossel de destaques;
- **Visualizar detalhes** de um destino (`detalhe.html`);
- **Cadastrar** um novo destino (`form.html`);
- **Editar** um destino existente (`form.html?id=...`);
- **Excluir** um destino, com modal de confirmação.

Todas as operações são feitas via **API Fetch**, consumindo o back end fake fornecido pelo **JSON Server**.

## Tecnologias utilizadas

- HTML5, CSS3, Bootstrap 5
- JavaScript (ES6+), API Fetch
- Node.js + JSON Server
- Git/GitHub (commits e tags)

## Estrutura do Projeto

```
├── db/
│   ├── db.json          # Base de dados do JSON Server
│   └── package.json     # Configuração e dependência do json-server
├── public/
│   ├── index.html        # Listagem de destinos (GET) + cards com editar/excluir
│   ├── detalhe.html       # Detalhes de um destino (GET por id)
│   ├── form.html          # Formulário de cadastro/edição (POST/PUT)
│   ├── graficos.html      # Página de visualização de dados (atividade anterior)
│   └── assets/
│       ├── css/styles.css
│       └── js/
│           ├── script.js   # Listagem, detalhe e exclusão (DELETE)
│           └── form.js     # Lógica do formulário (POST/PUT)
└── prints/                 # Capturas de tela da API e do DevTools
```

## Como executar o projeto

### 1. Instalar e iniciar o JSON Server

```bash
cd db
npm install
npm start
```

O servidor ficará disponível em `http://localhost:3000`, expondo os seguintes recursos:

- `http://localhost:3000/lugares`
- `http://localhost:3000/continentes`
- `http://localhost:3000/comentarios`
- `http://localhost:3000/favoritos`

### 2. Abrir o front-end

Com o JSON Server rodando, abra o arquivo `public/index.html` (recomendado usar a extensão **Live Server** do VS Code, para evitar problemas de CORS com `file://`).

## Estrutura de dados (`db.json`)

A entidade principal é **`lugares`**. Cada registro segue o modelo abaixo:

```json
{
  "id": 1,
  "nome": "Paris",
  "descricao": "Capital francesa famosa por arte, gastronomia e arquitetura icônica.",
  "conteudo": "Texto completo exibido na página de detalhes...",
  "pais": "França",
  "continente": "Europa",
  "destaque": true,
  "data": "2026-03-30",
  "imagem_principal": "https://...",
  "atracoes": [
    { "id": 1, "nome": "Torre Eiffel", "descricao": "...", "imagem": "https://..." }
  ],
  "tags": ["arte", "gastronomia", "cultura", "arquitetura"]
}
```

Também existem as entidades auxiliares `continentes`, `comentarios` e `favoritos`, mantidas da modelagem original do projeto.

## Endpoints da API (CRUD)

| Operação | Método | Endpoint               | Descrição                          |
|----------|--------|-------------------------|-------------------------------------|
| Create   | POST   | `/lugares`              | Cria um novo destino                |
| Read     | GET    | `/lugares`              | Lista todos os destinos             |
| Read     | GET    | `/lugares/:id`          | Detalha um destino específico       |
| Update   | PUT    | `/lugares/:id`          | Atualiza um destino existente       |
| Delete   | DELETE | `/lugares/:id`          | Remove um destino                   |

## Prints do Trabalho

> Os prints abaixo demonstram os testes da API e o funcionamento do CRUD via DevTools.

### Tela inicial (listagem de destinos)

`<< INSIRA AQUI o print de prints/home.png >>`

### Tela de detalhes do destino

`<< INSIRA AQUI o print de prints/detalhe.png >>`

### Testes da API (Postman / Insomnia / Thunder Client)

**GET — listar destinos**

`<< INSIRA AQUI o print de prints/api-get.png >>`

**POST — criar destino**

`<< INSIRA AQUI o print de prints/api-post.png >>`

**PUT — atualizar destino**

`<< INSIRA AQUI o print de prints/api-put.png >>`

**DELETE — excluir destino**

`<< INSIRA AQUI o print de prints/api-delete.png >>`

### DevTools — aba Network (Fetch/XHR)

Print mostrando as requisições GET e POST feitas a partir do formulário, com a confirmação da inserção do registro no `db.json`:

`<< INSIRA AQUI o print de prints/network.png >>`

---

## Apresentação dinâmica e avançada de dados (atividade anterior)

A página `graficos.html` apresenta visualizações interativas (gráficos, mapas) a partir dos dados de `lugares`, desenvolvida na etapa anterior do projeto.

`<< Esta seção documenta a entrega da semana 14; mantida para histórico >>`

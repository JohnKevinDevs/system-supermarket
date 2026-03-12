# system-supermarket
# Sistema de Caixa para Supermercado

Sistema de caixa (PDV – Ponto de Venda) desenvolvido para simular o funcionamento de um supermercado.  
O sistema permite registrar produtos através do código de barras, calcular valores da venda, selecionar formas de pagamento e gerar uma nota fiscal simplificada.

O projeto foi desenvolvido com **arquitetura separada em frontend e backend**, seguindo o modelo utilizado em aplicações modernas.

---

# 📸 Demonstração do Sistema

## Interface do Sistema
![Sistema]

## Produtos Utilizados no Sistema
Alguns produtos cadastrados no sistema:

![Arroz]
![Feijão]
![Macarrão]
![Refrigerante]

---

# Tecnologias Utilizadas

## Backend
- Java
- Spring Boot
- Spring Web
- Spring Data JPA
- MySQL
- Maven

## Frontend
- React.js
- JavaScript
- HTML
- CSS
- Axios

## Outros recursos
- API REST
- QR Code para pagamento via Pix
- Áudio de leitura de código de barras
- Imagens de produtos via Flaticon

---

# Arquitetura do Sistema

O projeto segue uma arquitetura **Frontend + Backend + Banco de Dados**.

Frontend (React)
↓
API REST
↓
Backend (Spring Boot)
↓
Banco de Dados MySQL


O frontend realiza requisições HTTP para o backend, que processa os dados e interage com o banco de dados.

---

# Estrutura do Banco de Dados

O sistema utiliza **quatro tabelas principais**.

## Produto
Armazena os produtos cadastrados.

Campos principais:

- id
- nome
- preco
- codigo_barras
- imagem_url
- estoque
- categoria_id

---

## Categoria
Organiza os produtos por tipo.

Exemplo:

| id | nome |
|----|------|
| 1 | Alimentos |
| 2 | Bebidas |

Relacionamento:

1 Categoria → N Produtos


---

## Venda
Representa uma compra realizada no caixa.

Campos:

- id
- data

Relacionamento:

1 Venda → N Itens de venda


---

## Item_Venda
Registra os produtos vendidos em cada venda.

Campos:

- id
- venda_id
- produto_id
- quantidade

Relacionamento:

1 Produto → N Itens de venda


---

# Funcionalidades do Sistema

## Registro de Produtos
- Busca de produtos por código de barras
- Exibição de nome, preço e imagem

## Carrinho de Compra
- Adicionar produtos
- Definir quantidade
- Cancelar último item
- Cálculo automático do total

## Cadastro de Cliente
- Nome
- Contato
- CPF

## Formas de Pagamento

- Dinheiro (com cálculo de troco)
- Pix (QR Code)
- Cartão (crédito ou débito)

## Nota Fiscal

Após finalizar a venda, o sistema gera uma **nota fiscal simplificada**, contendo:

- Produtos comprados
- Quantidade
- Valor unitário
- Valor total

Também é possível **imprimir a nota diretamente pelo navegador**.

---

# Como Executar o Projeto

## Clonar o repositório

```bash
git clone https://github.com/JohnKevinDevs/system-supermarket.git
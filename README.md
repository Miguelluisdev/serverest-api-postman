# **📌 ServeRest API – Testes de API com Postman, CSV e CI/CD (Newman)**

Este repositório contém um projeto completo de **testes de API**, evoluindo desde a execução manual no Postman até a automação via **Newman** e integração com **CI/CD**.

O alvo da API é o serviço público **ServeRest**:
👉 [https://serverest.dev](https://serverest.dev)

---

## **📁 Estrutura do Repositório**

| Arquivo                                | Descrição                                                                                   |
| -------------------------------------- | ------------------------------------------------------------------------------------------- |
| **serverest.postman_collection.json**  | Coleção de testes completa da API (CRUD de usuários, schemas, pré-testes, random user etc.) |
| **ServeRest.postman_environment.json** | Ambiente com variável `baseURL` apontando para o ServeRest                                  |
| **serverest.csv**                      | Massa de dados para criação de usuários usando *Runner* ou Newman                           |
| **README.md**                          | Documentação do projeto                                                                     |

---

## **🚀 Objetivos do Projeto**

✔ Demonstrar testes manuais usando Postman
✔ Evoluir para testes automatizados via Collection Runner
✔ Integrar massa de dados (CSV)
✔ Executar testes em linha de comando com Newman
✔ Preparar pipeline CI/CD para rodar testes automaticamente

---

# **📦 Requisitos & Versões Recomendadas**

Para rodar todo o projeto, as versões abaixo são as mais estáveis e recomendadas:

### **🟦 Node.js**

* **Versão recomendada:** `>= 18.x`
* Verificar sua versão:

  ```sh
  node -v
  ```
* Baixar:
  [https://nodejs.org/en/download](https://nodejs.org/en/download)

---

### **🟧 Postman**

* **Versão recomendada:** `>= 10.x`
* Necessário para testes manuais e exportação/importação da coleção.
* Baixar:
  [https://www.postman.com/downloads/](https://www.postman.com/downloads/)

---

### **🟩 Newman**

* **Versão recomendada:** `>= 6.x`
* Testado e funcionando bem com Node 16, 18 e 20.
* Instalação:

  ```sh
  npm install -g newman
  ```
* Verificar versão:

  ```sh
  newman -v
  ```

---

### **🟥 Newman Reporter – htmlextra**

* **Versão recomendada:** `>= 1.23.x`
* Necessário para gerar relatórios HTML completos.
* Instalação:

  ```sh
  npm install -g newman-reporter-htmlextra
  ```

---

## **🧪 Testes na Coleção**

A coleção inclui cenários reais da API:

### **🔸 Pré-Testes**

* Gerar usuário aleatório com **RandomUser API**
* Salvar valores em variáveis globais (`userName`, `userEmail`, `userPassword`)

### **🔸 CRUD de Usuários**

1. Criar usuário
2. Listar usuários
3. Buscar usuário específico
4. Atualizar usuário
5. Deletar usuário

Todos com:

✔ Validação de **status code**
✔ Validação de mensagens
✔ JSON Schema
✔ Scripts automáticos
✔ Dependência entre requisições

---

## **📄 Execução Manual no Postman**

### **1. Importar coleção**

```
serverest.postman_collection.json
```

### **2. Importar ambiente**

```
ServeRest.postman_environment.json
```

### **3. Rodar sequência sugerida**

1. `pre teste → data new user`
2. `cadastro de usuário → criar novo usuário`
3. Continuação dos testes da suíte

---

## **📊 Execução com Massa CSV (Runner)**

Use o arquivo:

```
serverest.csv
```

Passos:

1. Abrir *Collection Runner*
2. Selecionar a coleção
3. Importar CSV
4. Executar testes em lote

---

## **▶ Executando com Newman (CLI)**

Instalação:

```sh
npm install -g newman
```

Rodar com ambiente:

```sh
newman run serverest.postman_collection.json \
  -e ServeRest.postman_environment.json
```

Rodar com CSV:

```sh
newman run serverest.postman_collection.json \
  -e ServeRest.postman_environment.json \
  --iteration-data serverest.csv
```

---

## **🧾 Gerando Relatório HTML (Newman + htmlextra)**

Instalar o reporter:

```sh
npm install -g newman-reporter-htmlextra
```

Executar:

```sh
newman run serverest.postman_collection.json \
  -e ServeRest.postman_environment.json \
  -r htmlextra \
  --reporter-htmlextra-export report.html
```

---

## **🎯 Habilidades Demonstradas**

✔ Testes manuais de API
✔ Automação via scripts do Postman
✔ JSON Schema Validation
✔ Execução com Newman (CLI)
✔ Testes com massa (CSV)
✔ Relatórios HTML avançados
✔ CI/CD com execução a cada push

---

## **📬 Autor**

**Miguel Luis – QA / Testes de API / Automação**

# Desafio Técnico – Plataforma Jurídica (WordPress + WooCommerce)

Este repositório contém a prova de conceito funcional do desafio técnico, implementando:
- *Tema filho Storefront-child* com campos personalizados usando Carbon Fields.
- *Plugin aasp-custom-products* para relatório administrativo com paginação.
- Integração mock com API externa para validação de conteúdo.
- Ambiente de desenvolvimento com *Docker* (WordPress + MariaDB + phpMyAdmin).

---

## 1. Pré-requisitos

- Docker e Docker Compose instalados na máquina.
- Porta 8080 (WordPress) e 8081 (phpMyAdmin) disponíveis.

---

## 2. Clonar o repositório

bash
git clone git@github.com:daqniwloe/testewpmerge.git
cd desafio-juridico


## 3. Subir o ambiente Docker
bash
docker-compose up -d


## 4. Instalar dependências via Composer

- Entre no container do WordPress e rode os comandos para instalar as dependências:

bash
docker exec -it reviiv-wordpress bash
cd wp-content
composer require htmlburger/wpemerge
composer require htmlburger/carbon-fields

5. Instalar e ativar plugins e temas necessários

    WooCommerce:

        - Acesse o painel WordPress: http://localhost:8080/wp-admin.

        - Vá em Plugins > Adicionar novo, busque WooCommerce e instale.

        - Ative o WooCommerce e finalize a configuração inicial.

    Tema filho Storefront Child (ZIP incluso no repositório):

        - Vá em Aparência > Temas > Adicionar novo > Enviar tema.

        - Envie o arquivo storefront-child.zip disponível na pasta zip/ deste repositório.

        - Ative o Storefront Child.

    Plugin AASP Custom Products (ZIP incluso no repositório):

        - Vá em Plugins > Adicionar novo > Enviar plugin.

        - Envie o arquivo aasp-custom-products.zip disponível na pasta zip/ deste repositório.

        - Ative o plugin.

## 6. Criar um produto para testes

    - Vá em Produtos > Adicionar novo.

    - Nome: Curso Jurídico Avançado.

    - Preencha os campos personalizados em Informações Jurídicas:

        - Descrição Técnica: Conteúdo avançado incluindo análise de jurisprudência, estudos de caso e simulados.

        - Nível de Complexidade: Média

        - Horas Estimadas: 40

    - Publique o produto.

## 7. Testar funcionalidades

    - Frontend:

        - Acesse a página do produto e verifique a aba Informações Jurídicas.

        - Clique em Validar conteúdo jurídico com sistema externo para testar a integração mock.

    - Administração:

        - No menu do WordPress, vá em Produtos Jurídicos.

        - Confira o Relatório de Produtos Jurídicos com descrição, nível, horas e número de pedidos.

        - Use a paginação para navegar entre os resultados.

 ## 8. Encerrar ambiente Docker

bash
docker-compose down

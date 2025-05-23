# Extração de Dados dos Produtos Mais Vendidos do Mercado Livre

Este projeto tem como objetivo a extração de dados dos produtos mais vendidos do Mercado Livre, organizados por categoria. Utilizando a biblioteca Scrapy, o projeto realiza webscraping das páginas do site para coletar informações relevantes sobre os produtos, como produto/título, preço, categoria, ranking de vendas (dentro da categoria), link do produto e link da imagem do produto.

Os dados extraídos são armazenados em arquivos CSV (ou JSON), facilitando seu uso posterior para análises, relatórios, dashboards ou outras aplicações que necessitem dessas informações estruturadas.

## Descrição do Projeto

O código realiza as seguintes etapas:

- Navega pelas categorias mais vendidas do Mercado Livre.
- Coleta dados dos produtos em cada categoria, incluindo nome, preço e outros atributos relevantes.
- Salva os dados extraídos no formato desejado

## Para usar o projeto, siga os passos abaixo:

**1. Crie e ative o ambiente virtual:**
   python -m venv venv_webscrapping
   .\venv_webscrapping\Scripts\activate

**2. Instalação do Scrapy e dependências:**
   pip install scrapy
   pip freeze > requirements.txt

**3. Inicialização do Spider e extração dos dados:**
  - **Iniciar o spider:** scrapy crawl extracao_mercadolivre
  - **Baixar o html da página para testar o scrapy (OPCIONAL):**  scrapy fetch('https://www.mercadolivre.com.br/mais-vendidos')
    - *EXEMPLOS:*
      - Titulo: response.css('h3.dynamic-carousel__title::text').get()
      - Link da imagem do produto: response.css('img.dynamic-carousel__img::attr(data-src)').get()
  - **Extração dos dados em CSV:** scrapy crawl extracao_mercadolivre -o dados_mercadolivre_23_05_2025.csv
  - **Extração dos dados em JSON:** scrapy crawl extracao_mercadolivre -o dados_mercadolivre_23_05_2025.json

**4. Documentação da biblioteca scrapy:**  
  https://docs.scrapy.org/en/latest/intro/tutorial.html

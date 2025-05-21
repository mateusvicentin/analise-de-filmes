<h1 align="center" style="font-size:2.2rem; color:#4B8BBE;">
  🎬 Análise Exploratória de Filmes com Dashboard<br>usando Python, Pandas e Streamlit
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/python-3.11-blue?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" />
</p>

<hr style="border:1px solid #ececec; margin: 24px 0;">

<h2 style="color:#4B8BBE;">📂 Estrutura do Projeto</h2>

<pre><code style="font-size:1rem;">
.
├── dashboards/
│   └── app.py                       # Dashboard principal com Streamlit
├── data/
│   ├── processed/
│   │   ├── dados_tratados.csv           # Base tratada e pronta para análise
│   │   ├── filmes_media_9.csv           # Filmes com média ≥ 9
│   │   ├── maior_bilheteria.csv         # Filmes com maior bilheteria
│   │   ├── mais_avaliados.csv           # Filmes mais avaliados
│   │   ├── mais_caros.csv               # Filmes mais caros
│   │   ├── mais_populares.csv           # Filmes mais populares
│   │   ├── mais_votados_ano.csv         # Filmes mais votados por ano
│   │   ├── mais_votados_genero.csv      # Filmes mais votados por gênero
│   │   └── mais_votados.csv             # Top filmes mais votados
│   └── raw/
│       └── TMDB_all_movies.csv          # Base original bruta extraída da fonte
├── notebooks/
│   └── verificacao.ipynb                # Notebook de exploração e checagens
├── src/
│   ├── ingest/
│   │   └── load_csv.py                  # Script de ingestão e leitura dos CSVs
│   └── transform/
│       └── clean_data.py                # Rotinas de tratamento e limpeza dos dados
</code></pre>

<hr style="border:1px solid #ececec; margin: 24px 0;">

<h2 style="color:#4B8BBE;">🧩 Scripts principais</h2>

<h3 style="margin-top: 2em; color: #2ecc71;">🔹 <code>load_csv.py</code></h3>
<ul>
  <li><b>Resumo do arquivo:</b> exibe primeiras linhas e tipos de cada coluna.</li>
  <li><b>Pula linhas com problemas:</b> ignora linhas com erro automaticamente.</li>
  <li><b>Mostra total de linhas:</b> informa quantas linhas foram carregadas.</li>
</ul>
<p>
  <b>Como usar:</b>  
  <pre><code>python src/ingest/load_csv.py caminho/do/arquivo.csv</code></pre>
</p>

<h3 style="margin-top: 2em; color: #2ecc71;">🔹 <code>clean_data.py</code></h3>
<ul>
  <li>Remove linhas com valores nulos nas colunas essenciais (<code>id</code>, <code>title</code>, <code>release_date</code>, <code>vote_count</code>, <code>vote_average</code>, <code>imdb_rating</code>, <code>imdb_votes</code>).</li>
  <li>Remove linhas duplicadas.</li>
  <li>Separa <b>release_date</b> em <code>year</code>, <code>month</code> e <code>day</code>.</li>
  <li>Salva o DataFrame tratado em <code>data/processed/dados_tratados.csv</code>.</li>
</ul>
<p>
  <b>Como usar:</b> Basta rodar o script. Ele lê <code>data/raw/TMDB_all_movies.csv</code> e gera o arquivo tratado.
</p>

<hr style="border:1px solid #ececec; margin: 24px 0;">

<h2 style="color:#4B8BBE;">📊 Funcionalidades do Projeto</h2>

<ol>
  <li><b>Leitura dos Dados Tratados:</b> Carrega o <code>dados_tratados.csv</code>, exibe as primeiras linhas para mostrar a estrutura das colunas.</li>
  <li><b>Top 10 Filmes Mais Populares:</b> Ordena por <code>popularity</code> e salva os 10 primeiros em <code>mais_populares.csv</code>.</li>
  <li><b>Filmes com Nota Média 9:</b> Seleciona filmes com <code>imdb_rating</code> ≥ 9, populares e com muitos votos; salva em <code>filmes_media_9.csv</code>.</li>
  <li><b>Top 10 Filmes Mais Bem Avaliados:</b> Entre os 10 com mais votos, seleciona os melhores em <code>mais_avaliados.csv</code>.</li>
  <li><b>Top 10 Filmes Mais Votados:</b> Ordena por <code>imdb_votes</code> e salva top 10 em <code>mais_votados.csv</code>.</li>
  <li><b>Filmes Mais Caros da História:</b> Seleciona os 20 com maior <code>budget</code>, exporta para <code>mais_caros.csv</code>.</li>
  <li><b>Filmes com Maiores Faturamentos:</b> Top 20 em <code>revenue</code>, exporta para <code>maior_bilheteria.csv</code>.</li>
  <li><b>Filmes Mais Votados por Ano:</b> Para cada ano, salva o mais votado em <code>mais_votados_ano.csv</code>.</li>
  <li><b>Gêneros Mais Bem Avaliados:</b> Para cada gênero, salva o filme mais votado em <code>mais_votados_genero.csv</code>.</li>
</ol>

<hr style="border:1px solid #ececec; margin: 24px 0;">

<h2 style="color:#4B8BBE;">📈 Exemplos do Dashboard</h2>

<div align="center" style="margin:2em 0;">
  <h3>Top 10 Filmes Mais Populares</h3>
  <img src="https://github.com/user-attachments/assets/e58018ca-558e-475b-9696-0519221ef929" alt="mais_populares" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Filmes com Nota Média 9</h3>
  <img src="https://github.com/user-attachments/assets/5c24045f-3670-4c17-9372-1a84372a649a" alt="filmes_media_9" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Top 10 Filmes Mais Bem Avaliados de Todos os Tempos</h3>
  <img src="https://github.com/user-attachments/assets/8cc78edd-892d-4f1d-a4b1-0b0f96e814d7" alt="mais_avaliados" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Top 10 Filmes Mais Votados de Todos os Tempos</h3>
  <img src="https://github.com/user-attachments/assets/fe0501f5-69a7-45d4-83e0-1bea7f50df5d" alt="mais_votados" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Filmes Mais Caros da História</h3>
  <img src="https://github.com/user-attachments/assets/b5166dfb-7ee4-41c1-a0a3-aac59d7845e8" alt="mais_caros" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Filmes com Maiores Faturamentos</h3>
  <img src="https://github.com/user-attachments/assets/e6c7e2e5-bf88-4c24-8d17-5b0ec523211f" alt="maior_faturamento" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Filmes Mais Votados por Ano</h3>
  <img src="https://github.com/user-attachments/assets/362c0230-5b01-4cf7-b987-fd1cb15a8ca4" alt="mais_votados_ano" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Gêneros Mais Bem Avaliados</h3>
  <img src="https://github.com/user-attachments/assets/843bba97-7a54-4775-8093-abab91dd630a" alt="mais_votados_generos" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>

  <h3>Dashboard em Geral</h3>
  <img src="https://github.com/user-attachments/assets/bd49347c-4aeb-472e-b750-392a46daa0ed" alt="dashboard1" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>
  <img src="https://github.com/user-attachments/assets/d856ad13-0f98-4cd8-b662-204ab4fc5642" alt="dashboard1" style="max-width:400px; border-radius:12px; box-shadow:0 2px 12px #0001;"/>
</div>

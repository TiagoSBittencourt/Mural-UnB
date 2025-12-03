
# Mural UnB


## Sobre 

O [Mural UnB](https://github.com/unb-mds/2025-2-Mural-UnB) é uma plataforma digital projetada para centralizar e recomendar oportunidades acadêmicas e profissionais dentro da Universidade de Brasília (UnB).

O objetivo é criar uma experiência personalizada, onde os estudantes possam facilmente descobrir oportunidades alinhadas aos seus interesses e histórico acadêmico.
Ao analisar o perfil do usuário, a plataforma recomenda as opções mais relevantes e envia notificações sobre novas vagas.

Inclui oportunidades como:

    Empresas juniores
    Laboratórios de pesquisa
    Equipes de Competição

Em resumo, o Mural UnB funciona como um mural virtual, que vai além de apenas listar oportunidades — ele ajuda os estudantes a se conectarem com as oportunidades certas, no momento certo.

## Equipe



<table>
  <tr>
    <td align="center">
      <a href="https://github.com/TiagoSBittencourt">
        <img src="https://github.com/TiagoSBittencourt.png" width="100px;" alt="Tiago Bittencourt"/>
        <br /><sub><b>Tiago Bittencourt</b></sub>
      </a>
      <br /><span>SM • ML & Agent Developer</span>
    </td>
    <td align="center">
      <a href="https://github.com/Karmantinedev">
        <img src="https://github.com/Karmantinedev.png" width="100px;" alt="João Gonzaga"/>
        <br /><sub><b>João Gonzaga</b></sub>
      </a>
      <br /><span>PO • Backend Developer</span>
    </td>
    <td align="center">
      <a href="https://github.com/luanludry">
        <img src="https://github.com/luanludry.png" width="100px;" alt="Luan Ludry"/>
        <br /><sub><b>Luan Ludry</b></sub>
      </a>
      <br /><span>Frontend Developer</span>
    </td>
    <td align="center">
      <a href="https://github.com/Lucasft16">
        <img src="https://github.com/Lucasft16.png" width="100px;" alt="Lucas Fujimoto"/>
        <br /><sub><b>Lucas Fujimoto</b></sub>
      </a>
      <br /><span>Backend Developer</span>
    </td>
    <td align="center">
      <a href="https://github.com/MariaClara-Canuto">
        <img src="https://github.com/MariaClara-Canuto.png" width="100px;" alt="Maria Canuto"/>
        <br /><sub><b>Maria Canuto</b></sub>
      </a>
      <br /><span>Frontend Developer</span>
    </td>
    <td align="center">
      <a href="https://github.com/apptrx">
        <img src="https://github.com/apptrx.png" width="100px;" alt="Matheus Saraiva"/>
        <br /><sub><b>Matheus Saraiva</b></sub>
      </a>
      <br /><span>Backend Developer</span>
    </td>
  </tr>
</table>


## Como Funciona

1. **Listagem de Oportunidades (Feed)** → O usuário tem acesso a uma página com grande parte das oportunidades na UnB.  
2. **Análise de perfil** → O sistema identifica interesses e habilidades que o usuário quer ser recomendado por meio de Tags.  
3. **Recomendações personalizadas** → O estudante recebe oportunidades alinhadas ao seu perfil (tags).

---

# Motivação

A falta de um canal centralizado dificulta o acesso dos estudantes às oportunidades dentro da UnB.  
Atualmente, informações estão dispersas em murais físicos, e-mails institucionais e redes sociais, o que leva muitos alunos a **perderem prazos importantes**.  

O **Mural UnB** surge como resposta a esse problema, oferecendo **eficiência, transparência**.

---

## Tecnologias Utilizadas

### Frontend
- **React** – [https://reactjs.org/](https://reactjs.org/)  
- **TypeScript** – [https://www.typescriptlang.org/](https://www.typescriptlang.org/)  
- **Tailwind CSS** – [https://tailwindcss.com/](https://tailwindcss.com/)  

### Dados
- **Python** – [https://www.python.org/](https://www.python.org/)  
- **API - Gemini** – [https://docs.gemini.com/rest-api/](https://docs.gemini.com/rest-api/)  
- **JSON** – [https://www.json.org/json-en.html](https://www.json.org/json-en.html)  
- **Pandas** – [https://pandas.pydata.org/](https://pandas.pydata.org/)  
- **GitHub Actions** – [https://docs.github.com/en/actions](https://docs.github.com/en/actions)  

### Outros
- **Git** – [https://git-scm.com/](https://git-scm.com/)  
- **GitHub** – [https://github.com/](https://github.com/)  
- **GitHub Pages** – [https://pages.github.com/](https://pages.github.com/)  
- **MkDocs** – [https://www.mkdocs.org/](https://www.mkdocs.org/)

---

## Manual de instalção

### Scripts de Backend e ETL

Esta pasta contém os scripts Python responsáveis pela extração, transformação e carregamento (ETL) dos dados, além das integrações com IA (Google Gemini).

### Configuração Inicial

Antes de executar qualquer script, certifique-se de estar na **raiz do projeto**:

1.  **Ative o ambiente virtual:**
    ```bash
    source venv/bin/activate
    # Windows: venv\Scripts\activate
    ```

2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    pip install -r requirements-EJ.txt
    ```

3.  **Configuração de API (Gemini):**
    Para os scripts de IA funcionarem, crie um arquivo `.env` na raiz do projeto contendo sua chave:
    ```env
    GOOGLE_API_KEY="sua_chave_aqui"
    ```

---

### Pipelines de Execução

Os comandos abaixo devem ser executados a partir da raiz do projeto.

1. Pipeline de Laboratórios (FGA)
Responsável por baixar o portfólio, extrair textos e buscar imagens na web.

```bash
# 1. Baixar o PDF oficial da UnB
python scripts/labs_pdf.py

# 2. Extrair dados, buscar imagens na web e gerar CSV
python scripts/extrair_labs_fga.py
```

Saída: data/Labs/labs_fga.csv e imagens em data/images/labs/.

2. Pipeline de Empresas Juniores (EJs)
Extrai dados dos editais e portfólios das EJs.

```bash
python scripts/extrair_empresas_juniores.py
```

### 3. Pipeline de Inteligência Artificial (Embeddings)
Gera vetores semânticos para permitir a busca inteligente e categorização.

```bash

# 1. Gerar embeddings para as tags base
python scripts/generate_embeddings_gemini.py

# 2. Alocar tags aos laboratórios baseado em similaridade semântica
python scripts/alocar_tags_embeddings.py
```
## Testes e Qualidade
O projeto utiliza pytest para testes unitários (com mocks de rede/arquivos) e pylint para análise estática.

```bash
# Rodar todos os testes unitários
```bash
# 1. Clone o repositório
git clone https://github.com/unb-mds/2025-2-Mural-UnB.git

# 2. Configuração do Backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 3. Configuração do Frontend
cd site
npm install
npm run dev
```




 

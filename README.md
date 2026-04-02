# 🌍 Análise Racial Pro - Projeto Negram

A plataforma **Análise Racial Pro** é um Sistema de Informação Geográfica na Web (WebGIS) interativo desenvolvido para a visualização, processamento e análise de dados sociodemográficos e raciais. 

Projetada com arquitetura *Client-Side Rendering*, a aplicação processa matrizes de dados complexas diretamente no navegador do usuário, garantindo alta performance, privacidade no manuseio das informações e total independência de servidores backend de processamento.

---

## ✨ Funcionalidades

* **🔐 Autenticação e Controle de Acesso:** Sistema de login integrado para restringir o acesso ao painel analítico apenas a pesquisadores e membros autorizados.
* **📁 Ingestão Dinâmica de Dados:** Suporte a upload local de arquivos `.geojson`, permitindo a atualização instantânea do banco de dados geográfico na tela sem necessidade de novo *deploy*.
* **🗺️ Mapas Coropléticos Interativos:** Renderização geoespacial com classificação multicritério de variáveis (ex: População Branca vs. População Negra em quintis ou limiares de maioria).
* **🔍 Filtro Espacial Avançado:** Ferramenta de seleção múltipla de localidades (estilo *chips/tags*) com barra de busca em tempo real para isolar a análise em municípios específicos.
* **📊 Métricas e Rankings em Tempo Real:** Cálculo automático de médias demográficas e geração de um ranking ("Top 5 Concentrações") responsivo ao recorte espacial visualizado.
* **🛡️ Proteção Visual de Dados:** Camada de marca d'água invisível aos cliques do mouse para inibição de capturas de tela e gravação não autorizadas de relatórios internos.

---

## 🛠️ Tecnologias Utilizadas

O projeto foi construído utilizando tecnologias web nativas e bibliotecas de código aberto, otimizadas para leveza e execução rápida:

* **HTML5 / CSS3:** Estruturação semântica e estilização de interface (UI) inspirada em painéis analíticos modernos de Data Science.
* **JavaScript (Vanilla):** Lógica de aplicação, cálculos estatísticos e manipulação do DOM, dispensando frameworks pesados.
* **[Leaflet.js](https://leafletjs.com/):** Motor principal de renderização cartográfica e interação com os polígonos e limites geográficos.

---

## 🚀 Como Executar o Projeto

Como a aplicação não depende de um backend ou banco de dados em nuvem, a execução e os testes locais são extremamente simples.

### Pré-requisitos
* Um navegador web moderno (Google Chrome, Firefox, Edge, Safari).
* Um banco de dados estruturado e convertido para o formato `.geojson` contendo as feições espaciais e propriedades estatísticas.

### Passos para Execução

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/sua-organizacao/negram-analise-racial.git](https://github.com/sua-organizacao/negram-analise-racial.git)
    ```
2.  **Navegue até o diretório do projeto:**
    ```bash
    cd negram-analise-racial
    ```
3.  **Inicie a aplicação:**
    Basta abrir o arquivo `index.html` em seu navegador padrão duplo clique.
    *(Para fins de desenvolvimento contínuo, recomenda-se o uso de extensões como o Live Server no VS Code).*

---

## 📖 Estrutura de Dados (GeoJSON)

Para que a aplicação renderize corretamente as cores, legendas e as métricas nos painéis, o arquivo `.geojson` submetido no painel de upload deve conter as seguintes chaves no objeto `properties` de cada polígono:

| Propriedade | Tipo | Descrição |
| :--- | :--- | :--- |
| `NM_MUNICIP` | `String` | Nome do município (utilizado para popular dinamicamente os filtros espaciais). |
| `NM_BAIRRO` | `String` | Nome do bairro, comunidade ou setor censitário. |
| `BRANCOS%` | `Float/Int` | Porcentagem da população autodeclarada branca no recorte. |
| `NEGROS%` | `Float/Int` | Porcentagem da população autodeclarada negra/parda no recorte. |

---

## 🔒 Privacidade e Segurança de Dados

Todos os dados inseridos na plataforma via upload local são lidos utilizando a API nativa do navegador (`FileReader`) e processados **exclusivamente na memória temporária do cliente (Client-Side)**. 

Nenhum arquivo geográfico ou tabela sociodemográfica é enviado para a internet, interceptado por APIs de terceiros ou armazenado em servidores externos, garantindo total conformidade com a privacidade da pesquisa e os limites do acesso autorizado.

---

## ✉️ Contato e Equipe

* **Desenvolvedor:** Emerson de Oliveira
* **Instituição:** Projeto Negram - Instituto de Pesquisa e Planejamento Urbano e Regional (IPPUR / UFRJ)
* **Email Institucional:** negram.ippur.ufrj@gmail.com
* **Localização:** Rio de Janeiro, RJ - Brasil

---
*Documentação de Software gerada em Abril de 2026.*

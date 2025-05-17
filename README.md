# 🤖 Agente de IA (MVP) para Busca de Estágios em Programação

Um Agente de Inteligência Artificial Básico (MVP - Minimum Viable Product) desenvolvido em Python para auxiliar estudantes de programação a encontrar vagas de estágio. Este projeto inicial foca na coleta de vagas de uma fonte específica e na filtragem baseada em palavras-chave fornecidas pelo usuário.

**Criado como um projeto de aprendizado inicial em programação e conceitos básicos de web scraping e interação.**

## ✨ Funcionalidades (MVP)

*   **Coleta de Vagas:** Realiza a extração de informações de vagas de estágio de uma **única fonte web simples** (requer adaptação do código para o site alvo).
*   **Filtro Interativo:** Permite que o usuário insira palavras-chave (ex: "Python", "Remoto", "São Paulo") para filtrar as vagas encontradas.
*   **Exibição de Resultados:** Mostra as vagas que correspondem aos critérios de filtro diretamente no console (saída do notebook Colab).

## ⚠️ Considerações Éticas e Legais sobre Web Scraping

É **fundamental** estar ciente das implicações éticas e legais ao coletar dados da web.

*   **Termos de Serviço (ToS):** Sempre verifique os Termos de Serviço do site que você pretende scrapar. Muitos sites proíbem ou restringem scraping automatizado.
*   **Arquivo `robots.txt`:** Consulte o arquivo `robots.txt` do site (ex: `https://www.exemplo.com/robots.txt`) para entender quais partes do site os proprietários pedem para não serem acessadas por robôs.
*   **Não sobrecarregue:** Faça requisições de forma lenta e controlada (`time.sleep()`) para não prejudicar o desempenho do site alvo.
*   **Propósito:** Este código é fornecido **apenas para fins educacionais e de aprendizado**. Ao aplicá-lo, escolha fontes de dados simples, com permissão implícita ou explícita, e sempre respeite as regras. **Evite sites grandes e protegidos.**

## 🚀 Como Executar no Google Colab

Este projeto foi desenvolvido para rodar diretamente no ambiente do Google Colab.

1.  **Abra o Notebook:** Faça upload ou abra o arquivo `.ipynb` deste projeto no Google Colab.
2.  **Execute as Células Sequencialmente:** Siga a ordem das células no notebook.
    *   Execute a célula que **instala as bibliotecas** (`!pip install ...`) e importa os módulos.
    *   Execute a célula que **define a URL** e faz a requisição HTTP. **Importante:** Você precisará **editar esta célula** para apontar para a URL do site de vagas que você escolheu para scrapar.
    *   Execute a célula que **analisa o HTML** com BeautifulSoup.
    *   Execute a célula que **extrai os dados** das vagas. **Crucial:** Você precisará **inspecionar o HTML do site alvo** e **adaptar os seletores CSS/HTML** (`find`, `find_all`) nesta célula para que ela consiga encontrar corretamente o título, link, descrição, etc., das vagas no site escolhido.
    *   Execute a célula que contém o `input()`. O Colab irá pausar e exibir um campo de texto na área de saída da célula. **Digite as palavras-chave** que você deseja usar para filtrar as vagas (separadas por espaço) e pressione `Enter`.
    *   Execute a última célula para **exibir as vagas filtradas** com base nas palavras-chave que você digitou.

## ⚙️ Tecnologias Utilizadas

*   **Python:** Linguagem de programação principal.
*   **Google Colab:** Ambiente de desenvolvimento e execução.
*   `requests`: Para fazer requisições HTTP e obter o conteúdo das páginas web.
*   `beautifulsoup4`: Para analisar o código HTML e extrair informações estruturadas.
*   `lxml`: Parser rápido para BeautifulSoup.
*   `re`: Módulo de expressões regulares (útil para limpeza/busca de texto).
*   `time`: Para adicionar pausas e evitar sobrecarregar servidores.

## 💡 Próximos Passos e Possíveis Melhorias

Este MVP é apenas o começo! Muitas melhorias podem ser implementadas:

*   **Múltiplas Fontes:** Coletar vagas de vários sites e portais.
*   **Persistência de Dados:** Salvar as vagas encontradas em um banco de dados (como SQLite) para não precisar scrapar o site toda vez e para permitir buscas mais rápidas.
*   **Interface Melhor:** Criar uma interface de usuário mais amigável (ex: uma aplicação web simples usando Flask ou Streamlit, ou até mesmo um bot para Telegram/Discord).
*   **Filtros Avançados:** Implementar filtros mais sofisticados (ex: buscar por "Backend OU Frontend", excluir vagas com "experiência de 5 anos", filtrar por salário/modalidade).
*   **Processamento de Linguagem Natural (NLP):** Usar bibliotecas como NLTK ou spaCy para entender melhor as descrições das vagas e as consultas dos usuários (sinônimos, reconhecimento de entidades como linguagens, frameworks, localizações).
*   **Sistema de Recomendação:** Desenvolver um algoritmo para recomendar vagas com base no perfil do estudante ou no histórico de vagas que ele visualizou/filtrou.
*   **Acompanhamento de Vagas:** Permitir que o usuário salve vagas de interesse e acompanhe suas candidaturas.
*   **Melhor Tratamento de Erros:** Adicionar validações e tratamento de erros mais robustos.

## ✍️ Autor

*   [Seu Nome/Nickname] - [Link para seu GitHub ou LinkedIn, se quiser]

---

Sinta-se à vontade para adaptar este README, adicionar sua foto de perfil no GitHub, ou incluir qualquer outra informação que ache relevante!

# Aprendizado por Projeto Integrado - Seven Solutions 1° Semestre (API)

Desenvolver o Observatório de Inovação de São José dos Campos, uma solução de análise e visualização de dados em Power BI que mapeia o ecossistema industrial e de serviços do município a partir de dados da Relação Anual de Informações Sociais (RAIS), em parceria com o CADI e a Secretaria de Inovação e Desenvolvimento Econômico de São José dos Campos.


# Índice
* [Projeto (API)](#projeto-api)
* [Equipe](#equipe)
* [Objetivo do Projeto](#objetivo-do-projeto)
* [Tecnologias Utilizadas](#tecnologias-utilizadas)
* [Fontes dos Dados](#fontes-dos-dados)
* [Personas](#personas)
* [Product Backlog](#product-backlog)
* [Critérios de Aceitação](#critérios-de-aceitação)
* [Competências desenvolvidas](#competências-desenvolvidas)
* [Registro das Sprints](#registro-das-sprints)


# Projeto (API)
Projeto pedagógico alicerçado na Metodologia API para ensino-aprendizado focado no desenvolvimento de competências e fundamentado nos pilares de aprendizado com problemas reais (RPBL), validação externa e metodologia ágil.
Uso de estratégias para entender o problema, conceber uma solução viável, desenvolver e implementar o MVP, seguido de sua operação (CDIO).
Os resultados dos projetos devem obedecer ao Aviso Legal disponível no site da Fatec SJC, com definição das datas do kickoff e das sprints.

**Tema do semestre:** Mapeamento do Ecossistema Industrial e de Serviços da Região de São José dos Campos.

# Equipe

|    Função     | Nome | LinkedIn & GitHub |
| :-----------: | :--- | :---------------: |
| Product Owner | João Carlos Florencio de Sousa | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fsjoaocarlos/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/fsjuao) |
| Scrum Master | Maria Gessika da Silva | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maria-gessika-da-silva-44b900153/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/USUARIO_DA_GESSIKA) |
| Team Member | Carlos Eduardo Costa | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/carlos-eduardo-costa-13146697/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/caecosta2109-cmyk) |
| Team Member | Enzo Ferreira Martins de Paiva | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/enzo-ferreira-ba6619419/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/ZenzoFerreira) |
| Team Member | Giovanna Ferreira | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/giovanna-ferreira-047b13310/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/giovannaferreira304-stack) |
| Team Member | Juan Pereira Justino | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/juan-justino/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/juanpereirajustino-tech) |
| Team Member | Marcio Tavares da Rocha | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/m%C3%A1rcio-tavares-a15888452/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/MarcioR0CH4) |
| Team Member | Thais Helena Gomes Ambrósio | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/thais-ambr%C3%B3sio-3a3a581aa/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/thaishelenaambrosio1985-dev) |


# Objetivo do Projeto
Desenvolver o **Observatório de Inovação de São José dos Campos**, uma plataforma de visualização de dados em Power BI que apresenta indicadores econômicos e produtivos do município a partir da base da **RAIS** (Relação Anual de Informações Sociais), do Ministério do Trabalho e Emprego, visando:
* Identificar e organizar informações sobre os principais setores industriais e de serviços do município;
* Representar a distribuição geográfica dos estabelecimentos e setores produtivos;
* Apresentar indicadores de emprego formal (vínculos ativos) por setor;
* Apoiar a tomada de decisão de gestores públicos, empresas parceiras, potenciais investidores e cidadãos;
* Fomentar o diálogo entre governo, empresas e academia, segundo o modelo da **hélice tríplice**.


# Tecnologias Utilizadas

| Tecnologia | Uso no projeto | Requisito |
|------------|----------------|-----------|
| Google Colab | Acesso e organização dos dados públicos e institucionais | RN.P.1 |
| Python 3+ (pandas e numpy) | Extração, filtragem (município de SJC), verificação da qualidade e tratamento dos dados da RAIS | RN.P.2 |
| Power BI | Modelagem dos dados (modelo em estrela) e visualização no Observatório | RN.P.3 |
| GitHub | Versionamento do código e documentação técnica | RN.P.4 |
| Anthropic Claude | Criação da identidade visual e do background do painel | RN.P.4 |


# Fontes dos Dados

Bases de dados utilizadas na construção do dashboard ao longo das sprints.

| Fonte | Conteúdo utilizado | Uso no dashboard | Sprint |
|-------|--------------------|------------------|:------:|
| [RAIS Estabelecimentos – Ministério do Trabalho e Emprego](https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/acoes-e-programas/programas-projetos-acoes-obras-e-atividades/estatisticas-trabalho/rais/rais-2024) | Arquivo público `RAIS_ESTAB_PUB`, ano-base 2024, filtrado para São José dos Campos (código IBGE `354990`) | Tabela fato com os estabelecimentos e os vínculos ativos (CLT e estatutários) | 1, 2 e 3 |
| [CONCLA/IBGE – Comissão Nacional de Classificação](https://concla.ibge.gov.br/) | Tabelas oficiais da CNAE 2.0 (seção, divisão, grupo, classe e subclasse), da CNAE 95 e dos subsetores do IBGE | Descrição das atividades econômicas, tabela dimensão de atividade, hierarquia CNAE com navegação por níveis e agrupamento dos subsetores em Agropecuária, Indústria, Construção, Comércio e Serviços | 1, 2 e 3 |
| [Base dos Dados – dicionário da RAIS](https://basedosdados.org/dataset/3e7c4d58-96ba-448e-b053-d385a829ef00?table=86b69f96-0bfe-45da-833b-6edc9a0af213) | Significado dos demais códigos da RAIS | Tabelas dimensão de porte da empresa (faixas de tamanho do estabelecimento), Simples Nacional e natureza jurídica | 1, 2 e 3 |
| [Mendeley Data – CEPs por bairro](https://data.mendeley.com/datasets/g97jb8fp57/1) | Códigos de CEP com UF, cidade, bairro e logradouro | Tabela dimensão de CEP, com a localização dos estabelecimentos por zona e bairro de São José dos Campos | 3 |

## RAIS Estabelecimentos
A RAIS mede o estoque de emprego formal em 31 de dezembro. A versão pública não identifica as empresas (não traz CNPJ nem razão social), por isso o painel apresenta os dados por setor, atividade econômica, porte e CEP. A base não informa admissões, desligamentos, remuneração nem investimento em P&D.

## Relação CEP × Bairro (Mendeley Data)
Para agrupar os estabelecimentos por **zona e bairro de São José dos Campos**, os CEPs da RAIS foram cruzados com uma base complementar publicada no Mendeley Data. Essa base não faz parte da RAIS e foi usada só para a classificação por zona e bairro. CEPs sem correspondência foram marcados como `Bairro não identificado`.

> [!NOTE]
> Base disponibilizada sob licença [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Os CEPs estão atualizados até 2018, então CEPs criados depois disso podem não ter bairro associado.

# Personas

| Tipo de Usuário | Descrição / Interesse Principal | Necessidade Representativa |
|-----------------|---------------------------------|----------------------------|
| Gestor Público | Servidores da Secretaria de Desenvolvimento Econômico/CADI responsáveis por planejar políticas de fomento industrial e de inovação | Identificar setores estratégicos e monitorar o desenvolvimento econômico da cidade |
| Empresa Parceira | Empresas já estabelecidas na região, com interesse no ecossistema de inovação de SJC | Mapear sinergias e identificar possíveis parceiros no mesmo setor ou que possam agregar valor |
| Parceiro em Potencial | Empresas ou investidores externos avaliando a instalação de operações na região | Comparar indicadores entre setores para embasar decisões de investimento |
| Cidadão (pesquisadores, estudantes e jornalistas) | Acesso ao painel para fins acadêmicos, jornalísticos ou de acesso à informação | Consultar dados abertos, confiáveis e com metodologia transparente |


# Product Backlog

| Rank | Prioridade | User Story | Estimativa | Sprint | Requisito do Parceiro |
|------|------------|------------|------------|--------|-----------------------|
| 1  | Alta  | Como cidadão, quero acessar o Observatório publicamente e sem necessidade de login, para exercer meu direito de acesso à informação sobre os dados referentes à economia do município (Lei de Acesso à Informação) | 3  | 1 | RN.P.3, RN.P.5 |
| 2  | Alta  | Como usuário do Observatório, quero navegar por uma página inicial com indicação dos pontos tratados na análise de São José dos Campos, para ter uma visão geral rápida antes de aprofundar a análise | 5  | 1 | RN.P.3, RN.P.5 |
| 3  | Alta  | Como equipe de desenvolvimento, quero automatizar a extração dos dados da base RAIS nacional e filtrar apenas os registros do município de São José dos Campos, para garantir uma base de dados confiável e atualizável | 13 | 1 | RN.P.1, RN.P.2 |
| 4  | Alta  | Como equipe de desenvolvimento, quero versionar os scripts de tratamento de dados e a documentação do projeto no GitHub, para garantir rastreabilidade, colaboração e transparência do processo | 2  | 1 | RN.P.4, RN.P.6 |
| 5  | Alta  | Como gestor público, quero visualizar um mapa dos setores industriais e de serviços predominantes na região, para identificar oportunidades de fomento e atração de investimentos | 8  | 1 | RN.P.3, RN.P.5 |
| 6  | Alta  | Como usuário do Observatório, quero utilizar filtros por setor econômico e porte da empresa, para localizar rapidamente a informação relevante para minha análise | 5  | 1 | RN.P.3, RN.P.5 |
| 7  | Alta  | Como gestor público, quero visualizar indicadores de vínculos por setor, para compreender a dinâmica do mercado de trabalho local e orientar políticas públicas | 5  | 2 | RN.P.3 |
| 8  | Alta  | Como gestor público, quero visualizar, no mesmo painel, indicadores relacionados aos setores econômicos e de serviços, para embasar políticas de fomento ao diálogo entre esses atores | 8  | 2 | RN.P.3, RN.P.5 |
| 9  | Alta  | Como empresa parceira, quero identificar outros ramos do mesmo setor produtivo presentes na região, para mapear possíveis sinergias ou parcerias estratégicas | 8  | 2 | RN.P.3 |
| 10 | Alta  | Como empresa parceira, quero visualizar a distribuição geográfica das empresas por setor no município, para identificar clusters produtivos próximos ao meu negócio | 8  | 2 | RN.P.3, RN.P.5 |
| 11 | Média | Como parceiro em potencial, quero comparar indicadores econômicos entre diferentes setores da região, para apoiar minha decisão sobre onde investir ou instalar uma nova operação | 5  | 3 | RN.P.3 |
| 12 | Média | Como pesquisador, quero visualizar a classificação das atividades econômicas segundo a Classificação Nacional de Atividades Econômicas (CNAE), para relacionar os dados da RAIS a categorias produtivas | 5  | 3 | RN.P.2, RN.P.3 |
| 13 | Média | Como empresa parceira, quero visualizar quais setores concentram a maior geração de empregos formais, para identificar players relevantes para possíveis parcerias | 3  | 3 | RN.P.3 |
| 14 | Média | Como gestor público, quero dispor de diversos filtros para aprofundar minha análise referente à estrutura produtiva do município | 3  | 3 | RN.P.3 |

> Estimativas em *story points* (escala de Fibonacci). O backlog é passível de revisão e refinamento ao longo das Sprints, em conjunto com o cliente.


# Critérios de Aceitação

**"Como empresa parceira ou em potencial, quero visualizar os principais motores econômicos da região, para estimar os melhores espaços de inserção, oportunidades e parcerias comerciais e de desenvolvimento no município de São José dos Campos."**
* O painel deve apresentar a distribuição geográfica das empresas;
* Os dados macroeconômicos da região devem ser expostos em primeiro plano;
* Os resultados do processamento de busca devem ser concentrados em painel único, possibilitando filtragem por cadeia produtiva ou setor econômico;
* A disposição geográfica das atividades econômicas deve permitir a busca por zonas e bairros da cidade.

**"Como gestor público, quero visualizar, no mesmo painel, as principais atividades econômicas e seus respectivos setores produtivos, para embasar políticas de fomento ao diálogo entre esses atores e o desenvolvimento econômico da região."**
* O painel deve apresentar uma seção específica que relacione indicadores das atividades produtivas com planta no município e sua relevância econômica na cidade;
* Deve ser possível filtrar a visualização por setor produtivo;
* A navegação deve ser fluida e intuitiva;
* Deve haver indicação clara da fonte de cada indicador exibido.


# Competências desenvolvidas
* Introdução aos fundamentos de cadeia de suprimentos;
* Leitura, organização e interpretação de dados econômicos e industriais;
* Pensamento computacional aplicado a problemas reais;
* Comunicação técnica e elaboração de relatórios;
* Trabalho em equipe e organização de projetos;
* Visão sistêmica de processos produtivos e de serviços;
* Uso de ferramentas digitais para análise e visualização de dados;
* Metodologia ágil para planejamento e execução do projeto.


# Registro das Sprints

| Sprint            |  Entrega   | Status   | Histórico |
|-------------------|------------|----------|-----------|
| 01                | 28/09/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp1.md)  |
| 02                | 02/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp2.md)  |
| 03                | 27/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp3.md)  |
| Feira de Soluções | dd/mm/aaaa | a fazer  | [MVP](#)  |

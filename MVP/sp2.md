# MVP - Sprint 2: Modelagem dos Dados e Painel de Indicadores do Observatório

## Objetivo do MVP
> O propósito deste MVP é refazer a filtragem dos dados da RAIS, construir os relacionamentos entre as tabelas e apresentar, no Power BI, um painel público e navegável com os indicadores de emprego formal de São José dos Campos por setor, porte da empresa, atividade e localização.
- **Qual problema resolve?** A ausência de um mapeamento estruturado da estrutura produtiva do município, apontada pelo CADI e pela Secretaria de Inovação e Desenvolvimento Econômico, e a base de dados da Sprint 1, que ainda tinha registros duplicados, colunas sem informação e códigos sem descrição.
- **Qual hipótese será validada?** Organizar a RAIS em um modelo de dados relacional e apresentá-la em um painel com filtros por setor, porte da empresa e atividade permite identificar os setores predominantes do município e apoiar decisões da gestão pública.
- **Qual valor será entregue ao usuário final?** Uma visão clara e de acesso público sobre quais setores e atividades mais empregam em São José dos Campos, qual o porte das empresas e onde os estabelecimentos estão localizados.

---

## Descrição da Solução
> O que é entregue nesta etapa é a base de dados tratada e modelada e o painel do Observatório de Inovação, com três páginas publicadas na web.
- **Funcionalidades principais incluídas:**
    - Filtragem refeita da RAIS Estabelecimentos 2024 para o município (código IBGE 354990), com remoção dos registros duplicados: 42.362 estabelecimentos e 204.684 vínculos ativos.
    - Modelo em estrela com uma tabela fato e cinco tabelas dimensão (atividade, porte da empresa, Simples Nacional, natureza jurídica e localidade), ligadas por relacionamentos 1:*. As tabelas dimensão foram construídas com as tabelas da CONCLA/IBGE e da Base dos Dados e são responsáveis pelo funcionamento dos filtros do painel.
    - Classificação dos setores em Agropecuária, Indústria, Construção, Comércio e Serviços, a partir do subsetor do IBGE.
    - Página **Início**, com o objetivo do Observatório e a navegação.
    - Página **Indicadores Econômicos**, com vínculos ativos, CLT e estatutários e os vínculos por setor, porte da empresa e atividade (CNAE 2.0), além da participação das optantes pelo Simples Nacional.
    - Página **Distribuição Geográfica**, com mapa dos vínculos ativos por CEP, vínculos por atividade e vínculos e estabelecimentos por subsetor do IBGE.
    - Filtros por porte da empresa, subsetor IBGE e subclasse CNAE 2.0, e botões de navegação entre as páginas.
    - Identidade visual do painel, com backgrounds das páginas criados com o Anthropic Claude.
    - Publicação do painel com acesso público, sem necessidade de login.
- **Limitações conhecidas:**
    - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social).
    - A base mede o estoque de emprego em 31/12. Ela não informa admissões e desligamentos nem mede inovação ou investimento em P&D.
    - A localização é aproximada pelo CEP, e a base cobre apenas o município de São José dos Campos.
- **Escopo reduzido (somente o essencial para validar a ideia):**
    Base tratada e modelada e painel com indicadores de vínculos ativos por setor, porte da empresa, atividade e localização, publicado com acesso público.

---

## Fontes dos Dados
- **RAIS Estabelecimentos** ([Ministério do Trabalho e Emprego](https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/acoes-e-programas/programas-projetos-acoes-obras-e-atividades/estatisticas-trabalho/rais/rais-2024)), **ano-base 2024**, filtrada para o município de São José dos Campos (código IBGE `354990`).
- **[CONCLA/IBGE](https://concla.ibge.gov.br/)** (Comissão Nacional de Classificação): tabelas oficiais da CNAE e dos subsetores do IBGE, usadas para dar descrição aos códigos de atividade econômica da RAIS.
- **[Base dos Dados](https://basedosdados.org/dataset/3e7c4d58-96ba-448e-b053-d385a829ef00?table=86b69f96-0bfe-45da-833b-6edc9a0af213)**: dicionário da RAIS, usado para dar significado aos demais códigos da base, como as faixas de porte da empresa.

> As fontes complementares (CONCLA/IBGE e Base dos Dados) foram adotadas na Sprint 1 para dar significado aos códigos da RAIS. Nesta sprint, elas foram usadas para construir as tabelas dimensão do modelo, que fazem os filtros do painel funcionar.

---

## Personas / Usuários-Alvo

| Tipo de Usuário | Descrição / Interesse Principal | Necessidade Representativa |
|-----------------|---------------------------------|----------------------------|
| Gestor Público | Servidores da Secretaria de Desenvolvimento Econômico/CADI responsáveis por planejar políticas de fomento industrial e de inovação | Identificar setores estratégicos e monitorar o desenvolvimento econômico da cidade |
| Empresa Parceira | Empresas já estabelecidas na região, com interesse no ecossistema de inovação de SJC | Mapear sinergias e identificar possíveis parceiros no mesmo setor ou que possam agregar valor |
| Parceiro em Potencial | Empresas ou investidores externos avaliando a instalação de operações na região | Comparar indicadores entre setores para embasar decisões de investimento |
| Cidadão (pesquisadores, estudantes e jornalistas) | Acesso ao painel para fins acadêmicos, jornalísticos ou de acesso à informação | Consultar dados abertos, confiáveis e com metodologia transparente |

---

## Product Backlog (Sprint 2)

| Rank | Prioridade | User Story | Estimativa | Sprint | Requisito do Parceiro |
|------|------------|------------|------------|--------|-----------------------|
| 7  | Alta  | Como gestor público, quero visualizar indicadores de vínculos por setor, para compreender a dinâmica do mercado de trabalho local e orientar políticas públicas | 5  | 2 | RN.P.3 |
| 8  | Alta  | Como gestor público, quero visualizar, no mesmo painel, indicadores relacionados aos setores econômicos e de serviços, para embasar políticas de fomento ao diálogo entre esses atores | 8  | 2 | RN.P.3, RN.P.5 |
| 9  | Alta  | Como empresa parceira, quero identificar outros ramos do mesmo setor produtivo presentes na região, para mapear possíveis sinergias ou parcerias estratégicas | 8  | 2 | RN.P.3 |
| 10 | Alta  | Como empresa parceira, quero visualizar a distribuição geográfica das empresas por setor no município, para identificar clusters produtivos próximos ao meu negócio | 8  | 2 | RN.P.3, RN.P.5 |

> Estimativas em *story points* (escala de Fibonacci).

---

## Sprint(s) Relacionadas
| Sprint | Entregas Principais | Status |
|--------|---------------------|--------|
| 01 | Extração e filtragem da RAIS para o município em Python (Google Colab), verificação da qualidade dos dados, backlog do produto e primeira versão do painel. | Concluída |
| 02 | Filtragem refeita com remoção dos registros duplicados, modelo de dados em estrela com relacionamentos entre as tabelas, novo layout do painel com três páginas, página inicial de apresentação e publicação com acesso público. | Concluída |
| 03 | Análise dos macroprocessos produtivos, relação dos CEPs com os bairros do município (Mendeley Data), indicadores-resumo na página inicial e comparação entre setores. | Concluída |

---

## Critérios de Aceitação
- A base tratada deve conferir com o arquivo de origem: 42.362 estabelecimentos e 204.684 vínculos ativos.
- As tabelas dimensão devem se relacionar com a tabela fato em relacionamentos 1:*, sem registros sem correspondência.
- O painel deve apresentar os vínculos ativos por setor, porte da empresa, atividade e localização.
- Deve ser possível filtrar a visualização por porte da empresa, subsetor IBGE e subclasse CNAE 2.0.
- A navegação entre as páginas deve ser fluida e intuitiva.
- A fonte dos dados deve estar indicada em todas as páginas.
- O painel deve ser acessível publicamente, sem necessidade de login.
- **Métricas coletadas:** total de vínculos ativos, estabelecimentos com vínculos, participação de cada setor no emprego formal e participação das optantes pelo Simples Nacional.

---

## Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions. A validação com o cliente (CADI e Secretaria de Inovação e Desenvolvimento Econômico) ocorreu na apresentação da Sprint 2.
- **Feedback qualitativo (positivo/negativo):** Avaliação do cliente sobre a clareza dos indicadores e a facilidade de navegação, a ser registrada após a apresentação da Sprint 2.
- **Consistência dos dados:** Os totais do painel conferem com a base de origem: 204.684 vínculos ativos, 204.593 CLT e 91 estatutários.
- **Resultados apresentados pelo painel:**
    - Serviços concentram 51% dos vínculos ativos, seguidos pelo comércio (22%), pela indústria (21%) e pela construção civil (5%).
    - A fabricação de aeronaves é a atividade de maior peso, com 11.069 vínculos.
    - 63% dos 14.380 estabelecimentos com vínculos são optantes pelo Simples Nacional.

---

## Próximos Passos
- **Melhorias planejadas após feedback:** Ajustes nos indicadores e nos visuais conforme a avaliação do cliente na apresentação da Sprint 2.
- **Ajustes de usabilidade:** Indicadores-resumo na página inicial, ordenação da tabela de atividades e das faixas de porte da empresa, e agrupamento dos CEPs por região da cidade no mapa.
- **Expansão de funcionalidades para próximo incremento:** Análise dos macroprocessos produtivos, comparação entre setores e avaliação de fontes complementares, como o Novo CAGED (admissões e desligamentos) e os dados abertos de CNPJ (identificação das empresas).

---

## Anexos / Evidências

**Vídeo explicativo:**

https://github.com/user-attachments/assets/8593fb50-1975-4d2e-b786-70efa1943553

**Página Início**

<img width="1912" height="1064" alt="Página Início" src="https://github.com/user-attachments/assets/c876431d-2e3e-4c13-b530-d96e7028f3d6" />

**Página Indicadores Econômicos**

<img width="1910" height="1057" alt="Página Indicadores Econômicos" src="https://github.com/user-attachments/assets/2b27e5f8-f231-47cb-beda-349d06bee3ee" />

**Página Distribuição Geográfica**

<img width="1917" height="1078" alt="Página Distribuição Geográfica" src="https://github.com/user-attachments/assets/90e64b2e-6310-48f5-9266-72be116d0c3a" />

- Notebook de filtragem e refinamento dos dados (Google Colab): [Clique aqui](https://colab.research.google.com/drive/1du7vjnBfTXE3x-BC8cTGXzjk2bXjFn-6?usp=sharing)
- Plataforma BI: [Clique aqui](https://app.powerbi.com/view?r=eyJrIjoiNmMyNDNmMzUtMjk5Yi00ZTM1LTlmY2EtNDlhYzgxZmQzYzhjIiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9)
- Relatório da Sprint 2: [Relatorio_Sprint2.docx](https://github.com/user-attachments/files/34300636/Relatorio_Sprint2.docx)

---

## Registro das Sprints

| Sprint            |  Entrega   | Status   | Histórico |
|-------------------|------------|----------|-----------|
| 01                | 28/09/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp1.md)  |
| 03                | 27/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp3.md)  |
| Feira de Soluções | dd/mm/aaaa | a fazer  | [MVP](#)  |

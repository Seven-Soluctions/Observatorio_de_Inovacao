# MVP - Sprint 1: Extração dos Dados da RAIS e Primeira Versão do Painel

## Objetivo do MVP
> O propósito deste MVP é extrair da base nacional da RAIS os dados do município de São José dos Campos, organizá-los em Python e apresentar, no Power BI, uma primeira versão do painel do Observatório de Inovação com os setores, os vínculos de emprego formal e a localização dos estabelecimentos.
- **Qual problema resolve?** A ausência de um mapeamento estruturado da estrutura produtiva do município, apontada pelo CADI e pela Secretaria de Inovação e Desenvolvimento Econômico. Os dados da RAIS existem, mas estão em uma base nacional, extensa e em formato técnico, de difícil leitura.
- **Qual hipótese será validada?** Filtrar a RAIS para o município e apresentá-la em um painel com gráficos, mapa e filtros por setor e porte da empresa permite ter uma primeira visão de quais setores predominam em São José dos Campos.
- **Qual valor será entregue ao usuário final?** Uma primeira visão de quais setores reúnem mais estabelecimentos e vínculos de emprego formal no município e de onde esses estabelecimentos estão localizados.

---

## Descrição da Solução
> O que é entregue nesta etapa é o script de extração e filtragem da RAIS e a primeira versão do painel do Observatório, em uma única página.
- **Funcionalidades principais incluídas:**
    - Script em Python, no Google Colab, que lê a RAIS Estabelecimentos 2024 e filtra os registros do município de São José dos Campos (código IBGE 354990).
    - Verificação inicial da qualidade dos dados filtrados.
    - Tradução dos códigos da RAIS (subsetores, atividades e porte) para suas descrições, com base nas tabelas da CONCLA/IBGE e da Base dos Dados.
    - Gráfico **Principais setores econômicos**, com a quantidade de estabelecimentos por subsetor do IBGE.
    - Gráfico **Vínculos ativos**, com o total de vínculos do município distribuído por subsetor do IBGE.
    - Gráfico **Vínculos nos top 10 setores**, com os dez subsetores que mais empregam.
    - **Mapa** dos estabelecimentos por CEP.
    - Cartão com o **total de vínculos**.
    - Filtros por subsetor do IBGE (com abertura por classe da CNAE 95) e por porte da empresa.
    - Repositório no GitHub com o backlog do produto e a documentação do projeto.
- **Limitações conhecidas:**
    - A base filtrada ainda tinha registros duplicados, colunas sem informação e códigos sem descrição, como as faixas de porte da empresa, que aparecem apenas como números de 1 a 10. Por causa das duplicatas, os totais desta versão não coincidem com os das sprints seguintes, e a filtragem precisou ser refeita na Sprint 2.
    - As atividades foram apresentadas pela CNAE 95, classificação anterior à CNAE 2.0.
    - O painel tem uma única página, sem página inicial de apresentação e sem botões de navegação.
    - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social), e a localização é aproximada pelo CEP.
- **Escopo reduzido (somente o essencial para validar a ideia):**
    Extração e filtragem da RAIS para o município e um painel de uma página com estabelecimentos e vínculos por subsetor, mapa por CEP e filtros por subsetor e porte da empresa.

---

## Fontes dos Dados
- **RAIS Estabelecimentos** ([Ministério do Trabalho e Emprego](https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/acoes-e-programas/programas-projetos-acoes-obras-e-atividades/estatisticas-trabalho/rais/rais-2024)), **ano-base 2024**, filtrada para o município de São José dos Campos (código IBGE `354990`).
- **[CONCLA/IBGE](https://concla.ibge.gov.br/)** (Comissão Nacional de Classificação): tabelas oficiais da CNAE e dos subsetores do IBGE, usadas para dar descrição aos códigos de atividade econômica da RAIS.
- **[Base dos Dados](https://basedosdados.org/dataset/3e7c4d58-96ba-448e-b053-d385a829ef00?table=86b69f96-0bfe-45da-833b-6edc9a0af213)**: dicionário da RAIS, usado para dar significado aos demais códigos da base, como as faixas de porte da empresa.

---

## Personas / Usuários-Alvo

| Tipo de Usuário | Descrição / Interesse Principal | Necessidade Representativa |
|-----------------|---------------------------------|----------------------------|
| Gestor Público | Servidores da Secretaria de Desenvolvimento Econômico/CADI responsáveis por planejar políticas de fomento industrial e de inovação | Identificar setores estratégicos e monitorar o desenvolvimento econômico da cidade |
| Empresa Parceira | Empresas já estabelecidas na região, com interesse no ecossistema de inovação de SJC | Mapear sinergias e identificar possíveis parceiros no mesmo setor ou que possam agregar valor |
| Parceiro em Potencial | Empresas ou investidores externos avaliando a instalação de operações na região | Comparar indicadores entre setores para embasar decisões de investimento |
| Cidadão (pesquisadores, estudantes e jornalistas) | Acesso ao painel para fins acadêmicos, jornalísticos ou de acesso à informação | Consultar dados abertos, confiáveis e com metodologia transparente |

---

## Product Backlog (Sprint 1)

| Rank | Prioridade | User Story | Estimativa | Sprint | Requisito do Parceiro |
|------|------------|------------|------------|--------|-----------------------|
| 1  | Alta  | Como cidadão, quero acessar o Observatório publicamente e sem necessidade de login, para exercer meu direito de acesso à informação sobre os dados referentes à economia do município (Lei de Acesso à Informação) | 3  | 1 | RN.P.3, RN.P.5 |
| 2  | Alta  | Como usuário do Observatório, quero navegar por uma página inicial com indicação dos pontos tratados na análise de São José dos Campos, para ter uma visão geral rápida antes de aprofundar a análise | 5  | 1 | RN.P.3, RN.P.5 |
| 3  | Alta  | Como equipe de desenvolvimento, quero automatizar a extração dos dados da base RAIS nacional e filtrar apenas os registros do município de São José dos Campos, para garantir uma base de dados confiável e atualizável | 13 | 1 | RN.P.1, RN.P.2 |
| 4  | Alta  | Como equipe de desenvolvimento, quero versionar os scripts de tratamento de dados e a documentação do projeto no GitHub, para garantir rastreabilidade, colaboração e transparência do processo | 2  | 1 | RN.P.4, RN.P.6 |
| 5  | Alta  | Como gestor público, quero visualizar um mapa dos setores industriais e de serviços predominantes na região, para identificar oportunidades de fomento e atração de investimentos | 8  | 1 | RN.P.3, RN.P.5 |
| 6  | Alta  | Como usuário do Observatório, quero utilizar filtros por setor econômico e porte da empresa, para localizar rapidamente a informação relevante para minha análise | 5  | 1 | RN.P.3, RN.P.5 |

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
- O script deve filtrar apenas os registros do município de São José dos Campos (código IBGE 354990).
- O painel deve apresentar a quantidade de estabelecimentos e os vínculos ativos por subsetor do IBGE.
- O painel deve apresentar a distribuição geográfica dos estabelecimentos em um mapa.
- Deve ser possível filtrar a visualização por subsetor do IBGE e por porte da empresa.
- O script e a documentação devem estar versionados no GitHub.
- **Métricas coletadas:** total de vínculos ativos, estabelecimentos por subsetor e vínculos por subsetor.

---

## Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions. A validação com o cliente (CADI e Secretaria de Inovação e Desenvolvimento Econômico) ocorreu na apresentação da Sprint 1.
- **Feedback qualitativo (positivo/negativo):**
    - A verificação da base mostra registros duplicados, colunas sem informação e códigos sem descrição, o que indica a necessidade de refazer a filtragem e a modelagem dos dados.
    - É necessário repensar a escolha dos visuais, alguns mostram as mesmas informações, apenas de diferentes formas
- **Resultados apresentados pelo painel** (ainda com registros duplicados):
    - Cerca de 207 mil vínculos ativos no município.
    - Comércio e administração de imóveis e valores mobiliários é o subsetor com mais estabelecimentos (15,2 mil, 34% do total), seguido pelo comércio varejista (10,3 mil, 23%) e pelos serviços de alojamento e alimentação (5 mil, 11%).
    - Os subsetores que mais empregam são comércio e administração de imóveis e valores mobiliários (cerca de 39 mil vínculos) e comércio varejista (cerca de 38 mil), seguidos por serviços de alojamento e alimentação (22 mil) e serviços médicos, odontológicos e veterinários (17 mil).

---

## Próximos Passos
- **Melhorias planejadas após feedback:** Refazer a filtragem da RAIS, eliminando duplicidades e colunas sem informação, e incluir as descrições dos códigos.
- **Ajustes de usabilidade:** Criar uma página inicial de apresentação, dividir o painel em páginas temáticas com botões de navegação e substituir os códigos de porte da empresa por faixas descritas.
- **Expansão de funcionalidades para próximo incremento:** Modelo de dados em estrela com relacionamentos entre as tabelas, classificação das atividades pela CNAE 2.0, agrupamento dos subsetores em Agropecuária, Indústria, Construção, Comércio e Serviços e publicação do painel com acesso público.

---

## Anexos / Evidências

**Vídeo explicativo:**

https://github.com/user-attachments/assets/16512ea3-3a93-4f64-bce4-770e60a05f72

**Painel da Sprint 1**

<img width="1365" height="767" alt="Painel da Sprint 1" src="https://github.com/user-attachments/assets/2cc0f39a-3e2e-41b8-aa45-510b181e1ab4" />

- Plataforma BI: [Clique aqui](https://app.powerbi.com/view?r=eyJrIjoiMzM1ZjFmYzYtMjhiNC00Zjk2LTg0OWItY2ExYjE2NDliMDI1IiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9&pageName=b0eda75f0b95818c30e0)
- Relatório da Sprint 1: *a ser inserido*

---

## Registro das Sprints

| Sprint            |  Entrega   | Status   | Histórico |
|-------------------|------------|----------|-----------|
| 02                | 02/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp2.md)  |
| 03                | 27/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp3.md)  |
| Feira de Soluções | dd/mm/aaaa | a fazer  | [MVP](#)  |

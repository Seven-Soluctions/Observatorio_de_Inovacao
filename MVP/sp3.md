# MVP - Sprint 3: Cadeias Produtivas, Classificação CNAE e Comparação entre Setores

## Objetivo do MVP
> O propósito deste MVP é ampliar o painel do Observatório de Inovação com a análise dos macroprocessos produtivos de São José dos Campos, a classificação das atividades segundo a hierarquia da CNAE 2.0, a comparação de indicadores entre setores e a relação dos estabelecimentos com os bairros do município, além de trazer os principais números do município para a página inicial.
- **Qual problema resolve?** O painel da Sprint 2 mostrava os vínculos por setor, porte da empresa e atividade, mas não permitia comparar os setores lado a lado, não agrupava as atividades em cadeias produtivas, localizava os estabelecimentos apenas pelo CEP e exigia que o usuário navegasse até a segunda página para ver os principais números do município.
- **Qual hipótese será validada?** Agrupar as atividades da RAIS em cadeias produtivas e apresentar os setores em visuais comparativos permite que gestores, empresas e investidores identifiquem quais setores concentram o emprego formal e onde estão as oportunidades de parceria e investimento.
- **Qual valor será entregue ao usuário final?** Uma leitura rápida da economia do município já na página inicial, a comparação direta entre setores, a visão das cadeias produtivas e de suas atividades, organizadas segundo a CNAE, e a localização dos estabelecimentos por bairro.

---

## Descrição da Solução
> O que é entregue nesta etapa é a nova versão do painel do Observatório, com indicadores-resumo na página inicial, duas novas páginas (Comparação entre Setores e Cadeias Produtivas) e a relação dos CEPs com os bairros do município.
- **Funcionalidades principais incluídas:**
    - Página **Início** com indicadores-resumo em destaque: 204.684 vínculos ativos, 42.362 estabelecimentos, 14.380 estabelecimentos com vínculos, setor predominante (Serviços, 51% dos vínculos) e atividade de maior peso (fabricação de aeronaves, 11.069 vínculos).
    - Nova página **Comparação entre Setores**, com vínculos ativos, estabelecimentos, participação no emprego formal e média de vínculos por estabelecimento para Agropecuária, Indústria, Construção, Comércio e Serviços, lado a lado.
    - Ranking das atividades (subclasse CNAE 2.0) que mais geram empregos formais, com a participação acumulada de cada uma no total de vínculos.
    - Hierarquia da CNAE 2.0 (seção, divisão, grupo, classe e subclasse) na tabela dimensão de atividade, com navegação por níveis (*drill down*) nos visuais.
    - Nova página **Cadeias Produtivas**, que agrupa as atividades nos macroprocessos produtivos relevantes para o município, com vínculos, estabelecimentos e atividades de cada cadeia. Foram consideradas as 19 atividades (subclasse CNAE 2.0) com mais de 2.000 vínculos ativos cada, que somam 72.247 vínculos (cerca de 35% do total), associadas a dez macroprocessos: serviços de apoio às empresas (19.657 vínculos), aeroespacial e defesa (11.069), saúde (10.359), varejo e abastecimento (7.429), alimentação (6.861), educação (4.346), engenharia e serviços técnicos (3.628), automotiva (3.415), construção civil (2.947) e logística e transporte (2.536). As demais atividades ficam em "Demais atividades".
    - Relação dos CEPs da RAIS com as **zonas e os bairros de São José dos Campos**, a partir da base do Mendeley Data, para agrupar os estabelecimentos e os vínculos por zona e bairro.
    - Filtros por cadeia produtiva e por zona e bairro, somados aos filtros de porte da empresa, subsetor IBGE e subclasse CNAE 2.0 da Sprint 2.
    - Ajustes de usabilidade apontados na Sprint 2, todos implementados: ordenação da tabela de atividades e das faixas de porte da empresa e agrupamento dos CEPs por zona e bairro da cidade.
- **Limitações conhecidas:**
    - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social), por isso as cadeias produtivas são montadas a partir das atividades (CNAE) e não das empresas.
    - Uma mesma atividade pode servir a mais de uma cadeia. No painel, cada atividade foi associada a uma única cadeia, a de maior aderência.
    - A base do Mendeley Data tem CEPs atualizados até 2018, então CEPs criados depois disso podem ficar sem bairro associado. Esses CEPs não aparecem no filtro de bairro, mas seus vínculos continuam contabilizados nos demais visuais e nos totais do painel.
    - A base mede o estoque de emprego em 31/12. Ela não informa admissões, desligamentos, remuneração nem investimento em P&D.
    - A comparação é feita apenas dentro do município. Ainda não há comparação com o estado ou com o país.
- **Escopo reduzido (somente o essencial para validar a ideia):**
    Indicadores-resumo na página inicial, comparação entre os cinco setores, ranking das atividades que mais empregam, hierarquia CNAE, agrupamento das atividades em cadeias produtivas e relação dos CEPs com os bairros.

---

## Fontes dos Dados
- **RAIS Estabelecimentos** ([Ministério do Trabalho e Emprego](https://www.gov.br/trabalho-e-emprego/pt-br/acesso-a-informacao/acoes-e-programas/programas-projetos-acoes-obras-e-atividades/estatisticas-trabalho/rais/rais-2024)), **ano-base 2024**, filtrada para o município de São José dos Campos (código IBGE `354990`).
- **[CONCLA/IBGE](https://concla.ibge.gov.br/)** (Comissão Nacional de Classificação): tabelas oficiais da CNAE e dos subsetores do IBGE, usadas para dar descrição aos códigos de atividade econômica da RAIS.
- **[Base dos Dados](https://basedosdados.org/dataset/3e7c4d58-96ba-448e-b053-d385a829ef00?table=86b69f96-0bfe-45da-833b-6edc9a0af213)**: dicionário da RAIS, usado para dar significado aos demais códigos da base, como as faixas de porte da empresa.
- **[Mendeley Data](https://data.mendeley.com/datasets/g97jb8fp57/1)**: base de CEPs por bairro, usada nesta sprint para associar os CEPs da RAIS às zonas e aos bairros de São José dos Campos.

    > ZIMMERMANN, Ivan. *Códigos de CEP do Brasil por UF, CIDADE, BAIRRO E LOGRADOURO (Brazil ZIP CODES)*. Mendeley Data, v1, 2019. DOI: [10.17632/g97jb8fp57.1](https://doi.org/10.17632/g97jb8fp57.1)

> [!NOTE]
> A base do Mendeley Data é disponibilizada sob licença [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) e não faz parte da RAIS. Ela foi usada só para a classificação por zona e bairro.

---

## Personas / Usuários-Alvo

| Tipo de Usuário | Descrição / Interesse Principal | Necessidade Representativa |
|-----------------|---------------------------------|----------------------------|
| Gestor Público | Servidores da Secretaria de Desenvolvimento Econômico/CADI responsáveis por planejar políticas de fomento industrial e de inovação | Identificar setores estratégicos e monitorar o desenvolvimento econômico da cidade |
| Empresa Parceira | Empresas já estabelecidas na região, com interesse no ecossistema de inovação de SJC | Mapear sinergias e identificar possíveis parceiros no mesmo setor ou que possam agregar valor |
| Parceiro em Potencial | Empresas ou investidores externos avaliando a instalação de operações na região | Comparar indicadores entre setores para embasar decisões de investimento |
| Cidadão (pesquisadores, estudantes e jornalistas) | Acesso ao painel para fins acadêmicos, jornalísticos ou de acesso à informação | Consultar dados abertos, confiáveis e com metodologia transparente |

---

## Product Backlog (Sprint 3)

| Rank | Prioridade | User Story | Estimativa | Sprint | Requisito do Parceiro |
|------|------------|------------|------------|--------|-----------------------|
| 11 | Média | Como parceiro em potencial, quero comparar indicadores econômicos entre diferentes setores da região, para apoiar minha decisão sobre onde investir ou instalar uma nova operação | 5  | 3 | RN.P.3 |
| 12 | Média | Como pesquisador, quero visualizar a classificação das atividades econômicas segundo a Classificação Nacional de Atividades Econômicas (CNAE), para relacionar os dados da RAIS a categorias produtivas | 5  | 3 | RN.P.2, RN.P.3 |
| 13 | Média | Como empresa parceira, quero visualizar quais setores concentram a maior geração de empregos formais, para identificar players relevantes para possíveis parcerias | 3  | 3 | RN.P.3 |
| 14 | Média | Como gestor público, quero dispor de diversos filtros para aprofundar minha análise referente à estrutura produtiva do município | 3  | 3 | RN.P.3 |

> Estimativas em *story points* (escala de Fibonacci).

---

## Sprint(s) Relacionadas
| Sprint | Entregas Principais | Status |
|--------|---------------------|--------|
| 01 | Extração e filtragem da RAIS para o município em Python (Google Colab), verificação da qualidade dos dados, backlog do produto e primeira versão do painel. | Concluída |
| 02 | Filtragem refeita com remoção dos registros duplicados, modelo de dados em estrela com relacionamentos entre as tabelas, novo layout do painel com três páginas, página inicial de apresentação e publicação com acesso público. | Concluída |
| 03 | Indicadores-resumo na página inicial, comparação entre setores, ranking das atividades que mais empregam, hierarquia CNAE, cadeias produtivas e relação dos CEPs com os bairros do município (Mendeley Data). | Concluída |

---

## Critérios de Aceitação
- Os indicadores-resumo da página inicial devem conferir com a base de origem: 42.362 estabelecimentos e 204.684 vínculos ativos.
- O painel deve permitir comparar, lado a lado, os vínculos ativos, os estabelecimentos e a participação no emprego formal dos cinco setores.
- O painel deve apresentar o ranking das atividades que mais geram empregos formais.
- A tabela dimensão de atividade deve conter os cinco níveis da CNAE 2.0, e os visuais devem permitir navegar entre eles.
- Toda atividade da base deve estar associada a uma cadeia produtiva ou à categoria "Demais atividades", sem registros sem correspondência.
- Os CEPs da base devem estar associados às zonas e aos bairros da cidade. Os vínculos de CEPs sem bairro associado devem continuar contabilizados nos totais e nos demais visuais.
- Deve ser possível filtrar a visualização por cadeia produtiva, zona e bairro, porte da empresa, subsetor IBGE e subclasse CNAE 2.0.
- A soma dos vínculos das cadeias produtivas deve ser igual ao total de vínculos ativos do município.
- A fonte dos dados deve estar indicada em todas as páginas, e o painel deve continuar acessível publicamente, sem necessidade de login.
- **Métricas coletadas:** vínculos ativos e estabelecimentos por setor e por cadeia produtiva, participação de cada setor no emprego formal, média de vínculos por estabelecimento e participação acumulada das atividades que mais empregam.

---

## Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions e usuários externos à equipe.
- **Feedback qualitativo (positivo/negativo):** Os apontamentos do cliente (CADI e Secretaria de Inovação e Desenvolvimento Econômico) na apresentação da Sprint 2 foram implementados nesta sprint, entre eles os indicadores-resumo na página inicial, a ordenação da tabela de atividades e das faixas de porte da empresa e o agrupamento dos CEPs por zona e bairro. O retorno dos usuários externos sobre a versão da Sprint 3 ainda não foi recebido.
- **Consistência dos dados:** Os totais do painel conferem com a base de origem: 204.684 vínculos ativos, 204.593 CLT e 91 estatutários. A soma dos vínculos das cadeias produtivas confere com o total do município.
- **Resultados apresentados pelo painel:**
    - Serviços concentram 51% dos vínculos ativos, seguidos pelo comércio (22%), pela indústria (21%) e pela construção civil (5%).
    - A fabricação de aeronaves é a atividade de maior peso, com 11.069 vínculos.
    - A indústria tem a maior média de vínculos por estabelecimento: cerca de 35 vínculos (42.159 vínculos em 1.198 estabelecimentos), contra cerca de 15 nos serviços e 9 no comércio.
    - As dez atividades que mais empregam somam 51.112 vínculos, cerca de 25% do total do município. Depois da fabricação de aeronaves, aparecem atendimento hospitalar (8.299), supermercados (5.338), teleatendimento (4.395), serviços combinados de apoio a edifícios (4.099) e restaurantes (4.004). A fabricação de automóveis, camionetas e utilitários fica em 10º lugar, com 3.415 vínculos.
    - **Impacto dos principais setores, conforme os vínculos ativos:**
        - **Serviços:** 104.843 vínculos (51%) em 6.843 estabelecimentos, com 90 dos 91 vínculos estatutários do município. As atividades que mais empregam são atendimento hospitalar (8.299), teleatendimento (4.395), serviços combinados de apoio a edifícios (4.099), restaurantes (4.004) e serviços de engenharia (3.628).
        - **Comércio:** 45.491 vínculos (22%) em 5.240 estabelecimentos, todos CLT. O emprego se concentra em empresas de menor porte e no varejo: supermercados (5.338), vestuário e acessórios (2.091), hipermercados (1.783) e produtos farmacêuticos (1.674).
        - **Indústria:** 42.159 vínculos (21%) em 1.198 estabelecimentos. É o setor mais concentrado em grandes empresas, com a maior parte dos vínculos na faixa de 1.000 ou mais empregados. A fabricação de aeronaves (11.069) responde sozinha por cerca de 26% dos vínculos industriais, seguida pela fabricação de automóveis, camionetas e utilitários (3.415), de materiais para medicina e odontologia (2.060) e de cosméticos e produtos de higiene pessoal (1.769).

### Macroprocessos produtivos

As 19 atividades (subclasse CNAE 2.0) com mais de 2.000 vínculos ativos cada foram associadas aos macroprocessos produtivos aos quais pertencem:

| Macroprocesso produtivo | Atividades (CNAE 2.0) e vínculos ativos | Total de vínculos |
|-------------------------|------------------------------------------|------------------:|
| Serviços de apoio às empresas | Teleatendimento (4.395); serviços combinados para apoio a edifícios (4.099); serviços combinados de escritório e apoio administrativo (3.450); limpeza (3.415); vigilância e segurança privada (2.175); seleção e agenciamento de mão de obra (2.123) | 19.657 |
| Aeroespacial e defesa | Fabricação de aeronaves (11.069) | 11.069 |
| Saúde | Atendimento hospitalar (8.299); fabricação de materiais para medicina e odontologia (2.060) | 10.359 |
| Varejo e abastecimento | Supermercados (5.338); vestuário e acessórios (2.091) | 7.429 |
| Alimentação | Restaurantes (4.004); lanchonetes (2.857) | 6.861 |
| Educação | Educação infantil – creche (2.334); ensino fundamental (2.012) | 4.346 |
| Engenharia e serviços técnicos | Serviços de engenharia (3.628) | 3.628 |
| Automotiva | Fabricação de automóveis, camionetas e utilitários (3.415) | 3.415 |
| Construção civil | Construção de edifícios (2.947) | 2.947 |
| Logística e transporte | Transporte rodoviário de carga (2.536) | 2.536 |
| **Total** | **19 atividades** | **72.247** |

> As 19 atividades somam cerca de 35% dos vínculos ativos do município. As demais atividades, todas com menos de 2.000 vínculos cada, ficam na categoria "Demais atividades".

**Macroprocessos mais pertinentes ao município.** Em volume de vínculos, os serviços de apoio às empresas, o varejo e a alimentação têm grande peso, mas são atividades presentes em qualquer cidade de porte semelhante e atendem à demanda local. Os macroprocessos que distinguem São José dos Campos são:
- **Aeroespacial e defesa:** a fabricação de aeronaves é a atividade que mais emprega em todo o município e responde sozinha por cerca de 26% dos vínculos industriais.
- **Saúde:** reúne o atendimento hospitalar, segunda atividade que mais emprega, e uma indústria de materiais médicos e odontológicos, o que indica um polo de saúde que vai além dos serviços.
- **Automotiva:** a fabricação de automóveis é a segunda atividade industrial em vínculos.
- **Engenharia e serviços técnicos:** os serviços de engenharia estão entre as dez atividades que mais empregam e se relacionam com a base industrial e tecnológica do município.

---

## Próximos Passos

> **Os itens abaixo são possibilidades viáveis de evolução do Observatório, e não metas definidas pela equipe.** A adoção de cada uma depende da avaliação do cliente e da disponibilidade dos dados.

- **Melhorias planejadas após feedback:** Ajustes nos indicadores, nos visuais e na composição das cadeias produtivas conforme a avaliação do cliente na apresentação da Sprint 3.
- **Ajustes de usabilidade:** Revisão final do layout, dos textos de apoio e da navegação para a Feira de Soluções.
- **Expansão de funcionalidades para próximo incremento:** Comparação dos setores do município com o estado de São Paulo e com o Brasil (quociente locacional).
- **Integração de novas bases de dados ao Observatório:** O modelo em estrela construído nas sprints anteriores permite acrescentar novas bases ao painel sem refazer a estrutura existente. Entre as possibilidades:
    - **Perfil demográfico:** dados do Censo e das estimativas populacionais do IBGE por bairro e região, para relacionar o emprego formal à população de cada área da cidade.
    - **Séries temporais:** RAIS de outros anos-base, para comparar a evolução dos setores, das atividades e do porte das empresas ao longo do tempo, além do Novo CAGED (admissões e desligamentos mensais).
    - **Relação de empresas:** dados abertos do CNPJ (Receita Federal), para identificar as empresas por atividade e localização, o que a RAIS pública não permite, e apoiar o mapeamento de parceiros e o selo de cooperação em inovação.

---

## Anexos / Evidências

**Vídeo explicativo:**

https://www.youtube.com/watch?v=1cJukXYvuT8

https://github.com/user-attachments/assets/04d8bdab-3866-4c99-9a2c-cf74f49cc3b2

**Página Início**

<img width="1365" height="767" alt="Página Início" src="https://github.com/user-attachments/assets/9d4c384b-e0e6-4094-9b2e-a111a2dda3ee" />

**Página Indicadores Econômicos**

<img width="1365" height="767" alt="Página Indicadores Econômicos" src="https://github.com/user-attachments/assets/75fe1a2e-d3af-49f2-a13f-a284938285ad" />

**Página Distribuição Geográfica**

<img width="1365" height="767" alt="Página Distribuição Geográfica" src="https://github.com/user-attachments/assets/5afe7264-669f-4e30-be40-542598704c5d" />

- Dashboard publicado (Power BI): [Clique aqui](https://app.powerbi.com/view?r=eyJrIjoiNzRjZTlmMTgtZGE0NC00ZjZmLThiMTMtNjczNTg2MzIyN2Q3IiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9)
- Relatório da Sprint 3: [Clique aqui](https://github.com/user-attachments/files/35537598/Relatorio_Sprint3.pdf)

---

## Registro das Sprints

| Sprint            |  Entrega   | Status   | Histórico |
|-------------------|------------|----------|-----------|
| 01                | 28/09/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp1.md)  |
| 02                | 02/11/2026 | entregue | [MVP](https://github.com/Seven-Soluctions/Observatorio_de_Inovacao/blob/main/MVP/sp2.md)  |
| Feira de Soluções | dd/mm/aaaa | a fazer  | [MVP](#)  |

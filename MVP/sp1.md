# 📌 MVP - Sprint 1: Extração dos Dados da RAIS e Primeira Versão do Painel

## 🎯 Objetivo do MVP
> O propósito deste MVP é extrair da base nacional da RAIS os dados do município de São José dos Campos, organizá-los em Python e apresentar, no Power BI, uma primeira versão do painel do Observatório de Inovação com os setores, os vínculos de emprego formal e a localização dos estabelecimentos.
- **Qual problema resolve?** A ausência de um mapeamento estruturado da estrutura produtiva do município, apontada pelo CADI e pela Secretaria de Inovação e Desenvolvimento Econômico. Os dados da RAIS existem, mas estão em uma base nacional, extensa e em formato técnico, de difícil leitura.
- **Qual hipótese será validada?** Filtrar a RAIS para o município e apresentá-la em um painel com gráficos, mapa e filtros por setor e tamanho do estabelecimento permite ter uma primeira visão de quais setores predominam em São José dos Campos.
- **Qual valor será entregue ao usuário final?** Uma primeira visão de quais setores reúnem mais estabelecimentos e vínculos de emprego formal no município e de onde esses estabelecimentos estão localizados.

---

## 📝 Descrição da Solução
> O que é entregue nesta etapa é o script de extração e filtragem da RAIS e a primeira versão do painel do Observatório, em uma única página.
- **Funcionalidades principais incluídas:**
    - Script em Python, no Google Colab, que lê a RAIS Estabelecimentos 2025 e filtra os registros do município de São José dos Campos (código IBGE 354990).
    - Verificação inicial da qualidade dos dados filtrados.
    - Gráfico **Principais setores econômicos**, com a quantidade de estabelecimentos por subsetor do IBGE.
    - Gráfico **Vínculos ativos**, com o total de vínculos do município distribuído por subsetor do IBGE.
    - Gráfico **Vínculos nos top 10 setores**, com os dez subsetores que mais empregam.
    - **Mapa** dos estabelecimentos por CEP.
    - Cartão com o **total de vínculos**.
    - Filtros por subsetor do IBGE (com abertura por classe da CNAE 95) e por tamanho do estabelecimento.
    - Repositório no GitHub com o backlog do produto e a documentação do projeto.
- **Limitações conhecidas:**
  - A base filtrada ainda tinha registros duplicados, colunas sem informação e códigos sem descrição, como as faixas de tamanho do estabelecimento, que aparecem apenas como números de 1 a 10. Por isso, os totais desta versão (cerca de 207 mil vínculos) ficam um pouco acima da base corrigida na Sprint 2 (204.684 vínculos).
  - As atividades foram apresentadas pela CNAE 95, classificação anterior à CNAE 2.0.
  - O painel tem uma única página, sem página inicial de apresentação e sem botões de navegação.
  - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social), e a localização é aproximada pelo CEP.
- **Escopo reduzido (somente o essencial para validar a ideia):**
 Extração e filtragem da RAIS para o município e um painel de uma página com estabelecimentos e vínculos por subsetor, mapa por CEP e filtros por subsetor e tamanho do estabelecimento.

---

## 👥 Personas / Usuários-Alvo
- **Gestor Público:** Servidor da Secretaria de Desenvolvimento Econômico/CADI que planeja políticas de fomento industrial e de inovação. Dor atendida: falta de uma visão organizada dos setores predominantes no município.
- **Empresa Parceira:** Empresa já estabelecida no ecossistema de inovação de SJC. Dor atendida: dificuldade de localizar os estabelecimentos do seu setor no município.
- **Parceiro em Potencial:** Empresa ou investidor externo que avalia se instalar na região. Dor atendida: falta de informação reunida sobre o peso de cada setor na economia local.
- **Cidadão (pesquisadores, estudantes e jornalistas):** Usuário que busca informação pública sobre a economia do município. Dor atendida: dados da RAIS dispersos e em formato técnico, de difícil leitura.

---

## 🔑 User Stories (Backlog do MVP)
| ID  | User Story | Prioridade | Estimativa |
|-----|------------|------------|------------|
| US1 | Como cidadão, quero acessar o Observatório publicamente e sem necessidade de login, para exercer meu direito de acesso à informação sobre a economia do município (Lei de Acesso à Informação). | Alta | 3 pontos |
| US2 | Como usuário do Observatório, quero navegar por uma página inicial de apresentação, com indicação dos pontos tratados na análise de São José dos Campos, para ter uma visão geral rápida antes de aprofundar a análise. | Alta | 5 pontos |
| US3 | Como equipe de desenvolvimento, quero automatizar a extração dos dados da base RAIS nacional e filtrar apenas os registros do município de São José dos Campos, para garantir uma base de dados confiável e atualizável. | Alta | 13 pontos |
| US4 | Como equipe de desenvolvimento, quero versionar os scripts de tratamento de dados e a documentação do projeto no GitHub, para garantir rastreabilidade, colaboração e transparência do processo. | Alta | 2 pontos |
| US5 | Como gestor público, quero visualizar um mapa dos setores industriais e de serviços predominantes na região, para identificar oportunidades de fomento e atração de investimentos. | Alta | 8 pontos |
| US6 | Como membro do ecossistema de inovação, quero utilizar filtros por setor econômico e porte da empresa, para localizar rapidamente a informação relevante para minha análise. | Alta | 5 pontos |

> A publicação com acesso público (US1) e a página inicial de apresentação (US2) foram concluídas na Sprint 2, junto com o novo layout do painel.

---

## 📅 Sprint(s) Relacionadas
| Sprint | Entregas Principais | Status |
|--------|---------------------|--------|
| 01 | Extração e filtragem da RAIS para o município em Python (Google Colab), verificação da qualidade dos dados, backlog do produto e primeira versão do painel. | Concluída |
| 02 | Filtragem refeita, modelo de dados em estrela com relacionamentos entre as tabelas, novo layout do painel com três páginas e publicação com acesso público. | Planejada |
| 03 | Análise dos macroprocessos produtivos, indicadores-resumo na página inicial e comparação entre setores. | Planejada |

---

## 📊 Critérios de Aceitação
- O script deve filtrar apenas os registros do município de São José dos Campos (código IBGE 354990).
- O painel deve apresentar a quantidade de estabelecimentos e os vínculos ativos por subsetor do IBGE.
- O painel deve apresentar a distribuição geográfica dos estabelecimentos em um mapa.
- Deve ser possível filtrar a visualização por subsetor do IBGE e por tamanho do estabelecimento.
- O script e a documentação devem estar versionados no GitHub.
- **Métricas coletadas:** total de vínculos ativos, estabelecimentos por subsetor e vínculos por subsetor.

---

## 📈 Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions. A validação com o cliente (CADI e Secretaria de Inovação e Desenvolvimento Econômico) ocorreu na apresentação da Sprint 1.
- **Feedback qualitativo (positivo/negativo):** A verificação da base mostrou registros duplicados, colunas sem informação e códigos sem descrição, o que levou a refazer a filtragem e a modelagem dos dados na Sprint 2.
- **Resultados apresentados pelo painel:**
  - Cerca de 207 mil vínculos ativos no município.
  - Comércio e administração de imóveis e valores mobiliários é o subsetor com mais estabelecimentos (15,2 mil, 34% do total), seguido pelo comércio varejista (10,3 mil, 23%) e pelos serviços de alojamento e alimentação (5 mil, 11%).
  - Os subsetores que mais empregam são comércio e administração de imóveis e valores mobiliários (cerca de 39 mil vínculos) e comércio varejista (cerca de 38 mil), seguidos por serviços de alojamento e alimentação (22 mil) e serviços médicos, odontológicos e veterinários (17 mil).

---

## 🚀 Próximos Passos
- **Melhorias planejadas após feedback:** Refazer a filtragem da RAIS, eliminando duplicidades e colunas sem informação, e incluir as descrições dos códigos.
- **Ajustes de usabilidade:** Criar uma página inicial de apresentação, dividir o painel em páginas temáticas com botões de navegação e substituir os códigos de tamanho do estabelecimento por faixas descritas.
- **Expansão de funcionalidades para próximo incremento:** Modelo de dados em estrela com relacionamentos entre as tabelas, classificação das atividades pela CNAE 2.0, agrupamento dos subsetores em Agropecuária, Indústria, Construção, Comércio e Serviços e publicação do painel com acesso público.

---

## 📂 Anexos / Evidências

**Vídeo explicativo:**

https://github.com/user-attachments/assets/16512ea3-3a93-4f64-bce4-770e60a05f72

**Painel da Sprint 1**

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/2cc0f39a-3e2e-41b8-aa45-510b181e1ab4" />

- Plataforma BI: https://app.powerbi.com/view?r=eyJrIjoiMzM1ZjFmYzYtMjhiNC00Zjk2LTg0OWItY2ExYjE2NDliMDI1IiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9&pageName=b0eda75f0b95818c30e0
- Relatório da Sprint 1: [PREENCHER: link do relatório]






# 📌 MVP - Sprint 2: Modelagem dos Dados e Painel de Indicadores do Observatório

## 🎯 Objetivo do MVP
> O propósito deste MVP é refazer a filtragem dos dados da RAIS, construir os relacionamentos entre as tabelas e apresentar, no Power BI, um painel público e navegável com os indicadores de emprego formal de São José dos Campos por setor, porte, atividade e localização.
- **Qual problema resolve?** A ausência de um mapeamento estruturado da estrutura produtiva do município, apontada pelo CADI e pela Secretaria de Inovação e Desenvolvimento Econômico, e a base de dados da Sprint 1, que ainda tinha duplicidades, colunas sem informação e códigos sem descrição.
- **Qual hipótese será validada?** Organizar a RAIS em um modelo de dados relacional e apresentá-la em um painel com filtros por setor, porte e atividade permite identificar os setores predominantes do município e apoiar decisões da gestão pública.
- **Qual valor será entregue ao usuário final?** Uma visão clara e de acesso público sobre quais setores e atividades mais empregam em São José dos Campos, qual o porte dos estabelecimentos e onde eles estão localizados.

---

## 📝 Descrição da Solução
> O que é entregue nesta etapa é a base de dados tratada e modelada e o painel do Observatório de Inovação, com três páginas publicadas na web.
- **Funcionalidades principais incluídas:**
    - Base da RAIS Estabelecimentos 2025 filtrada para o município (código IBGE 354990), com 42.362 estabelecimentos e 204.684 vínculos ativos.
    - Modelo em estrela com uma tabela fato e cinco tabelas dimensão (atividade, porte, Simples Nacional, natureza jurídica e localidade), ligadas por relacionamentos 1:*.
    - Classificação dos setores em Agropecuária, Indústria, Construção, Comércio e Serviços, a partir do subsetor do IBGE.
    - Página **Início**, com o objetivo do Observatório e a navegação.
    - Página **Indicadores Econômicos**, com vínculos ativos, CLT e estatutários e os vínculos por setor, porte e atividade (CNAE 2.0), além da participação das optantes pelo Simples Nacional.
    - Página **Distribuição Geográfica**, com mapa dos vínculos ativos por CEP, vínculos por atividade e vínculos e estabelecimentos por subsetor do IBGE.
    - Filtros por porte, subsetor IBGE e subclasse CNAE 2.0, e botões de navegação entre as páginas.
- **Limitações conhecidas:**
  - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social).
  - A base mede o estoque de emprego em 31/12. Ela não informa admissões e desligamentos nem mede inovação ou investimento em P&D.
  - A localização é aproximada pelo CEP, e a base cobre apenas o município de São José dos Campos.
- **Escopo reduzido (somente o essencial para validar a ideia):**
 Base tratada e modelada e painel com indicadores de vínculos ativos por setor, porte, atividade e localização, publicado com acesso público.

---

## 👥 Personas / Usuários-Alvo
- **Gestor Público:** Servidor da Secretaria de Desenvolvimento Econômico/CADI que planeja políticas de fomento industrial e de inovação. Dor atendida: falta de uma visão organizada dos setores que mais empregam no município.
- **Empresa Parceira:** Empresa já estabelecida no ecossistema de inovação de SJC. Dor atendida: dificuldade de identificar os ramos do seu setor presentes no município e onde eles se concentram.
- **Parceiro em Potencial:** Empresa ou investidor externo que avalia se instalar na região. Dor atendida: falta de indicadores para comparar o peso dos setores.
- **Cidadão (pesquisadores, estudantes e jornalistas):** Usuário que busca informação pública sobre a economia do município. Dor atendida: dados da RAIS dispersos e em formato técnico, de difícil leitura.

---

## 🔑 User Stories (Backlog do MVP)
| ID  | User Story | Prioridade | Estimativa |
|-----|------------|------------|------------|
| US7  | Como gestor público, quero visualizar indicadores de vínculo por setor, para compreender a dinâmica do mercado de trabalho local e orientar políticas públicas. | Alta | 5 pontos |
| US9  | Como gestor público, quero visualizar, no mesmo painel, indicadores relacionados aos setores econômicos e de serviços, para embasar políticas de fomento ao diálogo entre esses atores. | Alta | 8 pontos |
| US10 | Como empresa parceira, quero identificar outros ramos do mesmo setor produtivo presentes na região, para mapear possíveis sinergias, fornecedores ou parcerias estratégicas. | Alta | 8 pontos |
| US11 | Como empresa parceira, quero visualizar a distribuição geográfica das empresas por setor no município, para identificar clusters produtivos próximos ao meu negócio. | Alta | 8 pontos |

---

## 📅 Sprint(s) Relacionadas
| Sprint | Entregas Principais | Status |
|--------|---------------------|--------|
| 01 | Extração e filtragem da RAIS para o município em Python (Google Colab), verificação da qualidade dos dados, backlog do produto e primeira versão do painel. | Concluída |
| 02 | Filtragem refeita, modelo de dados em estrela com relacionamentos entre as tabelas, novo layout do painel com três páginas e publicação com acesso público. | Concluída |
| 03 | Análise dos macroprocessos produtivos, indicadores-resumo na página inicial e comparação entre setores. | Planejada |

---

## 📊 Critérios de Aceitação
- A base tratada deve conferir com o arquivo de origem: 42.362 estabelecimentos e 204.684 vínculos ativos.
- As tabelas dimensão devem se relacionar com a tabela fato em relacionamentos 1:*, sem registros sem correspondência.
- O painel deve apresentar os vínculos ativos por setor, porte, atividade e localização.
- Deve ser possível filtrar a visualização por porte, subsetor IBGE e subclasse CNAE 2.0.
- A navegação entre as páginas deve ser fluida e intuitiva.
- A fonte dos dados deve estar indicada em todas as páginas.
- O painel deve ser acessível publicamente, sem necessidade de login.
- **Métricas coletadas:** total de vínculos ativos, estabelecimentos com vínculos, participação de cada setor no emprego formal e participação das optantes pelo Simples Nacional.

---

## 📈 Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions. A validação com o cliente (CADI e Secretaria de Inovação e Desenvolvimento Econômico) ocorre na apresentação da Sprint 2.
- **Feedback qualitativo (positivo/negativo):** Avaliação do cliente sobre a clareza dos indicadores e a facilidade de navegação, a ser registrada após a apresentação da Sprint 2.
- **Consistência dos dados:** Os totais do painel conferem com a base de origem: 204.684 vínculos ativos, 204.593 CLT e 91 estatutários.
- **Resultados apresentados pelo painel:**
  - Serviços concentram 51% dos vínculos ativos, seguidos pelo comércio (22%), pela indústria (21%) e pela construção civil (5%).
  - A fabricação de aeronaves é a atividade de maior peso, com 11.069 vínculos.
  - 63% dos 14.380 estabelecimentos com vínculos são optantes pelo Simples Nacional.

---

## 🚀 Próximos Passos
- **Melhorias planejadas após feedback:** Ajustes nos indicadores e nos visuais conforme a avaliação do cliente na apresentação da Sprint 2.
- **Ajustes de usabilidade:** Indicadores-resumo na página inicial, ordenação da tabela de atividades e das faixas de porte, e agrupamento dos CEPs por região da cidade no mapa.
- **Expansão de funcionalidades para próximo incremento:** Análise dos macroprocessos produtivos, comparação entre setores e avaliação de fontes complementares, como o Novo CAGED (admissões e desligamentos) e os dados abertos de CNPJ (identificação das empresas).

---

## 📂 Anexos / Evidências

**Vídeo explicativo:**

LINK_DO_VIDEO

**Página Início**

<img width="1912" height="1064" alt="Captura de tela 2026-11-02 203924" src="https://github.com/user-attachments/assets/c876431d-2e3e-4c13-b530-d96e7028f3d6" />

**Página Indicadores Econômicos**

<img width="1910" height="1057" alt="Captura de tela 2026-11-02 203940" src="https://github.com/user-attachments/assets/2b27e5f8-f231-47cb-beda-349d06bee3ee" />

**Página Distribuição Geográfica**

<img width="1917" height="1078" alt="Captura de tela 2026-11-02 203955" src="https://github.com/user-attachments/assets/90e64b2e-6310-48f5-9266-72be116d0c3a" />


- Plataforma BI: https://app.powerbi.com/view?r=eyJrIjoiNmMyNDNmMzUtMjk5Yi00ZTM1LTlmY2EtNDlhYzgxZmQzYzhjIiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9
- Relatório da Sprint 2: [TRABALHO_API_final.docx](https://github.com/user-attachments/files/34300490/TRABALHO_API_final.docx)

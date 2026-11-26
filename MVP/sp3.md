# 📌 MVP - Sprint 3: Cadeias Produtivas, Classificação CNAE e Comparação entre Setores

> ⚠️ **Rascunho para revisão da equipe.** Trechos marcados com `[PREENCHER]` dependem do painel da Sprint 3 (números, prints, vídeo e link). Apague esta nota antes de publicar.

## 🎯 Objetivo do MVP
> O propósito deste MVP é ampliar o painel do Observatório de Inovação com a análise dos macroprocessos produtivos de São José dos Campos, a classificação das atividades segundo a hierarquia da CNAE 2.0 e a comparação de indicadores entre setores, além de trazer os principais números do município para a página inicial.
- **Qual problema resolve?** O painel da Sprint 2 mostrava os vínculos por setor, porte e atividade, mas não permitia comparar os setores lado a lado, não agrupava as atividades em cadeias produtivas e exigia que o usuário navegasse até a segunda página para ver os principais números do município.
- **Qual hipótese será validada?** Agrupar as atividades da RAIS em cadeias produtivas e apresentar os setores em visuais comparativos permite que gestores, empresas e investidores identifiquem quais setores concentram o emprego formal e onde estão as oportunidades de parceria e investimento.
- **Qual valor será entregue ao usuário final?** Uma leitura rápida da economia do município já na página inicial, a comparação direta entre setores e a visão das cadeias produtivas e de suas atividades, organizadas segundo a CNAE.

---

## 📝 Descrição da Solução
> O que é entregue nesta etapa é a nova versão do painel do Observatório, com indicadores-resumo na página inicial e duas novas páginas: Comparação entre Setores e Cadeias Produtivas.
- **Funcionalidades principais incluídas:**
    - Página **Início** com indicadores-resumo em destaque: 204.684 vínculos ativos, 42.362 estabelecimentos, 14.380 estabelecimentos com vínculos, setor predominante (Serviços, 51% dos vínculos) e atividade de maior peso (fabricação de aeronaves, 11.069 vínculos).
    - Nova página **Comparação entre Setores**, com vínculos ativos, estabelecimentos, participação no emprego formal e média de vínculos por estabelecimento para Agropecuária, Indústria, Construção, Comércio e Serviços, lado a lado.
    - Ranking das atividades (subclasse CNAE 2.0) que mais geram empregos formais, com a participação acumulada de cada uma no total de vínculos.
    - Hierarquia da CNAE 2.0 (seção, divisão, grupo, classe e subclasse) na tabela dimensão de atividade, com navegação por níveis (*drill down*) nos visuais.
    - Nova página **Cadeias Produtivas**, que agrupa as atividades nos macroprocessos produtivos relevantes para o município `[PREENCHER: confirmar a lista usada no painel, por exemplo aeroespacial e defesa, automotiva, química e petroquímica, saúde, tecnologia da informação e logística]`, com vínculos, estabelecimentos e atividades de cada cadeia.
    - Filtro por cadeia produtiva, somado aos filtros de porte, subsetor IBGE e subclasse CNAE 2.0 da Sprint 2.
    - Ajustes de usabilidade apontados na Sprint 2: ordenação da tabela de atividades e das faixas de porte `[PREENCHER: e agrupamento dos CEPs por região da cidade no mapa, se foi feito]`.
- **Limitações conhecidas:**
  - A RAIS pública não identifica as empresas (não traz CNPJ nem razão social), por isso as cadeias produtivas são montadas a partir das atividades (CNAE) e não das empresas.
  - Uma mesma atividade pode servir a mais de uma cadeia. No painel, cada atividade foi associada a uma única cadeia, a de maior aderência.
  - A base mede o estoque de emprego em 31/12. Ela não informa admissões, desligamentos, remuneração nem investimento em P&D.
  - A comparação é feita apenas dentro do município. Ainda não há comparação com o estado ou com o país.
- **Escopo reduzido (somente o essencial para validar a ideia):**
 Indicadores-resumo na página inicial, comparação entre os cinco setores, ranking das atividades que mais empregam, hierarquia CNAE e agrupamento das atividades em cadeias produtivas.

---

## 👥 Personas / Usuários-Alvo
- **Gestor Público:** Servidor da Secretaria de Desenvolvimento Econômico/CADI que planeja políticas de fomento industrial e de inovação. Dor atendida: falta de uma visão das cadeias produtivas do município para orientar as políticas de fomento.
- **Empresa Parceira:** Empresa já estabelecida no ecossistema de inovação de SJC. Dor atendida: dificuldade de saber quais setores e atividades concentram o emprego e quais ramos compõem a sua cadeia produtiva.
- **Parceiro em Potencial:** Empresa ou investidor externo que avalia se instalar na região. Dor atendida: falta de indicadores comparáveis entre setores para embasar a decisão de investimento.
- **Cidadão (pesquisadores, estudantes e jornalistas):** Usuário que busca informação pública sobre a economia do município. Dor atendida: dificuldade de relacionar os dados da RAIS a uma classificação reconhecida, como a CNAE.

---

## 🔑 User Stories (Backlog do MVP)
| ID  | User Story | Prioridade | Estimativa |
|-----|------------|------------|------------|
| US11 | Como parceiro em potencial, quero comparar indicadores econômicos entre diferentes setores da região, para apoiar minha decisão sobre onde investir ou instalar uma nova operação. | Média | 5 pontos |
| US12 | Como pesquisador, quero visualizar a classificação das atividades econômicas segundo a CNAE, para relacionar os dados da RAIS a categorias produtivas reconhecidas academicamente. | Média | 5 pontos |
| US13 | Como empresa parceira, quero visualizar quais setores concentram a maior geração de empregos formais, para identificar players relevantes para possíveis parcerias. | Média | 3 pontos |

---

## 📅 Sprint(s) Relacionadas
| Sprint | Entregas Principais | Status |
|--------|---------------------|--------|
| 01 | Extração e filtragem da RAIS para o município em Python (Google Colab), verificação da qualidade dos dados, backlog do produto e primeira versão do painel. | Concluída |
| 02 | Filtragem refeita, modelo de dados em estrela com relacionamentos entre as tabelas, novo layout do painel com três páginas e publicação com acesso público. | Concluída |
| 03 | Indicadores-resumo na página inicial, comparação entre setores, ranking das atividades que mais empregam, hierarquia CNAE e cadeias produtivas. | Concluída |
| Feira de Soluções | Apresentação final do Observatório ao cliente e à comunidade. | Planejada |

---

## 📊 Critérios de Aceitação
- Os indicadores-resumo da página inicial devem conferir com a base de origem: 42.362 estabelecimentos e 204.684 vínculos ativos.
- O painel deve permitir comparar, lado a lado, os vínculos ativos, os estabelecimentos e a participação no emprego formal dos cinco setores.
- O painel deve apresentar o ranking das atividades que mais geram empregos formais.
- A tabela dimensão de atividade deve conter os cinco níveis da CNAE 2.0, e os visuais devem permitir navegar entre eles.
- Toda atividade da base deve estar associada a uma cadeia produtiva ou à categoria "Demais atividades", sem registros sem correspondência.
- Deve ser possível filtrar a visualização por cadeia produtiva, porte, subsetor IBGE e subclasse CNAE 2.0.
- A soma dos vínculos das cadeias produtivas deve ser igual ao total de vínculos ativos do município.
- A fonte dos dados deve estar indicada em todas as páginas, e o painel deve continuar acessível publicamente, sem necessidade de login.
- **Métricas coletadas:** vínculos ativos e estabelecimentos por setor e por cadeia produtiva, participação de cada setor no emprego formal, média de vínculos por estabelecimento e participação acumulada das atividades que mais empregam.

---

## 📈 Métricas de Validação
- **Número de usuários que testaram o MVP:** Os oito integrantes da equipe Seven Solutions `[PREENCHER: e outros usuários, se houve teste com colegas ou com o cliente]`.
- **Feedback qualitativo (positivo/negativo):** `[PREENCHER: retorno do CADI e da Secretaria na apresentação da Sprint 2 e o que foi ajustado a partir dele]`.
- **Consistência dos dados:** Os totais do painel conferem com a base de origem: 204.684 vínculos ativos, 204.593 CLT e 91 estatutários. A soma dos vínculos das cadeias produtivas confere com o total do município.
- **Resultados apresentados pelo painel:**
  - Serviços concentram 51% dos vínculos ativos, seguidos pelo comércio (22%), pela indústria (21%) e pela construção civil (5%).
  - A fabricação de aeronaves é a atividade de maior peso, com 11.069 vínculos.
  - `[PREENCHER: média de vínculos por estabelecimento do setor com maior média, por exemplo a indústria]`.
  - `[PREENCHER: quantas atividades somam metade dos vínculos do município, a partir do ranking]`.
  - `[PREENCHER: vínculos e participação da principal cadeia produtiva, por exemplo aeroespacial e defesa]`.

---

## 🚀 Próximos Passos
- **Melhorias planejadas após feedback:** Ajustes nos indicadores, nos visuais e na composição das cadeias produtivas conforme a avaliação do cliente na apresentação da Sprint 3.
- **Ajustes de usabilidade:** Revisão final do layout, dos textos de apoio e da navegação para a Feira de Soluções.
- **Expansão de funcionalidades para próximo incremento:** Comparação dos setores do município com o estado de São Paulo e com o Brasil (quociente locacional), uso do Novo CAGED (admissões e desligamentos) e dos dados abertos de CNPJ (identificação das empresas e selo de cooperação em inovação).

---

## 📂 Anexos / Evidências

**Vídeo explicativo:**

https://github.com/user-attachments/assets/04d8bdab-3866-4c99-9a2c-cf74f49cc3b2

**Página Início**

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/9d4c384b-e0e6-4094-9b2e-a111a2dda3ee" />

**Página Indicadores Econômicos**

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/75fe1a2e-d3af-49f2-a13f-a284938285ad" />

**Página Distribuição Geográfica**

<img width="1365" height="767" alt="image" src="https://github.com/user-attachments/assets/5afe7264-669f-4e30-be40-542598704c5d" />

- Plataforma BI: https://app.powerbi.com/view?r=eyJrIjoiNzRjZTlmMTgtZGE0NC00ZjZmLThiMTMtNjczNTg2MzIyN2Q3IiwidCI6ImVhYmU2NGM1LTY4ZjUtNGE3Ni04MzAxLTk1NzdhNjc5ZTQ0OSIsImMiOjR9
- Relatório da Sprint 3: `[PREENCHER: link do relatório]`

# TGI Engov

# DOCUMENTAÇÃO

- **Informações Gerais**
    - **Título do Dataset:** tgi_simulado_engov.xlsx
    - **Criador:** Gerado com IA.
    - **Fonte:** Dados sintéticos simulando pesquisa TGI gerados por IA.

- **Título e Objetivo da Análise: Análise Exploratória e Clusterização do Público da Marca Engov**
    - O objetivo deste projeto foi segmentar o público da marca Engov em grupos homogêneos (clusters), utilizando Análise Exploratória de Dados (AED) e técnicas de clusterização, para permitir a criação de estratégias de marketing mais direcionadas.

- **Dicionário de Variáveis (Colunas)**

| Variável | Tipo de Dado | Descrição |
| --- | --- | --- |
| `Respondent_ID` | Numérico | Identificador único de cada respondente. |
| `Sexo` | Categórico | Gênero do respondente (M: Masculino, F: Feminino). |
| `Idade` | Numérico | Idade do respondente em anos. |
| `Classe` | Categórico | Classe socioeconômica do respondente (ex: A, B, C, D). |
| `Regiao` | Categórico | Região de residência do respondente (ex: PR, BA, RJ, SP). |
| `Consome_Engov` | Categórico | Indica se o respondente consome o produto Engov (Sim, Não). |
| `Frequencia_Alcool` | Categórico | Frequência com que o respondente consome bebidas alcoólicas (ex: Média, Baixa, Alta). |
| `Sai_para_Balada` | Categórico | Frequência com que o respondente sai para baladas (ex: Nunca, 1x/semana). |
| `Midia_Preferida` | Categórico | Meio de comunicação preferido do respondente (ex: YouTube, Instagram, Rádio FM). |
| `Indice_Afinidade` | Numérico | Um índice fictício que mede a afinidade do respondente com a marca. |
| `Peso_Projecao` | Numérico | Peso da amostra para projeção populacional. |
- Requirements:
    - **pandas**
    - **numpy**
    - **matplotlib**
    - **seaborn**
    - **scikit-learn**
    - **openpyxl**

---

# **1. Análise Exploratória de Dados (AED)**

## Distribuição da base de amostra por sexo.

![01-distribuição-sexo.png](01-distribuio-sexo.png)

## Distribuição da base de amostra por classes sociais.

![02-distribuição-classes.png](02-distribuio-classes.png)

## Distribuição por região

![03-distribuição-regiões.png](03-distribuio-regies.png)

| Regiao | Contagem | Porcentagem (%) |
| --- | --- | --- |
| PR | 35 | 17.5 |
| RJ | 34 | 17.0 |
| MG | 30 | 15.0 |
| BA | 27 | 13.5 |
| SP | 26 | 13.0 |
| RS | 26 | 13.0 |
| PE | 22 | 11.0 |

## Distribuição de consumo de Engov

![04-distribuição-consome-engov.png](04-distribuio-consome-engov.png)

| Consome_Engov | Contagem | Porcentagem (%) |
| --- | --- | --- |
| Sim | 123 | 61.5 |
| Não | 77 | 38.5 |

## Distribuição de frequência de consumo de Alcool

![05-distribuição-frequencia-alcool.png](05-distribuio-frequencia-alcool.png)

| Frequencia_Alcool | Contagem | Porcentagem (%) |
| --- | --- | --- |
| Média | 74 | 37.0 |
| Alta | 68 | 34.0 |
| Baixa | 58 | 29.0 |

## Distribuição de público que sai de balada

![06-distribuição-sai-balada.png](06-distribuio-sai-balada.png)

| Sai_para_Balada | Contagem | Porcentagem (%) |
| --- | --- | --- |
| 1x/semana | 66 | 33.0 |
| 1x/mês | 45 | 22.5 |
| 2x/semana | 40 | 20.0 |
| Nunca | 35 | 17.5 |
| 3x/semana | 14 | 7.0 |

## Distribuição de mídia preferida

![07-distribuição-midia-preferida.png](07-distribuio-midia-preferida.png)

| Midia_Preferida | Contagem | Porcentagem (%) |
| --- | --- | --- |
| TV Aberta | 38 | 19.0 |
| TikTok | 36 | 18.0 |
| Spotify | 33 | 16.5 |
| YouTube | 28 | 14.0 |
| Instagram | 26 | 13.0 |
| Revistas | 22 | 11.0 |
| Rádio FM | 17 | 8.5 |

## Histograma de idade

![08-histograma-de-idade.png](08-histograma-de-idade.png)

## Histograma de afinidade

![09-histograma-indice-afinidade.png](09-histograma-indice-afinidade.png)

## Histograma de peso e projeção

![10-histograma-peso-projeção.png](10-histograma-peso-projeo.png)

# 2. Cruzamentos e Aprofundamento

## Perfil de Consumidor vs. Não-Consumidor por Mídia

Para explorar este insight, vamos cruzar a variável `Consome_Engov` com a `Midia_Preferida`. O objetivo é descobrir se existe uma diferença no consumo de mídia entre quem usa o produto e quem não usa.

![download.png](download.png)

| Mídia Preferida | Não Consome Engov (%) | Sim, Consome Engov (%) |
| --- | --- | --- |
| **Spotify** | 19.48 | 14.63 |
| **TikTok** | 19.48 | 17.07 |
| **YouTube** | 18.18 | 11.38 |
| **TV Aberta** | 12.99 | 22.76 |
| **Instagram** | 10.39 | 14.63 |
| **Revistas** | 12.99 | 9.76 |
| **Rádio FM** | 6.49 | 9.76 |

**1. Oportunidade no Spotify, TikTok e YouTube (Não-Consumidores)**

- **O que os dados mostram:** O grupo que **não consome** Engov tem uma preferência notavelmente maior por **Spotify** (19.48%), **TikTok** (19.48%) e **YouTube** (18.18%) em comparação com os consumidores.
- **Insight:** Isso sugere que as plataformas de streaming e redes sociais de vídeo podem ser o "terreno fértil" para a marca atrair novos clientes. Campanhas de marketing direcionadas para esses canais, com mensagens que abordem as razões pelas quais o público-alvo ainda não compra, podem ser muito eficazes.

**2. A Força da TV Aberta e Rádio FM (Consumidores)**

- **O que os dados mostram:** O público que **consome** Engov demonstra uma preferência significativamente maior por **TV Aberta** (22.76%) e **Rádio FM** (9.76%).
- **Insight:** Isso valida a importância das mídias tradicionais para a **fidelização** da base de clientes existente. Para manter o relacionamento com os consumidores fiéis, a marca deve continuar investindo nessas plataformas, que são onde eles passam mais tempo.

**3. Mídias Equilibradas: Instagram e Revistas**

- **O que os dados mostram:** A preferência por **Instagram** e **Revistas** é relativamente equilibrada entre os dois grupos.
- **Insight:** Isso sugere que essas plataformas podem ser usadas para campanhas que servem a ambos os propósitos: **fidelização** e **aquisição**.

## Onde Estão os Consumidores de Mídia Digital?

Para este insight, vamos explorar o perfil demográfico (idade e classe) dos usuários das mídias digitais mais populares em nosso dataset: **TikTok**, **Spotify**, **YouTube** e **Instagram**. O objetivo é criar uma "persona" para quem usa essas plataformas e descobrir se há um perfil específico.

![12-distribuição-classes-tiktok.png](12-distribuio-classes-tiktok.png)

![13-distribuição-classes-spotify.png](13-distribuio-classes-spotify.png)

![14-distribução-classes-youtube.png](14-distribuo-classes-youtube.png)

![15-distribuição-classes-instagram.png](15-distribuio-classes-instagram.png)

- **Público de Instagram e TikTok:** Os gráficos de **Instagram** e **TikTok** são muito similares. Ambos têm a maior concentração de público na **Classe B** (53.8% e 52.8%, respectivamente) e na **Classe C** (30.8% e 30.6%). A presença da Classe A é a menor. Isso reforça a ideia de que essas plataformas são muito populares entre as classes B e C.
- **Público de YouTube:** O público do **YouTube** tem uma composição um pouco diferente. Embora a **Classe B** ainda seja o maior grupo (50%), a **Classe C** tem uma porcentagem maior (39.3%) em comparação com as outras mídias, enquanto a Classe A tem a menor representação de todas as mídias digitais analisadas (10.7%). Isso sugere que o YouTube pode ser uma plataforma valiosa para atingir um público de classe C.
- **Público de Spotify:** O gráfico do **Spotify** é o que mais se destaca. Nele, a distribuição de classes é mais equilibrada e há uma presença maior da **Classe A** (21.2%) do que nas outras mídias. As Classes B e A têm a mesma representação, com 39.4% cada, o que é um padrão único entre as plataformas digitais.

### **Insights**

A análise nos mostra que não existe um único "público digital". Cada plataforma atrai perfis ligeiramente diferentes:

1. **Instagram e TikTok:** São ideais para campanhas de massa focadas nas classes **B e C**. A comunicação nesses canais deve ser feita de forma que ressoe com esse público.
2. **YouTube:** Embora também seja forte nas Classes B e C, sua maior proporção na **Classe C** o torna um canal estratégico para atingir esse grupo.
3. **Spotify:** Esta é a principal plataforma para alcançar o público da **Classe A**. Se a marca Engov deseja focar em um público de maior poder aquisitivo, o Spotify é um canal promissor.

## **Análise da Mídia Preferida por Classe Social**

![16-midias-preferidas-classe-a.png](16-midias-preferidas-classe-a.png)

![17-Midias-preferida-classe-b.png](17-Midias-preferida-classe-b.png)

![18-Mídia-preferida-classe-c.png](18-Mdia-preferida-classe-c.png)

### **Insights da Análise por Classe Social**

A visualização dos três gráficos juntos nos permite ver um padrão de consumo de mídia muito mais complexo e estratégico.

### **1. O Público da Classe A é Único**

O gráfico da **Classe A** se destaca de todos os outros. A mídia preferida desse grupo não é a TV Aberta ou o TikTok, mas sim o **Spotify** (31%) e **Revistas** (19%). Essa é a prova que precisávamos: o público de maior poder aquisitivo tem hábitos de consumo de mídia distintos e valoriza plataformas que oferecem experiências sem interrupção e conteúdo de nicho. Para a marca Engov, este é um insight crucial para campanhas de fidelização e relacionamento.

### **2. TV Aberta é a Mídia de Massa**

A **TV Aberta** aparece como uma das mídias mais importantes nas classes **B** (22%) e **C** (19%). Isso reforça o papel da TV como o canal de massa ideal para alcançar a maioria da população. Embora o público de Classe A não a consuma tanto, a TV é a plataforma ideal para campanhas de grande alcance, focadas nas classes que compõem a maior parte da amostra.

### **3. O Triunfo do Digital nas Classes B e C**

O público das classes **B e C** tem um alto consumo de mídias digitais, mas com diferenças sutis.

- **Classe B:** Prefere **TV Aberta** e **TikTok**. Isso sugere que a marca pode alcançar esse público com campanhas de massa na TV e, em seguida, engajá-los com conteúdo rápido e relevante no TikTok.
- **Classe C:** Tem um consumo equilibrado de **TikTok, TV Aberta e YouTube**, com 19% para cada um. Essa pluralidade indica que a marca precisa de uma estratégia multicanal para atingir a Classe C, com uma forte presença digital.

### **Conclusão de Análise por classes**

A análise por classe social nos mostra que não há um único canal de comunicação que funcione para todos. A marca Engov precisa de uma estratégia de mídia personalizada: **Spotify e Revistas** para a Classe A, e uma combinação de **TV Aberta e plataformas digitais** (TikTok e YouTube) para as Classes B e C.

## Hábito de Balada e Frequência de Álcool por Consumo de Engov

![19-habito-balada-por-consumo-engov.png](19-habito-balada-por-consumo-engov.png)

### **1. O Consumo de Engov Não Está Restrito Apenas a quem Vai para Baladas**

- **O que os dados mostram:** O grupo que **consome** Engov tem uma porcentagem maior de pessoas que **`Nunca`** vão para baladas (20.33%) do que o grupo de não-consumidores (12.99%).
- **Insight:** Este é o insight mais valioso desta análise. Ele indica que o Engov está sendo consumido por um público que não se associa à vida noturna tradicional. A marca não deve se limitar à comunicação voltada para festas e baladas. O produto tem potencial para ser posicionado para outros cenários, como alívio de mal-estar em geral, sem ser necessariamente relacionado à ressaca de balada.

### **2. Quem Vai para Baladas não é o Único Público**

- **O que os dados mostram:** O grupo que **não consome** Engov tem uma frequência de balada maior do que o grupo que consome. As porcentagens para `1x/semana`, `1x/mês` e `2x/semana` são consistentemente maiores para o grupo "Não".
- **Insight:** Isso nos mostra que os baladeiros assíduos não são, necessariamente, o público mais fiel da marca. Pode haver uma competição maior por esse público, ou eles podem usar outros métodos de alívio. O fato de que há mais consumidores que nunca vão à balada do que não-consumidores sugere que a marca já encontrou um público muito mais amplo.

![20-frequencia-alcool-consumo-engov.png](20-frequencia-alcool-consumo-engov.png)

Este gráfico nos mostra a frequência de consumo de álcool entre os consumidores de Engov e os não-consumidores.

- **Público de Alta Frequência:** O gráfico revela que o grupo que **consome** Engov tem uma porcentagem maior de pessoas com `Alta` frequência de consumo de álcool (35.77%) em comparação com o grupo que `Não` consome (31.17%). Isso reforça a ideia de que o produto tem uma forte ligação com quem bebe muito.
- **Público de Média Frequência:** Por outro lado, o grupo que **não consome** Engov tem a maior porcentagem de pessoas com `Média` frequência de consumo (40.26%) em comparação com o grupo que consome (34.96%).

### **Insights:**

Ao juntar a análise de `Sai_para_Balada` com a de `Frequencia_Alcool`, a história da marca Engov fica muito mais clara.

1. **Engov: Mais que um Produto Pós-Balada**
A análise de `Sai_para_Balada` mostrou que o Engov tem um consumo significativo entre pessoas que `Nunca` vão à balada. Isso nos diz que a marca já ultrapassou a ocasião de consumo tradicional e pode ser vista como uma solução para mal-estar em geral, e não apenas para a ressaca de festas.
2. **A Verdadeira Ligação é com a Bebida, Não com o Local**
O cruzamento com `Frequencia_Alcool` comprova o que a análise de balada sugeriu. O público de `Alta` frequência de álcool é, de fato, mais propenso a consumir Engov. Isso significa que, independentemente do local (balada, bar, casa de amigos), o que importa para o consumo de Engov é a **intensidade da ingestão de álcool**.
3. **Oportunidade de Mercado: Média Frequência de Álcool**
O público com `Média` frequência de consumo de álcool é o maior grupo de não-consumidores de Engov. A marca pode focar em campanhas de aquisição direcionadas a esse grupo, que já tem o hábito de beber, mas que talvez não pense no Engov como uma solução.

## Distribuição de Idade por Afinidade

O objetivo desta análise é entender se a idade tem alguma relação com o nível de afinidade com a marca. No início do projeto, notamos que o histograma de `Indice_Afinidade` era bimodal, com picos em baixa e alta afinidade. Agora, vamos cruzar isso com a idade para ver se a afinidade com a marca muda com o tempo.

![21-distribuição-idade-publico-baixa-afinidade.png](21-distribuio-idade-publico-baixa-afinidade.png)

![22-distribuição-idade-publico-alta-afinidade.png](22-distribuio-idade-publico-alta-afinidade.png)

### **1. A Idade Média não Define a Afinidade**

- **O que os dados mostram:** A **média de idade** do público de **Baixa Afinidade** (39.24 anos) e do público de **Alta Afinidade** (39.14 anos) é praticamente a mesma.
- **Insight:** Isso nos mostra que a idade, por si só, não é o fator que determina se alguém gosta ou não da marca. Pessoas de 40 anos, por exemplo, podem ter afinidade baixa ou alta. O que realmente importa é a **distribuição de idade dentro de cada grupo**.

### **2. A Afinidade tem a Ver com o Estágio de Vida**

- **O que o gráfico mostra:** O histograma de **Baixa Afinidade** tem dois picos claros: um no grupo mais jovem (18-25 anos) e outro no grupo mais velho (55-60 anos). Já o histograma de **Alta Afinidade** é concentrado em um único pico, entre os 30 e 50 anos.
- **Insight:** A afinidade com a marca não é algo que cresce com a idade. A marca tem um **público fiel e concentrado (30-50 anos)**, que é o seu núcleo. Por outro lado, o público mais jovem e o mais velho são menos engajados. A marca tem um desafio de **aquisição** no público mais jovem e de **reconquista ou relevância** no público mais velho.
- 

# 3. Clusterização

Nesta etapa, exploramos as características demográficas e de comportamento dos respondentes. A análise revelou informações importantes:

- **Distribuição Bimodal da Afinidade:** O **`Indice_Afinidade`** mostrou picos em baixa e alta afinidade, indicando a existência de pelo menos dois grupos distintos no público.
- **Consumo de Engov:** 61.5% da amostra consome Engov, e 38.5% não. A análise dos não-consumidores é crucial para estratégias de aquisição.
- **Mídias Preferidas:** Variáveis como **`Midia_Preferida`** revelaram que o público está presente em diferentes canais, como **Spotify** e **TikTok**, além dos tradicionais como **TV Aberta** e **Rádio FM**.

---

### **2. Pré-processamento dos Dados**

Antes de aplicar a clusterização, os dados foram preparados:

- **Codificação:** Variáveis categóricas foram transformadas em numéricas usando **One-Hot Encoding**.
- **Padronização:** Variáveis numéricas foram padronizadas com **StandardScaler** para que tivessem a mesma importância no modelo de clusterização.

---

### **3. Metodologia de Clusterização**

![23-metodo-cotovelo.png](23-metodo-cotovelo.png)

- **Método do Cotovelo:** Utilizou-se o **Método do Cotovelo** para determinar o número ideal de clusters. A análise do gráfico de inércia sugeriu que **3 clusters (k=3)** seria a divisão mais adequada, pois a queda na inércia se estabilizou a partir deste ponto.
- **Algoritmo:** O modelo **K-Means** foi aplicado aos dados pré-processados, segmentando o público nos 3 grupos definidos.

---

### **4. Perfis dos Clusters**

A análise final identificou três perfis distintos de consumidores:

| Cluster | Idade Média | Afinidade Média | Consumo de Engov | Mídia Preferida |
| --- | --- | --- | --- | --- |
| **0 (Cauteloso)** | 36 anos | 153 (Acima da Média) | 57% Consomem | **Spotify**, **TV Aberta**, **TikTok** |
| **1 (Fiel)** | 43 anos | 167 (Alta) | 75% Consomem | **TV Aberta**, **Instagram**, **Revistas** |
| **2 (Potencial)** | 39 anos | 92 (Baixa) | 55% Consomem | **TikTok**, **Spotify** |

### **Interpretação dos Clusters**

### **Cluster 0: O Consumidor Cauteloso**

Perfil: Com uma idade média de 36 anos e uma afinidade com a marca acima da média (153.03), este grupo já tem um bom relacionamento com a marca Engov. A taxa de consumo (56.92%) é boa, mas não tão alta quanto a de outros clusters.

- Características: A mídia preferida é bastante variada, mas com destaque para Spotify (23.08%), TV Aberta (20.00%) e TikTok (16.92%). A distribuição de gênero é predominantemente masculina (58.46%). Eles parecem ser um público engajado, mas que talvez não esteja totalmente convertido ao consumo regular.

### **Cluster 1: O Consumidor Fiel**

Perfil: Este é o grupo mais maduro, com idade média de quase 43 anos, e a maior afinidade com a marca (166.85). A taxa de consumo de Engov é a mais alta de todos os grupos (74.58%).

- Características: A mídia preferida é a TV Aberta (23.73%), seguida de perto por Instagram e Revistas (ambas com 15.25%). Eles representam o consumidor tradicional e leal da marca. Este é o público que a Engov precisa manter e fidelizar.

### **Cluster 2: O Público em Potencial**

Perfil: Com uma idade média de 39 anos, este grupo se destaca por ter a menor afinidade com a marca (91.86). A taxa de consumo de Engov é a mais baixa entre os grupos, com quase metade deles (44.74%) não consumindo o produto.

- Características: Este público prefere o TikTok (26.32%), o que sugere que eles podem ser mais jovens ou mais digitais que os outros grupos. A afinidade baixa e a alta porcentagem de não-consumidores indicam que este é o público mais difícil de converter.

---

### **Conclusões e Recomendações**

A clusterização foi eficaz em dividir o público em grupos com características bem definidas. As descobertas permitem que a marca Engov crie estratégias de marketing personalizadas para cada segmento:

- Para o **Cluster Fiel**, a recomendação é focar em **campanhas de fidelização**.
- Para o **Cluster Cauteloso**, as estratégias devem focar na **conversão** para consumo mais regular.
- Para o **Cluster Potencial**, a marca deve investir em **campanhas de aquisição** em mídias como o TikTok, com mensagens que abordem a baixa afinidade inicial.

# **Conclusão Geral**

1. **Segmentação Sólida:** Identificamos três perfis de público: o **Fiel** (com alta afinidade e consumo), o **Cauteloso** (com afinidade média, mas potencial para se tornar fiel), e o **Potencial** (com baixa afinidade, que representa a maior oportunidade de crescimento).
2. **Estratégia de Mídia:** Descobrimos que a marca precisa de uma estratégia multicanal, pois o público de **Classe A** consome **Spotify** e **Revistas**, enquanto as classes **B e C** se dividem entre **TV Aberta, TikTok e YouTube**.
3. **Posicionamento do Produto:** Os dados mostraram que o Engov é consumido por um público que não se associa apenas a baladas. A marca pode expandir seu posicionamento para além do "pós-festa" e se conectar com um público mais amplo.
4. **Afinidade e Idade:** Por fim, provamos que a idade não é o fator determinante de afinidade, mas sim o **estágio de vida**. A marca tem um público fiel em seu auge, mas precisa de estratégias diferentes para engajar os mais jovens e os mais velhos.
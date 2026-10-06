# PCS5917 – IA Adversarial

## Portfólio Individual

**Aluno:** Nome do aluno ou aluna  
**Disciplina:** PCS5917 – IA Adversarial  
**Período:** 3º período de 2026  
**Instituição:** Universidade de São Paulo – Escola Politécnica  
**Professor:** Victor Takashi Hayashi  

## 1. Objetivo do Portfólio

Este portfólio reúne as principais atividades, estudos, experimentos e reflexões desenvolvidos ao longo da disciplina **PCS5917 – IA Adversarial**.

O objetivo é documentar individualmente o processo de aprendizagem sobre:

- notícias e referências científicas sobre IA Adversarial (Aula 1);
- fundamentos de Inteligência Artificial e Segurança (Aula 2);
- aplicação de IA em cibersegurança (Aula 3);
- ataques adversariais contra sistemas de IA (Aulas 4 e 5);
- avaliação de ataques e uso de LLMs como juiz (Aula 6);
- defesas em Large Language Models (Aula 7).

Os experimentos realizados durante as aulas devem ser complementados por registros individuais, notebooks, respectivos resultados e referências bibliográficas (citações).

## 2. Organização do Repositório

**IMPORTANTE**: somente branch main (demais branches serão desconsideradas na correção).
Faça o desenvolvimento incremental com **commits semanais**, pois a evolução durante as semanas também é critério de avaliação.
Organize seu README focando em ser objetivo, com evidências de resultados e citações às referências utilizadas.

```text
.
├── README.md (com registros de resultados)
├── notebooks/ (colocar aqui os notebooks citados no README)
│   ├── aula-02-llm-jailbreaks.ipynb
│   ├── aula-03-asvspoof.ipynb
│   ├── aula-04-nanogcg.ipynb
│   ├── aula-05-pair.ipynb (e/ou cipherchat)
│   ├── aula-06-llm-judge.ipynb
│   └── aula-07-defesas-llm.ipynb
├── images/ (colocar aqui as imagens usadas no README)
│   └── ...
└── outros/
    └── ...
```

## Disclaimer de Uso Ético

Este repositório foi desenvolvido exclusivamente para fins acadêmicos e de pesquisa no contexto da disciplina **PCS5917 – IA Adversarial**.

Alguns experimentos, datasets, prompts, códigos e resultados apresentados podem conter **conteúdo potencialmente malicioso**, incluindo exemplos de jailbreaks, payloads e outras técnicas de ataque. Esses materiais são disponibilizados para fins de estudo, análise, reprodução controlada e compreensão de mecanismos de ataque e defesa.

Os conteúdos devem ser utilizados somente em **ambientes autorizados e controlados**, sem direcionamento a sistemas, modelos, redes, dispositivos ou usuários de terceiros. A reprodução dos experimentos deve respeitar as políticas de uso das ferramentas e os termos das plataformas utilizadas.

O conteúdo deste repositório **não constitui recomendação ou incentivo à realização de atividades maliciosas**. O objetivo é compreender riscos de segurança, desenvolver métodos de avaliação e contribuir para o desenvolvimento de sistemas de Inteligência Artificial mais seguros.

## 3. Resultados obtidos
### Aula 02 – Fundamentos de Segurança e IA

**Cenário**

Nesta atividade avaliou-se a robustez do modelo Kimi-K2 frente a ataques adversariais do tipo *jailbreak*.
O modelo está disponível no HuggingFace e foi utilizando o Inference Provider Novita.
O código gerado para chamada ao LLM está disponível em  [`notebooks/aula-02-llm-jailbreaks.ipynb`](notebooks/aula-02-llm-jailbreaks.ipynb)
Os ataques são baseado nos ataques disponíveis neste [dataset](https://github.com/yjw1029/Self-Reminder-Data/blob/master/data/jailbreak_prompts.csv), sendo empregadas técnicas de personas sem restrições, *roleplay*, ofuscação e cifras, além do uso de outros idiomas (português, russo, fijiano, guarani).
O ambiente de execução utilizado foi o Google Colab.

**Resultados**

No total, **12 dos 101 ataques** tiveram sucesso, uma taxa de sucesso de ataque de **11,9%**. A taxa separada por idioma:
    
| Idioma | Ataques | Sucessos | Taxa de sucesso |
|---|---:|---:|---:|
| Inglês | 75 | 6 | 8,0% |
| Português | 20 | 5 | 25,0% |
| Russo | 4 | 1 | 25,0% |
| Fijiano | 1 | 0 | 0,0% |
| Guarani | 1 | 0 | 0,0% |
| **Total** | **101** | **12** | **11,9%** |

![Taxa de sucesso de jailbreak por idioma](Outros/Aula%2002/taxa_sucesso_por_idioma.png)

Há uma diferença expressiva entre os idiomas. Os ataques em **inglês**, língua de maior cobertura no alinhamento do modelo, tiveram a **menor** taxa de sucesso (8,0%), ainda que concentrem a maioria das tentativas (75 de 101). Os ataques em idiomas de menor recurso foram proporcionalmente muito mais eficazes: **russo** (25,0%) e **português** (25,0%).

O padrão é consistente com a hipótese de que o alinhamento de segurança dos LLMs é mais frágil fora do inglês, já que as defesas são majoritariamente treinadas e avaliadas nesse idioma.
O conjunto completo encontra-se em [`Outros/Aula 02/prompts_e_respostas.csv`](Outros/aula%2002/prompts_e_respostas.csv).

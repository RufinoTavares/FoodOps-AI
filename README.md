# FoodOps AI — Previsão de Atrasos em Entregas

### Machine Learning | Python | Análise de Dados | Logística

## Sobre o projeto

O **FoodOps AI** é um projeto de Ciência de Dados desenvolvido para identificar pedidos de e-commerce com maior risco de atraso na entrega, utilizando dados públicos da Olist.

O objetivo é apoiar a priorização de pedidos que merecem acompanhamento logístico, utilizando técnicas de análise de dados, engenharia de atributos e Machine Learning.

## Problema de negócio

Em operações de e-commerce, acompanhar todos os pedidos com a mesma intensidade pode ser inviável.

A pergunta central do projeto é:

**Ao priorizar os 10% dos pedidos com maior risco previsto, quantos atrasos conseguimos identificar?**

## Tecnologias utilizadas

- Python
- Pandas e NumPy
- Scikit-learn
- XGBoost
- Google Colab
- Matplotlib
- Power BI (próxima etapa)

## Metodologia

O projeto foi desenvolvido em etapas:

1. Carregamento, limpeza e integração dos dados da Olist.
2. Construção da variável-alvo de atraso.
3. Análise exploratória dos pedidos e das rotas logísticas.
4. Engenharia de atributos relacionados a frete, vendedores e prazos.
5. Separação temporal dos dados para treinamento, validação e teste.
6. Treinamento e comparação de Regressão Logística, Random Forest e XGBoost.
7. Seleção do modelo com base na validação.
8. Avaliação final em dados reservados.

O modelo selecionado foi a **Regressão Logística sem pesos**.

## Resultados no teste final

| Métrica | Resultado |
|---|---|
| Pedidos avaliados | 19.294 |
| ROC-AUC | 0,7064 |
| Average Precision | 0,0704 |
| Precision@10% | 7,15% |
| Recall@10% | 20,47% |
| Lift@10% | 2,05x |

Ao priorizar os 10% dos pedidos com maior risco, o modelo identificou **138 atrasos entre 1.930 pedidos selecionados**, alcançando uma concentração de atrasos aproximadamente 2,05 vezes maior que a média do período.

## Limitações

- A taxa de atraso diminuiu de 9,93% na validação para 3,49% no teste final, afetando a comparação das métricas.
- A Average Precision foi menor no teste final, embora o ROC-AUC tenha permanecido próximo ao observado na validação.
- A calibração das probabilidades não foi resolvida. Portanto, o risco previsto deve ser utilizado principalmente como um **ranking relativo**, e não como uma probabilidade absoluta confiável.
- O estudo utiliza pedidos históricos entregues, o que limita a generalização para todos os pedidos de uma operação real.
- A disponibilidade histórica de todas as informações no momento da compra não pôde ser comprovada integralmente.

## Próximas etapas

- Construir um dashboard operacional no Power BI.
- Integrar consultas SQL.
- Explorar componentes de inteligência artificial para apoio à análise logística.
- Melhorar a documentação e a reprodutibilidade do projeto.

## Autoria

Projeto desenvolvido por Michele Rufino Tavares, formada em Física Computacional pela Universidade Federal Fluminense (UFF) e estudante de Ciência de Dados.

## Classificador de páginas Web no domínio de Setor Imobiliário

Classificador de páginas web voltado para o setor de imóveis. A classificação se divide em duas tarefas: identificar se o imóvel está anunciado para aluguel ou venda e o tipo do imóvel (casa, apartamento, outros).

##### Desenvolvido por Ana França

### Bibliotecas
- Pyhton 2.7
- NLTK 3.2.5
- scikit-learn 0.19.1
- auto-scikit 0.2.1
- XGBoost 0.6

### Estrutura do Projeto
- classifiers/ - Pasta com classificadores persistidos para cada tarefa.
- vectorize_selector_features/ - Pasta com procesos de vetorização de documentos e seleção de features aplicados durante a etapa de pré-processamento.
- scripts/ - Pasta com scripts para classificação:
  - preprocess.py - Script da etapa de pré-processamento. Transforma os documentos em matrizes termo-documento e persiste em arquivos temporarios.
  - automl_classifiers.py - Script da etapa de classificação. Utiliza arquivos gerados pelo script preprocess.py para realizar a tarefa de classificação.
- run_classifiers.sh - shell script base do projeto.

### Como utilizar...
Para classificar páginas web do setor de imóveis de um determinado diretório basta rodar o script `run_classifiers.sh` com os seguintes parâmetros:
- `<dir>`- Diretorio com as páginas web (html) para o processo de classificação
- `<output filename>` - Nome do arquivo de saída desejado

Ex.: `./run_classifiers.sh <dir> <output filename>`

O arquivo de saída gerado é no formato csv com os seguintes campos: 
  nome do arquivo, resultado da tarefa 1 (aluguel/venda), resultado da tarefa 2(casa, apartamento, outros).

# Corrida Noturna da Ponte Estaiada

Sistema de inscrições e resultados desenvolvido em Python para a disciplina de Programação I (UNIFSA).

## Como executar

Para iniciar o sistema, certifique-se de ter o Python instalado e execute o seguinte comando no terminal na pasta do projeto:

```bash
python corrida.py

```

## Funcionalidades

**Etapa 1:**

* Cálculo automático do valor da inscrição baseado em lote, distância escolhida (5km ou 10km) e descontos de meia-inscrição para corredores com 60 anos ou mais.


* Geração do código único do corredor e extração de primeiro nome utilizando obrigatoriamente técnicas de fatiamento de strings (*slicing*), sem o uso da função `split()`.


* Cálculo do tempo em segundos e definição do *pace* por km, com fatiamento de tempo exigido no formato estrito HH:MM:SS.


* Determinação automática da categoria do atleta e checagem de premiação.



**Etapa 2: Níveis implementados**

* **Nível Essencial:** Menu interativo completo para cadastrar corredor, listar inscritos, buscar corredor por código e registrar tempos posteriores, guardando todos os dados em dicionários dentro de uma lista principal.


* **Nível Intermediário:** Uso de tuplas inalteráveis para categorias e tempos-limite, uso de conjuntos (`sets`) para checagem rápida de códigos já utilizados, dicionários para contagem de inscritos e uso de *List Comprehensions* para listagem de resultados.


* **Nível Avançado:** Exibição da classificação geral por distância (menor para maior tempo), pódio por categoria detalhando os 3 melhores tempos, e um relatório final completo na saída do sistema com total de inscritos, arrecadação, tempos médios e corredores mais rápidos.



## Exemplo de uso

```text
==========================================
   SISTEMA CORRIDA PONTE ESTAIADA (UNIFSA)
==========================================
1 - Cadastrar corredor
2 - Listar inscritos
3 - Buscar corredor por código
4 - Registrar tempo de prova
5 - Calcular resultado (simulação individual)
6 - Inscritos por categoria
7 - Ver resultados (com tempo e premiados)
8 - Classificação geral por distância
9 - Pódio por categoria
10 - Sair e exibir relatório final
==========================================
Escolha uma opção (1-10): 1

--- CADASTRO DE CORREDOR ---
Nome completo: Maria Clara Sousa
Idade: 34
Distância (5 ou 10 km): 5
Lote (1 ou 2): 1

==========================================
        COMPROVANTE DE INSCRIÇÃO          
==========================================
Primeiro Nome: Maria
Código       : MARSOU34
Categoria    : Adulto
Distância    : 5 km
Valor a pagar: R$ 80.00
==========================================

```

## Decisões da dupla

* **Resolução de códigos repetidos:** Utilizamos um `set` de controle chamado `codigos_usados`. Caso um novo corredor gere um código base (ex: MARSOU34) que já exista no sistema, o programa resolve o conflito adicionando um sufixo numérico de auto-incremento (ex: MARSOU34-2, MARSOU34-3, etc.) no momento do cadastro.


* **Dados de teste automáticos:** Para otimizar os testes e a correção da banca, implementamos a função `carregar_dados_exemplo()`. O sistema já inicia com 8 corredores cadastrados previamente na memória (dados sugeridos no documento do projeto), dispensando a digitação manual repetitiva a cada execução.


* **Restrição de Funções Nativas:** A exigência de não usar `.split()` para a leitura do tempo e do nome foi respeitada integralmente, lidando com os dados através dos métodos `.find()`, `.rfind()` e índices diretos de *slicing*[cite: 3, 6].

## Autores

José Teixeira (https://github.com/Dev-JoseTeixeira)
Kawan Arruda (https://github.com/kawanxxz)

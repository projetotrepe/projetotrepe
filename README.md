# Projeto CIN-UFPE - TRE-PE

__Combate à Desinformação__

Este projeto é uma parceria entre o Centro de Informática e o Tribunal Regional Eleitoral de Pernambuco e visa a conceber e construir um sistema para auxiliar o tribubal a combater a desinformação nas redes sociais. Depoimentos contendo potenciais <i>fake news</i> a respeito do processo eleitoral brasileiro serão coletados e classificados por um modelo de aprendizagem de máquina, permitindo ao órgão agir proativamente para esclarecer o cidadão e mitigar o espalhamento da informação imprecisa.

## O projeto

- [Kick-off](#Kick-off)
- [Escopo](#Escopo)
- [Equipe](#Equipe)
- [Documentos](#Documentos)
- [Terminologia](#Terminologia)
- [Arquitetura](#Arquitetura)

## Kick-off

O projeto iniciou em maio de 2022, com previsão para durar até novembro do mesmo ano. O documento gênese do projeto (plano de trabalho), bem como
uma planilha com exemplos de tweets contendo <i>fake news</i> foram fornecidos pelo TRE:
- <a href="https://docs.google.com/document/d/1FFtdv7i1mJ_0aSddEmxohi7XMRdWHkMO/view" target="_new">Plano de Trabalho</a>
- <a href="https://drive.google.com/file/d/1iw_X-tjyWAL4KPh39DY8EOV8-HQ0viPG/view" target="_new">Planilha com exemplos de tweets com <i>fake news</i></a>

## Escopo

Inicialmente, serão coletados dados apenas do Twitter. O usuário autenticado poderá cadastrar fluxos, contendo termos (palavras-chave), perfis de usuário e outros filtros, a fim de coletar tweets de interesse, os quais serão automaticamente classificados quanto ao sentimento: `positivos`, `neutros` ou `negativos` (com `negativo` significando <i>fake news</i>). O usuário poderá, então, visualizar, filtrar e ordenar os tweets coletados em cada fluxo, alterar sua classificação e responder a um ou mais deles, utilizando uma conta Twitter previamente cadastrada. Respostas-padrão poderão ser cadastradas para serem sugeridas a tweets negativos de determinado fluxo. Os tweets reclassificados pelos usuários serão utilizados para retreinar o classificador, de modo que a acurácia melhore com o tempo.

## Equipe

- Sergio Soares (scbs@cin.ufpe.br)
- George Darmiton da Cunha Cavalcanti (gdcc@cin.ufpe.br)
- Paulo Salgado Gomes de Mattos Neto (psgmn@cin.ufpe.br)
- Francimaria Rayanne dos Santos Nascimento (frsn2@cin.ufpe.br)
- Rafael Borba Costa dos Santos (rbcs@cin.ufpe.br)
- Francisco Mauro Falcao Matias Filho (fmfmf@cin.ufpe.br)
- Marcia Andrade Porto (map@cin.ufpe.br)
- Herikles V. F. Cordeiro (hvfc@cin.ufpe.br)
- Tales Tomaz Alves (tta@cin.ufpe.br)

Grupo do google: projeto-cin-ufpe-tre-pe-l@cin.ufpe.br

## Documentos

Os seguintes documento colaborativos estão versionados no google drive do projeto (projetotrepe@cin.ufpe.br):
- <a href="https://docs.google.com/document/d/1toSEPuZElSXHxttON7wjd_zLiKlxcSwp/edit#" target="_new">Documento de requisitos</a>
- <a href="https://docs.google.com/spreadsheets/d/1zAS5NzxOKYrU-t0ECLQkVdj4rbiYx-9b5SZSyVnDjPU/edit#gid=0" target="_new">Cronograma</a>

## Terminologia

- Fake news: informação inverídica, inexata ou imprecisa, acidental ou intencionalmente veiculada.
- Tweet: um texto de até 280 caracteres publicado no Twitter.
- Fluxo: um conjunto de termos e filtros (query), no formato da busca do Twitter (https://twitter.com/search-advanced), criado pelo usuário para coletar tweets de interesse.
- Sentimento: atributo do tweet que representa a probabilidade de conter <i>fake news</i>, em três classes:
   `positivo`: baixa probabilidade;
   `neutro`: média probabilidade;
   `negativo`: alta probabilidade.

## Arquitetura

Estão previstos os seguintes componentes de software na solução. A definir suas estruturas internas, comportamentos e interfaces.

![image](https://user-images.githubusercontent.com/105316617/167894123-e139f269-26cf-45c0-99c9-c215140b6010.png)

- ___scraper___: acessa os fluxos cadastrados no BD, busca na API do Twitter e salva os tweets e metadados em “BD produção”.
- ___web app___: permite o cadastro dos fluxos, usuários e modelos de resposta, bem como a visualização dos tweets coletados e classificados. Gera relatórios. Permite responder aos tweets.
- ___ETL___: extrai, pré-processa e carrega os tweets e metadados do BD Produção para o BD ML. 
- ___ML___: processamento, treino, retreino e testes dos modelos de ML para classificação do sentimento dos tweets.
- ___ML Produção___: acessa o BD Produção para classificar os tweets recém coletados e obter os tweets reclassificados pelos usuários para retreino dos modelos.

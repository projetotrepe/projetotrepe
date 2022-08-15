# Projeto CIN-UFPE - TRE-PE

__Combate à Desinformação__

Este projeto é uma parceria entre o Centro de Informática e o Tribunal Regional Eleitoral de Pernambuco e visa a conceber e construir um sistema para auxiliar o tribubal a combater a desinformação nas redes sociais (Twitter). Depoimentos contendo potenciais <i>fake news</i> a respeito do processo eleitoral brasileiro serão coletados e classificados por um modelo de aprendizagem de máquina, permitindo ao órgão agir proativamente para esclarecer o cidadão e mitigar o espalhamento da informação imprecisa.

## O projeto

- [Kick-off](#Kick-off)
- [Escopo](#Escopo)
- [Equipe](#Equipe)
- [Documentos](#Documentos)
- [Terminologia](#Terminologia)
- [Arquitetura/Entregas](#Arquitetura/Entregas)
- [Amostra](#Amostra)

## Kick-off

O projeto iniciou em maio de 2022, com previsão para durar até janeiro de 2023. O documento gênese do projeto (plano de trabalho), bem como
uma planilha com exemplos de tweets contendo <i>fake news</i> foram fornecidos pelo TRE:
- <a href="https://docs.google.com/document/d/1FFtdv7i1mJ_0aSddEmxohi7XMRdWHkMO/view" target="_blank">Plano de Trabalho</a>
- <a href="https://drive.google.com/file/d/1iw_X-tjyWAL4KPh39DY8EOV8-HQ0viPG/view" target="_blank">Planilha com exemplos de tweets com <i>fake news</i></a>

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
- <a href="https://docs.google.com/document/d/1toSEPuZElSXHxttON7wjd_zLiKlxcSwp/edit#" target="_blank">Documento de requisitos</a>
- <a href="https://docs.google.com/spreadsheets/d/1zAS5NzxOKYrU-t0ECLQkVdj4rbiYx-9b5SZSyVnDjPU/edit#gid=0" target="_blank">Cronograma</a>
- <a href="https://docs.google.com/presentation/d/1xAJx3UGdRkWQ0CfsShtBRk2zLB4aX2CA" target="_blank">Protótipo de telas</a>
- <a href="https://docs.google.com/document/d/e/2PACX-1vRdqi3xK9wCXNIbVNkThZJmLIwYPmkj3lGXuXO_UHJfVQ4srKLz81uNncDR6f72r52mz3mF6_94hCdc/pub" target="_blank">API (backend) do SCDE</a>

## Terminologia

- Fake news: informação inverídica, inexata ou imprecisa, acidental ou intencionalmente veiculada.
- Tweet: um texto de até 280 caracteres publicado no Twitter.
- Fluxo: um conjunto de termos e filtros (query), no <a hre="https://twitter.com/search-advanced" target="_blank">formato da busca do Twitter</a>, criado pelo usuário para coletar tweets de interesse.
- Sentimento: atributo do tweet que representa a probabilidade de conter <i>fake news</i>, em três classes:
   `positivo`: baixa probabilidade;
   `neutro`: média probabilidade;
   `negativo`: alta probabilidade.

## Arquitetura/Entregas

-<a href="https://docs.google.com/presentation/d/1xAJx3UGdRkWQ0CfsShtBRk2zLB4aX2CA" target="_blank">Apresentação contendo a arquitetura da solução, macroentregas do projeto e resumo do cronograma (08/2022)</a>

## Amostra

Tweets coletados a partir de 20/05/2022 para os fluxos identificados nos <a href="https://docs.google.com/document/d/1toSEPuZElSXHxttON7wjd_zLiKlxcSwp/edit#" target="_blank">requisitos</a>:
- <a href="https://scde.cin.ufpe.br/api" target="_blank">https://scde.cin.ufpe.br/api</a>

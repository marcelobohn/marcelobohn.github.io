---
layout: post
title:  "Primeira semana de testes unitários"
date:   2015-11-25 22:00:00
category: dev
tags: [quality, php, phpunit, tests]
---
Fechei a primeira semana de testes e o sentimento é muito bom. Como previsto tive que fazer ajuste do código da aplicação para conseguir obter o retorno necessário dentro dos métodos de teste, fato que levou a criar um código melhor e melhores práticas.

Acredito que esse tipo de problema, é por exemplo um dos causadores das falhas sem explicação nos sistemas, pois são momentos que os métodos não retornam nada e falham por  falta de parâmetos e ou parâmetos incorretos.

Outro ponto positivo dos testes, é a compreenção mais detalhada dos métodos que ainda não precisaram passar por manutenção. Depois de quase dois anos prestando manutenção no código, sempre tem aqueles pontos não acessados que agora serão vasculhados.

Por fim, vou acabar passando um a um cada controller com suas actions e cada model com seus métodos, ajustando e melhorando cada um deles.

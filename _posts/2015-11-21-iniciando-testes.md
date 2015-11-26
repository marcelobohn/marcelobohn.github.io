---
layout: post
title:  "Iniciando testes unitários"
date:   2015-11-21 17:30:00
category: dev
tags: [quality, php, phpunit, tests]
---

Essa semana começei a implementar os primeiros testes unitários no projeto que trabalho, é foi construido com PHP e Zend Framework, então o caminho foi PHPUnit. O projeto não foi iniciado pela empresa que trabalho, mas com mais de um ano dado manutenção no mesmo, passei a acreditar que seria possível encontrar um caminho melhor para algumas coisas.

O carregamento do projeto pelo PHPUnit não foi muito complexo e logo consegui rodar o primeiro teste de Model. Mas no segundo momento, quando fui testar um controller, tive problemas mas que também puderam ser superados com algumas buscas.

Então depois de refatorar um pouco a estrutura começei a fazer mais testes. Logo senti o benefício dos testes, quando fui testar um controller que retornava um json, o mesmo tinha um `exit` que acabava encerrando os testes, então tive que corrigir o método para não fazer isso, pois não era uma boa prática e fiz a implementação correta.

Para ser honesto, depois de algumas semanas estudando e refletindo sobre o assunto, passei a não acreditar como é possível implementar um método, sem que o mesmo passe sobre uma validação feita tb por código e fazer TDD e escrever o teste primeiro e depois o método faz muito mais sentido.

Estou bem no começo, mas tenho certeza que logo vou ter felizes benefícios dos testes.

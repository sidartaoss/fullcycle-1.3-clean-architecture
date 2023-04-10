# Clean Architecture - Notification Pattern em Products

- A aplicação, até o momento, trabalha em um cenário onde, a cada vez que a camada de domínio verifica uma falha de validação, é retornado um erro à camada de apresentação.

- Isso pode acabar trazendo uma experiência desagradável ao usuário final. Por que não retornar todos os erros de uma só vez? Imaginemos um caso de uso em que um formulário submete os dados e a camada de domínio recebe esses dados para validação.

- É dentro desse cenário que _Martin Fowler_ nos apresentou, em 2004, um padrão (ou _pattern_, em inglês) conhecido como _Notification_.

- Conforme o próprio blog de _Martin Fowler_, trata-se de:

> "Um objeto que coleta informações sobre erros e outras informações na camada de domínio e as comunica à (camada de) apresentação."

- O cenário de aplicação é muito bem descrito por _Martin Fowler_ e combina bem com o cenário da nossa aplicação:

> "Um cenário de aplicação comum é o de uma (camada de) apresentação capturando dados do usuário e enviando esses dados para o domínio para validação. O domínio precisa fazer uma série de verificações e, se alguma delas falhar, avisa a (camada de) apresentação."

- Resumidamente, _Martin Fowler_ explica que:

> "Uma Notificação (ou _Notification_, em inglês) é um objeto que o domínio usa para coletar informações sobre erros durante a validação. Quando um erro aparece, a Notificação é enviada de volta para a (camada de) apresentação para que a (camada de) apresentação possa exibir mais informações sobre os erros."

- Assim, o _Notification Pattern_ funciona como um _container_ acumulador de erros, para que se possa retornar todos os erros de uma vez, evitando a geração excessiva deles.

- Nesse contexto, este desafio propõe:

  - Utilizar o padrão de _Notification_ na entidade de _Products_.

  - Implementar testes unitários.

> N.T.: A solução envolve os arquivos:
> /src/domain/product/entity/product.spec.ts
> /src/domain/product/entity/product.ts

> FOWLER, Martin. Notification. 09 de ago. de 2004. Disponível em: <https://www.martinfowler.com/eaaDev/Notification.html>. Acesso em: 10 de abr. de 2023.

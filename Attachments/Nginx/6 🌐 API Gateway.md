Um **API Gateway** simplifica e gerencia o acesso aos serviços de backend, oferecendo um ponto de entrada único e controlado para os clientes consumirem funcionalidades fornecidas por APIs diversas.

![https://assets-global.website-files.com/5ff66329429d880392f6cba2/643fd2fde829634fa4f769a0_6178d93647ddf9f443e800f4_API Gateway example.png](https://assets-global.website-files.com/5ff66329429d880392f6cba2/643fd2fde829634fa4f769a0_6178d93647ddf9f443e800f4_API Gateway example.png)

é muito comum que tenhamos serviços diferentes realizando tarefas diferentes. Principalmente quando utilizamos uma arquitetura orientada a microsserviços.

Então o que nós fizemos aqui foi criar serviços diferentes e ter um ponto de entrada através desse servidor para esses serviços - e esse ponto de entrada tem um nome.

Em uma arquitetura de microsserviços, quando nós temos um ponto único de entrada, chamamos isso de API Gateway ou de portão de uma API. Então, a partir de uma API Gateway é decidido para onde essa requisição vai ser realmente redirecionada.

Então, o problema que essa técnica visa resolver é aquela ideia de clientes acessando livremente cada um dos serviços e de que às vezes um serviço ou domínio muda para outro servidor, ou alguma coisa assim do tipo.
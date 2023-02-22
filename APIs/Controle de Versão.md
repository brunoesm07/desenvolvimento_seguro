Imagine que você está trabalhando em um aplicativo extenso que lança novas versões de uma API todos os dias. Muitos outros aplicativos dependem de sua API para que seus recursos funcionem conforme o esperado.

Uma boa estratégia de controle de versão garantirá que pelo menos uma versão de sua API funcione conforme o esperado.

## Diferentes tipos de estratégias de versionamento

1.  **Versionamento de URI:** Esta é a estratégia de versionamento mais comum, embora viole cada URI que deve conter um recurso exclusivo. Quando uma versão do URI é concluída, todos os recursos são atualizados para uma nova versão. O controle de versão de URI também pode causar problemas com o armazenamento em cache. Um exemplo dessa estratégia é o seguinte:

````
https://website.com/api/v1/users

https://website.com/api/v2/users
````

2.  **Versões de parâmetros de consulta:** essa estratégia declara a versão de uma API usando parâmetros de consulta. Um exemplo deste tipo de estratégia pode ser o seguinte:

``https://website.com/users?version=1``

3. **Controle de versão de cabeçalhos personalizados:** o controle de versão também pode ser feito passando cabeçalhos de solicitação personalizados. Um exemplo será o seguinte:

``curl -H "accept-version: 1" https://website.com/users ``

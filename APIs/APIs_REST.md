# Princípios de API REST

Roy Fielding criou o REST em 2000. As APIs REST (Representational State Transfer) são aquelas APIs que seguem as diretrizes da arquitetura REST. Eles também são conhecidos como APIs RESTful.

APIs REST seguem seis princípios de design que são os seguintes:

1.  **Separação cliente-servidor:** A aplicação que está solicitando o recurso é chamada de cliente, e a aplicação que possui o recurso é chamada de servidor. Quando o cliente solicita uma solicitação ao servidor, o servidor envia uma resposta ao cliente. O servidor não pode iniciar uma solicitação ao cliente. Em uma API RESTful, o cliente e o servidor são sempre mantidos independentes um do outro. Isso garante que o cliente e o servidor possam ser dimensionados independentemente.
    
2.  **Stateless:** Em uma API RESTful, cada solicitação precisa conter os dados necessários para processá-la. Os servidores não têm permissão para armazenar nenhum dado relacionado ao cliente. Nenhuma sessão ou estado de autenticação é armazenado no servidor. Se o cliente exigir autenticação, ele precisará se autenticar antes de enviar uma solicitação ao servidor.
    
3.  **Armazenável em cache:** nas APIs REST, os recursos devem ser capazes de armazenar em cache no cliente ou no servidor. Quando um cliente solicita um recurso do servidor, a resposta do servidor conterá as informações sobre se o recurso pode ser armazenado em cache ou não e por quanto tempo. A ideia principal do cache é melhorar o desempenho do cliente reduzindo a largura de banda necessária para carregar o recurso.
    
4.  **Sistema em Camadas:** Nas APIs REST, pode haver vários intermediários entre o cliente e o servidor. Nem sempre é necessariamente verdade que o cliente se conecta diretamente ao servidor e solicita um recurso. Pode haver vários sistemas entre eles que são responsáveis ​​por lidar com segurança, tráfego, balanceamento de carga, redirecionamento, etc. O cliente ou o servidor não tem nenhuma informação sobre quantos sistemas estão entre eles.
    
5.  **Interface uniforme:** todas as solicitações e respostas em uma API REST devem seguir um protocolo comum. Isso permite que os aplicativos evoluam de forma independente. O cliente e o servidor podem interagir entre si em um único idioma, independentemente da arquitetura em que se baseiam.
    
6.  **Code on Demand (opcional):** quando um cliente solicita um recurso, o servidor pode retornar executáveis ​​como parte da resposta. Esta é uma restrição opcional. Em certos casos, isso pode ajudar a reduzir a quantidade de código que deve ser escrito no cliente.
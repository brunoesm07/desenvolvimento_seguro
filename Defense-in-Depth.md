## 1. O princípio da Defesa em Profundidade

O princípio de Defesa em Profundidade é uma estratégia de segurança da informação e cibernética que se baseia na aplicação de várias camadas de controles de segurança para proteger os ativos de uma organização. Baseia-se na ideia de que, se uma camada de segurança falhar, as outras camadas ainda poderão proteger o ativo. 

Tem como objetivo criar um ambiente seguro que seja resiliente a ataques e possa detectar e responder rapidamente a quaisquer incidentes de segurança. 

Se um invasor externo derrubar uma linha de defesa ou uma ameaça interna comprometer parte da rede de uma organização, outras medidas de segurança podem ajudar a limitar e mitigar os danos a toda a rede. 

### 1.2 Pilares

Existem três partes principais de qualquer estratégia de defesa em profundidade, que são:

1. **Controles físicos**: medidas de segurança que impedem o acesso físico a sistemas de TI, como vigilância, câmeras de segurança, leitores de impressão digital e portas trancadas.

2. **Controles técnicos**: medidas de segurança que protegem a segurança da rede e outros recursos de TI usando hardware e software, como sistemas de proteção contra intrusões, firewalls de aplicativos web ([WAF](https://dev.to/brmartin/waf-o-que-e-e-qual-sua-funcao-4dhf)), gerenciamento de configurações, proxy, scanners da web, gestão de identidades e acessos, antivírus e anti-malwares, sistemas de prevenção de perda de dados, sistemas de autenticação de dois fatores, biometria, gerenciadores de senhas, redes privadas virtuais, criptografia de dados, sistemas de backups etc.

3. **Controles administrativos**: medidas de segurança que se referem às políticas e procedimentos direcionados aos funcionários de uma organização e seus fornecedores e parceiros comerciais. Os exemplos incluem: políticas de privacidade e proteção de dados, gerenciamento de riscos de colaboradores terceiros, parceiros comerciais e fornecedores, políticas de treinamento e conscientização de segurança, adoção de metodologias para promover a melhoria contínua e garantir as melhores práticas etc.

![[defesa em profundidade.png]]
Img/Fonte: Imperva

### 1.3 Segurança em camadas

A segurança em camadas refere-se ao uso de vários produtos e práticas de segurança para proteger uma organização contra um vasto spectrum de ameaças físicas e cibernéticas.

No geral, uma arquitetura de defesa em profundidade é composta por sete camadas de proteção.

1- **Política, procedimentos e conscientização**

Trata-se da camada responsável por implementar as políticas e os procedimentos que irão governar as práticas de segurança da informação e segurança cibernética de uma empresa, bem como as ações de conscientização, treinamento e educação dessas práticas em geral que deverão ser seguidas e desempenhadas por todos os funcionários, fornecedores e parceiros comerciais da empresa.

2- **Segurança física**

Considerada a primeira barreira de proteção de uma infraestrutura de TI, a camada de segurança física tem como objetivo garantir que as ameaças não tenham acesso físico aos ativos tangíveis, como pessoas, servidores, desktops, dispositivos de rede – switches, roteadores, racks de telecomunicação, racks de redes – path panels, painéis de controle elétricos, painéis de controle de climatização, dispositivos de armazenamento de dados e outros recursos valiosos.

3- **Segurança de perímetro**

A camada segurança de perímetro, tem como objetivo implementar a proteção necessária entre o ambiente  externo e a infraestrutura de TI interna da empresa. A defesa de perímetro permite a entrada de dados autorizados, bloqueando o tráfego suspeito.

Esta camada é composta por mecanismos e ferramentas de proteção de borda tais como: roteadores, switches layer 3, appliances de firewall, sistemas de IDS e IPS e sistemas DLPs. Além de esquemas como DMZ – zonas desmilitarizadas de rede, sistemas de proxy e conversão de endereços de rede (NAT), VPN – redes virtuais privadas, dentre outras tecnologias de proteção.

4- **Segurança de rede interna**

A camada de segurança de rede interna deve possuir mecanismos e ferramentas de proteção capazes de lidar com a identidade e autenticação dos usuários da rede, autorizando ou não, o acesso destes usuários aos recursos computacionais e de redes disponíveis na infraestrutura de TI, protegendo os dados e informações que navegam pela rede, além de outros mecanismos e ferramentas que exerçam funções relacionadas a filtros que permitam analisar de forma consistente todos os pacotes de dados que circulam pela mesma. 

5- **Segurança de host**

A camada de segurança de host, concentra-se em manter a proteção dos hosts (computadores, notebooks, smartphones, servidores, etc) e respectivamente dos sistemas operacionais que controlam estes hosts.

6- **Segurança da aplicação**

A camada de segurança aplicação tem como objetivo garantir a segurança e proteção de aplicativos, sistemas de informação e demais outras aplicações contra diversas ameaças.

7- **Segurança de dados**

Trata-se da camada de segurança mais profunda da estratégia de defesa em profundidade e tem como principal objetivo proteger um dos ativos de TI mais valiosos que a empresa possui, os “dados”.

![[segurança em camadas.png]]
Img/Fonte: TechTarget

### 1.4 Segurança integrada

Garante que vários produtos de segurança funcionem entre si para melhorar sua capacidade de detectar e mitigar ameaças. Uma estratégia de segurança pode ser em camadas, mas não integrada, enquanto uma estratégia de segurança integrada é em camadas por natureza.

## 2. Fazendo uma analogia (relembrando minha época de aviação)

Em segurança da aviação aborda-se com frequência o **modelo do queijo suíço**, que vejo ter importância também na segurança cibernética. 

No modelo do queijo suíço, as defesas de uma organização contra falhas são modeladas como uma série de barreiras, representadas como fatias (camadas, na defesa em profundidade) de queijo e, quanto mais fatias há, mais segurança haverá. 

Porém orifícios (vulnerabilidades) nas fatias de queijo representam pontos fracos individuais em partes individuais do sistema e variam continuamente em tamanho e posição em todas as fatias. Quando esses orifícios se alinham, ocorre o acidente (em segurança cibernética, o vazamento de dados, exploit, etc).

> James Reason propõe que todo perigo possui barreiras e salvaguardas, e que na ocasião de um acidente é importante detectar como e porque estas barreiras falharam.
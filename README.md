![windows1](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/facfe533-f38c-410a-bd41-b63fbef13a0f)

# Introdução

Essa wiki documenta todas as etapas de implementação de um servidor Windows proposto pelo professor [Paulo Henrique Sousa Barbosa](https://github.com/agenteph) na disciplina de Redes de Computadores II do curso de Ciência da Computação do Instituto Federal de Educação, Ciência e Tecnologia do Maranhão - Campus Imperatriz (IFMA). Projeto implementado por [Elvis Rodrigues Almeida](https://github.com/Elvis-Almeida)

Em toda nossa jornada iremos utilizar uma máquina virtual, mas após a criação da máquina virtual e execução do `.iso` todo o resto será igual a um computador real após a execução do pen-drive bootável. Irei considerar que você saiba criar e executar um pen-drive bootável *(caso queira instalar em seu computador físico)* e também instalar o [VitualBox](https://www.virtualbox.org/) em seu PC, mas se você não tem esse conhecimento de como fazer, aqui estão alguns links que te ajudaram nisso:

>  [VirtualBox: Saiba o que é, como funciona e como instalar!](https://blog.b2bstack.com.br/virtualbox/)

> [Como criar pendrive bootável Windows? O passo a passo!](https://blog.betrybe.com/tecnologia/pen-drive-bootavel-windows/)

> [Como dar boot no computador pelo pendrive](https://tecnoblog.net/responde/boot-pen-drive-windows-mac/). 

---

## Especificação do computador

Processador: Intel® Core™ i5-9300H CPU @ 2.40GHz × 8<br>
Memória ram: 8GB<br>
Placa de vídeo: GTX 1650<br>
Sistema operacioal: Linux Pop!_OS 22.04 LTS<br>
Disco: SSD NVMe m.2 512GB<br>
Placa de rede: Gigabit<br>

# Instalando servidor

## Baixando `.iso`

Para baixar a `.iso` vamos para o site oficial da Microsoft que fica neste link https://www.microsoft.com/pt-br/evalcenter/download-windows-server-2016 e lá vamos baixar a versão em Inglês de 64 bits

> :warning: essa versão que vou usar é apenas de teste, sendo possivel utilizar por apenas 180 dias gratuito, caso queira implementar como servidor de produção recomenda-se comprar uma licença oficial.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fc557443-4024-4188-8260-5379908f9401)


## Criando máquina virtual 

Agora que já temos o `.iso` vamos criar nossa maquina virtual, basta abrir o **VirtualBox** e clicar em **Novo** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/d53f3d10-30a5-4991-a4c7-a2a9cff7d6c5)

Irá abrir uma janela como essa, e nela você colocará o nome da sua maquina vitual, selecionará a `.iso` e irá marca a opção **pular instalação desassistida** *(Caso não marque essa opção irá apresentar uma falha na instalação)* agora após isso é só clicar em **Próximo**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9caaaa7c-286e-4773-b42e-1264b737af63)

Agora vamos configurar o hardware da nossa maquina virtual, essa parte é muito relativa ao hardware que você tem, o recomendado é que se utilize menos da metade da capacidade do seu computador, tanto em **CPU** quanto em menmória **RAM**. Depois é só clicar em  **Próximo**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a3650ea4-bef7-42f7-b215-d60a98c32266)

Essa parte irei colocar **30GB** de disco para ser usado pela maquina vitual, e conforme o espaço que você tiver disponível pode colocar mais, porém não deixe menos que **30GB** pois pode não ser sufuciente para o sistema dependendo que for intalar. Após isso é só clicar em  **Próximo**

> :warning: Recomendado colocar acima de **30GB**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c1faa25c-c74f-4b4c-83fd-c356e91e580c)

Aqui é um resumo das configurações, aperte em **Finalizar**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ac144bdf-7167-479a-be7d-7781aa3abc66)

## Instalando Windows

Antes de iniciamos desativar a rede durante a instalação para que a instalação seja mais rápida, pois caso contrario iria ser feito varios downloads e atualizações durante a instalação.

Para isso vamos em **Configurações**.

![Captura de tela de 2023-03-21 22-27-36](https://user-images.githubusercontent.com/70353348/226778223-c8cae63f-ea78-4bcf-9bee-0013e31c2b6b.png)

Depois selecione **Rede**, na janela de rede em **Conectado a**, selecione a opção **Placa em modo bridge** (*isso fará o computador virtual pegar o ip da sua rede real, dessa forma tornando possivel conectarmos ao servidor mais tarde*) e na opção avançado desmarque a caixinha de **Cabo conectado** (*isso fará nossa instalação ser mais rápida, pois não irá baixar atualizações durante a instalação o que pode causar demora*). 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/d1505a31-e071-4cd8-bace-e8eb2b0ec013)

Nesse momento é só apertar na setinha verde **Iniciar** para ligar a maquina virtual.

![Captura de tela de 2023-03-21 22-27-36](https://user-images.githubusercontent.com/70353348/226778223-c8cae63f-ea78-4bcf-9bee-0013e31c2b6b.png)

Aguarde o sistema iniciar

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/16dff1ef-ffc7-408c-b4ad-bdf2b1eed065)

Aqui você pode apertar em **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b0fac10d-88e2-46f3-922f-0ef7e51a6408)

Clique em **Install now**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fedfab6f-626e-45f1-a3bc-a001d2fc2554)

Aqui vamos selecionar a versão do nosso Windows que será a **2016 Standard Evaluation (Desktop Experience)** que no caso é a segunda opção. Aperte **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/87bc96cd-71df-45b8-90c8-e1a943476d79)

Vamos aceitar os termos e apertar em **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/e8a004cb-df79-4213-90f8-2054c7739332)

Agora vamos selecionar a segunda opção, que é a instalação customizada.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/df9e663f-4963-43d9-8253-a4baffc1c89d)

Vamos selecionar o disco e apertar em **Next** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b19a8075-6523-4edc-8654-8798c28a014c)

Após isso vamos aguardar a instalação ser finalizada.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2e8f014a-2ee5-4d57-9838-90ee9d18aaac)

Após finalizar essa etapa o sistema será reiniciado automáticamente

---

Depois de reiniciar será pedido que você crie uma senha para o servidor, e após criada é só apertar em **Finish** 

> :warning: É altamete recomendado que você cria uma **senha forte** para o seu servidor em produção! 

> :warning: A senha necessita ter letras **maiúsculas**, **minúsculas** e **números**!

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0ac3c16a-cc88-4250-955a-994fd4f671ed)

Agora podemos entrar no nosso servidor, para aparecer a tela de senha basta precionar **Ctrl + Alt + Delete**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6f8b4885-6339-4f89-bc28-16ed1adea6f2)

Caso você tenha o mesmo problema que eu tive que mesmo precionando as teclas não funcionava você pode usar um teclado virtual para precionar esse botões, é só ir em **Entrada** depois **Teclado** e depois em **Teclado de Tela**.

![gif](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/56359612-4a4c-431f-a403-f63a2422f028)

Descobri outro metodo mais fácil para contornar esse problema, é só ir em **Entrada** depois **Teclado** e **Inserir Ctrl + Alt + Del**

![Gravação-de-tela-de-27-05-2023-13_28_26](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b31072f9-7feb-484b-af41-b2fb4939b150)


# Visão Geral

Após instalar nosso servidor temos essa tela inicial

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/dc483aa5-e564-4af8-8bc9-41b2598e0230)

Agora vamos abrir o programa **Server Manager** (*que é o uma ferramenta de gerenciamento do servidor feito para facilitar a administração e o monitoramento*), caso esse programa já não tenha aberto automaticamente.

> :warnig: Para abrir qual quer programa que eu mensionar você pode ir na lupa na barra inferior e logo após escrever o nome do programa.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/31627595-3f8e-4ffb-8a62-24f35e1290d4)

Essa é a pricipal tela que vamos usar durante toda nossa jornada onde temos no lado esquerdo temos **Dashboad**, **Local Server**, **All Servers** e o **File and Storage Services** que:

- Em **Dashboad** você pode ver o status geral do seu servidor de forma resumida.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/149672ab-9e6a-432b-a3cd-915bc5c5b66c)

- Em **Local Server** é onde vemos varias as informações do servidor, como nome, data e hora, atualizações, firewall entre outras.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/eec62fe0-6881-4928-9635-50904022fbd0)

- Em **All Servers** ira mostrar todos os servidores conectados (*sim, é possível gerenciar um servidor apartir do outro*)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9705a177-73f9-41b0-86b7-a55cf87dab79)

- E em **File and Storage Services** é o serviço de compartilhamento de arquivo que já vem instalado no servidor, porém não é recomendado usar ele com a configuração que veio, vamos ajustar isso mais afrente. 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b3753a59-14e0-42fc-9f02-c2b12f73dc8a)

No canto superior direito temos as opções **Maneger** e **Tools** onde:

O **Maneger** é onde podemos adicionar ou remover funções e recursos, adicionar servidores, criar grupos de servidores e gerenciar as propriedades do servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/78173dc3-afbf-4b67-bc0c-f43f2c5139d7)

O **Tools** é onde fica nossas ferramentas, ou seja, as configurações de todas as funções e recursos adicionados no servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/41532634-296e-431d-86ad-eb31beeb5e95)

## Atualizando

Antes de tudo vamos atualizar nosso servidor, isso é extremamente importante pois deixar o windows desatualizado se torna-o vulneravel a ataques de invasores, dessa forma para atualizarmos vamos em **Windows Update**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2db53d01-af2c-4af0-b582-20acf3033efb)

Agora vamos em **Check for updates**

> :warning: Caso você esteje fazendo em uma maquina vitual apenas de teste como eu, atualize somente se você estiver alocado muito espaço em disco para seu windows caso contrário poderar encher a memoria e corromper a máquina.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/31d82866-0bec-47af-943e-d273e56c2c0b)

Aguarde o tempo que for nessesário para atualizar tudo, recomenda-se tirar um dia só pra deixar ele atualizando.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ec6528ad-d15a-43cb-a461-75ad9251e8e5)

> :warning: após atualizar o servidor reinicie!

# Configurações iniciais

## Configurando Nome

Agora com tudo beleza vamos em **Local Server**, aqui será onde vamos fazer as primeiras configurações.

Vamos inicialmente trocar o nome do servidor, para isso vamos clicar no nome do servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/eec62fe0-6881-4928-9635-50904022fbd0)

Depois clique em **Change**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6ac74677-7fc0-43f9-bb6e-0bc6f295ef7e)

Aqui você escolhe o nome do servidor, escolher um bom nome para servidor é importante pois ajuda a identifica-lo na rede, assim para uma boa escolha de nome você pode seguir essas caracteristicas, como ser **descritivo** (*Um nome que reflita a finalidade ou função do servidor*), **conciso** (*Mantenha o nome curto e objetivo*) e **consistente** (*Mantenha uma convenção de nomenclatura consistente em toda a infraestrutura*). 

No meu caso escolhi **SRVIFMAELVIS01** onde **SRV** significa Servidor, **IFMAELVIS** para dizer que é um servidor do ELVIS no IFMA e **01** para dizer que é o servidor numero 1, para caso exirem mais eles seram nomeados **02**, **03**.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/54a80cfe-9388-40ce-9b11-5b26315a8fdb)

Após isso clique em **OK**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9837d45f-9c6f-4884-a102-b8decf1e69e4)

Avisa que o computador precisa ser reiniciado para aplicar a alterações, aperte **OK**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/7072051b-ad47-42de-80e1-06479beca94c)

E por fim aperte em **Restart Now** para reiniciar o servidor
 
![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6623befa-025f-4bd8-8b6b-5901d78dcad1)

## Configurando hora

Agora vamos acertar a hora do servidor, apesar de não parecer importânte acertar a hora do servidor ela é de muita importância, pois todos os logs do sistema ficam registrado as horas isso afeta diretamente os registros de eventos e auditoria, e caso essas horas estejam erradas o servidor pode aprensentar erros de sincronização de eventos, além seus logs estaram todos com as horas erradas dificultando a resolução do problema, para que tais problemas não ocorra vamos arrumar a hora indo em **Time Zone**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1911bd1d-8434-4990-b328-3b6f88b55af2)

Clique em **Change Time Zone**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/bafca343-c29f-41a5-ad88-3f68f2d72f28)

Troque a zona para aonde seu servidor irá operar. no meu caso coloquei horário de Brasília e aperte **OK**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1e3b252c-4e3f-4e0d-aee3-ed0f6e557577)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b502e05e-26bf-4a88-bbbb-9b8229fdfbbc)

Agora vamos em **Internet Time**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c1e5f446-b398-4732-a83b-0eb1020a57b8)

Agora clique em **Changes settings**  

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4f6528f7-3b8f-45c6-850d-eb7dccb0b04c)

E aqui vamos trocar o servidor do **time.windows.com** pelo **time.nist.gov** é recomendado fazer isso pois ele é operado pelo Instituto Nacional de Padrões e Tecnologia dos Estados Unidos (**NIST**) e oferece um serviço de tempo altamente preciso além de terem varios servidores espalhados pelo mundo e pela confiabilidade pois o **NIST** é uma instituição respeitada e confiável em relação a padrões de medição e tempo.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/069e5d94-912f-46a2-81c0-a91af0855153)

Após isso aperte **Ok**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9d2cffe1-096d-498c-997f-3d348cfc268b)

Aperte **Ok** novamente para fechar a janela

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ce29df9f-35c7-4af4-bc58-6c382c9dc8a9)

## Configurando IP

Agora vamos configurar o IP para isso vamos em **Ethernet**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5d732d3f-86e0-430b-8805-d1c3421a53e4)

Clique com o botão direito do mouse encima da sua placa de rede que está usando e depois clique em **Properties**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c3fbfafe-b9f2-4a4f-8b5b-1b64a7609065)

Procure por **IPV4** e depois clique em **Properties** novamente

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b46bad2e-e31b-474d-8381-1e5081d22508)

Aqui selecione a 2º opção para colocar o ip manualmente, pois não queremos que o IP do servidor mude.

A configuração que fiz no meu foi a sequinte: 

```

IP address: 192.168.43.227
Subnet mask: 255.255.255.0
Default Geteway: 192.168.43.1

Preferred DNS server: 127.0.0.1
Alternate DNS server: 1.1.1.1

```

O DNS principal sendo ele mesmo é para que não tenhamos problemas futuramente e como servidor secundo coloquei o 1.1.1.1 que é o servidor DNS da Cloundflare. Após isso aperte **OK**

> :warning: O IP que você colocará em seu servidor será de acordo com a sua rede, no meu caso a minha rede é a **192.168.43.0/24** com o Gateway sendo o **192.168.43.1**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8eb52c19-86a1-4490-baa8-5d2fb33869ab)

Aparecerá essa janela e é só aperta em **Yes**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a334ed75-4558-43eb-a52b-6a0f7eb5256b)

Após isso temos nosso servidor pronto para recerber as primeiras funções e recursos.

> :warning: Sempre verifique se o Windows Defender, Windows Firewall e o IE Enhenced Security Configuration se estão ativos, além disso, verifique por novas atualizações e atualize seu servidor sempre!

> :warning: Nunca desative o Windows Defender e o Windows Firewall!

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/20cdfb80-f9d4-456c-9d78-493d79f32569)

# IIS e FTP

## Sobre

O IIS (*Internet Information Services*) é um servidor web feito pela Microsoft para Windows. Ele fornece uma plataforma robusta e escalável para hospedar e entregar sites, serviços web, aplicativos e outros conteúdos na Internet ou em uma rede local.

O FTP (*File Transfer Protocol*) é um protocolo de rede utilizado para transferir arquivos entre computadores pela rede. Ele permite a transferência eficiente de arquivos de um computador para outro, independentemente do sistema operacional em uso.

## Instalando

Vamos em **Manager** e clicamos em **Add rules and features** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c8166010-c855-4af5-a878-174b3ec266b6)

Aqui ele mostra algumas recomendações, como já fizemos tudo como recomendado vamos marcar **skip this page by default** para não aparecer novamente e apertar em **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b0b3055c-ca87-44a2-a00c-41f6266b32f9)

Como vamos instalar na nossa maquina local vamos apenas apertar **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f13af91a-d7b6-41e2-8937-48f4bb8959e9)

Aqui você escolhe em qual servidor quer instalar, porém como só tem o nosso vamos apertar **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8bbea500-b22e-40b3-8cb2-0978dbde3eae)

Nessa tela é onde é listado todas as funções disponíveis para seu servidor windows, se você observar cada uma dessas funções tem uma breve descrição, como vamos instalar o **ISS** vamos marcar ele

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c98e1bc3-99e5-4901-9821-ef7606036ff2)

Aqui pergunta se você quer adicionar os recursos nessesário para a função funcionar, vamos clicarem **Add features**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/93d49c23-49a9-4b8c-b035-14511d8fe9f9)

Aperte em **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9ef43b34-42c1-429f-afc3-333d231ff2ca)

Aqui pergunta se você quer adicionar alguma **features** no nosso caso não será nessesário, aperte em **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5cdf1083-c40b-49dd-9dde-172d056f9451)

Aqui é um pequeno resumo sobre o serviço e a instalação, aperte **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/279bf54f-3206-441a-86e7-b4f71a27123b)

Aqui é onde vamos escolher quais recursos vamos instalar junto com nossa função, marquei as funções que iremos utilizar, é só seleciona-las e aperte **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3aec99a5-6a75-4dbf-a7aa-e8bbf39d7274)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/46b1bde2-0152-4f00-9335-7f1ec50d1348)

Marque o **FTP** para ser instalado junto. Aperte **Next**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/bfb3285d-b117-493c-b975-0a694a38350a)

Agora ele mostra um resumo da sua instalação, mas antes vamos exportar nossa configuração, essa exportação é muito útil pois ela gera um relatório de tudo que foi instalado, isso é muito importante para auditoria do sistema

Para isso vamos clicar em **Export Configuration Settings** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/557fb052-a82b-4c0a-bffc-3aa8f7d8a56e)

Escolha a pasta ponha um nome para seu arquivo e clique em **Save**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/757c2ff7-7c3d-463e-9767-686526acfd46)

Agora é só apertar **Install**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/557fb052-a82b-4c0a-bffc-3aa8f7d8a56e)

Após ums instantes sua função estará instalada. Após isso aperte **Close**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1b57e2cf-fb15-48cf-b62c-a75251c3d72d)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5521b26c-1f88-453e-bf23-78d4990d4d3f)

Aqui podemos ver que a função já está funcionando, basta acessa o ip do seu servidor pelo navegador que aparecerá uma tela igual essa

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/95228eb2-5279-47ba-ad13-1ed989ef0f7e)

##  Configurações

Você pode acessar as configurações do serviço indo em **Tools** e depois procurar pelo nome do serviço que nesse caso está escrito **Internet Information Services (IIS) Manager**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a51dc52a-a076-4fea-91b9-e14f53b1204a)

Aqui vamos clicar no nome do nosso servidor que está na lateral esquerda para aparecer as configurações dele

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/32c72af1-1b43-4de2-8430-be861dd57bb2)

Aqui vemos todas as configurações que podemos fazer na nossa função, vemos no lado direito as opções de **restart**, **start** e **stop** da função 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5f202dcf-32dc-41ee-9a67-95af1f527652)

Clicando com o botão direito do mouse sobre o nome do nosso servidor vemos mais opções como, **Add site** e **Add FTP**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/cf9f4581-3964-41a6-a3f5-bc0cba2f2c4a)

Na categoria **ISS** clicando em **Default Document** podemos ver os documentos padrão do site

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4be61158-2ef7-4f55-be2d-83f7a5b6e129)

Aqui vemos onde fica a pasta onde o arquivo do site que é entregue pelo servidor fica que é em `C:/inetpub/wwwroot`

[Mostrando pasta onde fica o site.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5a2a5a84-f24a-498d-9bcb-2f6bb3a29aa4)

Na categoria **ISS** clicando em **Authentication** podemos ver as configurações de autenticação

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ff35f8e5-96fb-4843-b920-821ff808d468)

Podendo habilitar ou desabilitar caso queira clicando com o botão direito do mouse

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fc0b582b-67f2-4df2-a404-14fc644f3ab0)

Vamos adicionar um novo site, para isso vamos criar um site no servidor clicando com o botão direito do mouse encima do nome do servidor e depois em Add site.

> :warning: Nunca coloque uma porta já utilizada por outra função, caso contrario ira apresentar erro no seu servidor

[Criando novo site.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/00b17e05-2e43-4e55-9c39-7f70809bf145)

Aqui vamos criar o arquivo index.html para ser exibido no nosso novo site.

[criando index.html.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/35a56737-320d-4fe2-a89d-3577a0c0df70)

Aqui vamos liberar a porta 8080 como configuramos no nosso site no firewall para que máquinas externas possam acessar nosso site.

[liberando porta no firewall.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c822124a-8b20-4c5f-b1ea-6c236bec68e0)

Vemos que está tudo funcionando

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/28195c3e-4a70-457f-bfb0-5dc828e26525)

Caso queira modificar as páginas de erro você pode ir na categoria **ISS** clicando em **Error pages** você pode ver onde os arquivos estão ou trocar o arquivo.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/dac8dec9-1702-492a-9a6f-275be6e7be9c)

Agora vamos criar um certificado ssl auto assinado.

[Criando certificado auto assinado.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/538e1c7d-9030-4e0b-b936-b30166c5cb19)

Após criado o certificado agora vamos adicionalo em nosso site de teste

[Adicionando protocolo https no site de teste.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2aeb2208-0850-473c-8944-5c48879c3e82)

Essa tela aparece por conta de o certificado ser auto assinado, como ele não é autenticado eu nenhuma certificadora o navegador considera o site como perigoso, mas basta em **Advanced** e depois em **Accept the risk and continue**

![Captura de tela de 2023-05-27 21-32-39](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6e2eb8bd-a812-4172-93fc-6803c60b345e)

Aqui vemos nosso site funcionando com nosso certificado SSL

![Captura de tela de 2023-05-27 21-33-16](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/46ae1bcd-d157-4488-adf7-e0f52bdb04bb)

Em **IP address and domain restrictions** podemos adicionar ou remover restrições por ip ou domínio.

[Adicionando e removendo restrições por ip.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/606ba46e-9435-4cd1-abda-95c7b5bc1c9d)

# Samba

## sobre 

O Samba é também uma solução de compartilhamento de arquivos e também de impressoras, ele é amplamente utilizado em redes mistas com diferentes sistemas operacionais, oferecendo uma forma simples e segura de compartilhar recursos em uma rede local ou na internet.

## Instalando

Aqui vamos instalar a função, é só seguir os passos do video que será instalado o samba corretamente.

## Configurando

[Instalando função samba.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/200daf0b-adb3-4a15-9b63-017d84be659d)

Em tools e em **File Server Resouce Manager** vamos encontrar essa tela onde faremos todas as configurações necessárias

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/feaa4cf2-8695-4363-9e6a-9fa0920d67e5)

Em **Quotas Management** e em **Quatas** você pode adicionar limites de utilização de recursos da pasta como limitar a quantidade de MB que a pasta pode conter 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/60d3f4c7-deee-4d27-959f-17205b94c55f)

Em **Quatas Templates** você pode usar umas dessas configurações já prontas para usar em sua pasta compartilhada

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/75a42b9a-8bbd-48bc-8791-84097da3a2c5)


Em **File Screens Management** e **File Screens** você pode adicionar regras como aceitar somente um tipo de arquivo ou todos os tipos exceto um específico como **.exe**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/d2c63339-e86b-4c67-ad57-48c44505d978)

Em **File Screens Templates** você pode usar umas dessas configurações prontas, e caso queira criar sua própria configuração você pode clicar com o botao direito do mouse e depois em **Create File Screen Template** e criar sua configuração. 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f018b6db-169a-4459-839b-040c941ca7b7)

Agora em **Reports Storage Management** é onde configuramos os relatórios que nosso servidor irá gera sobre tudo que está acontecendo no servidor, é muito importante para auditoria caso haja algum problema. 

Algumas das configurações disponíveis:
> Configurar o local de armazenamento dos relatórios: Você pode especificar o local onde os relatórios serão armazenados. Pode ser um caminho local ou um caminho de rede compartilhado.

> Agendamento de relatórios: É possível configurar agendamentos para a geração automática de relatórios sobre o uso e as cotas de arquivos. Esses relatórios podem ser executados periodicamente conforme a configuração definida.

> Configurar notificações: É possível configurar notificações por email para alertar os administradores sobre eventos específicos relacionados ao uso e às cotas de arquivos. Por exemplo, você pode ser notificado quando uma cota de arquivo atingir um determinado limite.

> Personalização de relatórios: O Gerenciador de Recursos de Servidor de Arquivos oferece opções para personalizar os relatórios gerados. É possível selecionar os tipos de relatórios a serem gerados, especificar os dados a serem incluídos nos relatórios e personalizar o formato dos relatórios.

[Reports Tasks.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/587aef6c-cfb4-4812-85a1-6bdfe5862829)

E em **File Management Tasks** podemos ver todas as atividades que estão acontecendo agora, como não tem niguém usando meu servidor agora ele está vazio.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f8cc2ec8-20f1-42a2-a7b9-c7eae83daf23)

Agora vamos voltar para o gerenciador do servidor e em **File and Storage Service > Shares** vamos criar nossa pasta compartilhada. no meu já existe algumas pastas compartilhadas mas no seu estará vazio. Para iniciarmos o assistente clicamos com o botão direito do mouse e depois em **New shere**.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/72aa203a-6c75-4360-9433-96a9f71534d2)
  
Nessa parte vamos escolher **SMB Shere - Advanced** para termos acesso a todas as configurações.

![Captura de tela de 2023-06-17 18-34-33](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4e943812-1ae0-42c3-8b6f-d21c4017990a)

Nessa tela é onde vamos escolher qual pasta vamos compartilhar, vamos selecionar **Type a custom path** para selecionarmos uma pasta personalizada e logo após clicamos em **Browser**. 

![Captura de tela de 2023-06-17 18-35-10](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6ceeb839-2fed-4847-bdab-b44ed2e3365e)

Agora vou criar uma pasta na raiz do sistema com o nome **COMPARTILHAMENTO** clicado em **New Folder** e depois vamos clicar em **Select Folder** para selecionar a pasta. 

![Captura de tela de 2023-06-17 18-35-50](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a87f4d3d-a491-4b5d-a196-92792b20c717)

Agora é só apertar em **Next**

![Captura de tela de 2023-06-17 18-35-59](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/02ce2425-c637-40e9-805b-e08293e7f437)

Aqui não alteramos nada, se quiser pode colocar uma descrição para a pasta.

![Captura de tela de 2023-06-17 18-36-27](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f1a380fe-0462-4714-96ee-57c525b8df3f)

Aqui nessa parte temos as seguintes opções:

> Enable Access-based Enumeration (Habilitar Enumeração Baseada em Acesso): Essa opção permite controlar a visibilidade dos arquivos e pastas compartilhados com base nas permissões de acesso dos usuários. Quando habilitada, apenas os itens para os quais o usuário tem permissão serão visíveis ao navegar pelo compartilhamento.

> Allow caching of share (Permitir o cache do compartilhamento) permite que os arquivos do compartilhamento sejam armazenados em cache nos clientes que acessam o compartilhamento. O objetivo dessa opção é melhorar o desempenho e a velocidade de acesso aos arquivos, especialmente em cenários em que há muitos acessos aos mesmos arquivos repetidamente.

> Encrypt Data Access (Acesso de Dados Criptografado): Quando habilitada, essa opção aplica criptografia aos dados que estão sendo acessados no compartilhamento de pasta. Isso ajuda a proteger a confidencialidade dos dados durante a transmissão pela rede.

Iremos deixar todas essas opções ativas.

![Captura de tela de 2023-06-17 18-36-38](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/e6a5dd99-3bd4-4774-9cf7-e185911fb66c)

Aqui vamos personalizar as permissões de usuário, para isso vamos clicar em **Customize Permissions**.

![Captura de tela de 2023-06-17 18-36-45](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3a8d0307-0f2b-4c1d-a137-eb02c72766fa)

Na janela que acabou de abrir vamos apagar todas as permissões já predefinidas clicando em **Disable Inheritance** e depois em **Remove all inherited permissions from this object** para remover todas as permissões.

![Captura de tela de 2023-06-17 18-36-52](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/00689041-558a-4dc8-9b75-dd737e219d33)

Após removido vamos clicar em **Add > Select a principal > advanced**

![Captura de tela de 2023-06-17 18-37-19](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5cb2fa06-4735-4f33-bb25-eed9c0f67b50)

Agora vamos clicar em **Find Now** e depois selecionar o tipo de usuário.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/cafa66b6-849e-4b6b-805f-c8a2e9116014)

Após selecionar o tipo, vamos escolher as permissões que esse tipo de usuário terá. você pode fazer isso para quantos tipos quiser e até para usuários específicos.

![Captura de tela de 2023-06-17 18-38-08](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/81df4a6e-4f0f-4add-91cb-9c8f64fc617f)

Após adicionados as permissões vamos clicar em **OK**.

![Captura de tela de 2023-06-17 18-39-41](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c2e2a7de-a09c-4044-a2e4-c0721ae21e45)

Vamos para a proxima tela clicando em **Next**.

![Captura de tela de 2023-06-17 18-39-53](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a01ad918-b867-41cd-a6e9-a20c6866735f)

Aqui é só apertar **Next** novamente.

![Captura de tela de 2023-06-17 18-40-30](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c09ca58b-ad07-4f06-bf05-57c0e51bbd41)

Nessa tela podemos escolher as **quotas** caso você queira aplicar alguma do template é só selecionar e apertar **Next**. 

![Captura de tela de 2023-06-17 18-40-45](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f3a4986d-a281-4c79-b487-577a901fa383)

Aqui ele mostra um resumo das configurações. Agora é só apertar em **Create**.

![Captura de tela de 2023-06-17 18-40-53](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5beb6a21-d28c-41a8-a697-51abd2d249ca)

Aqui vemos que o compartilhamento foi criado com sucesso.

![Captura de tela de 2023-06-17 18-40-58](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0d8e90a2-2a18-40b5-bfc6-9e091dc21ff7)

Aqui podemos ver que nossa pasta está sendo compartilhada.

![Captura de tela de 2023-06-17 18-41-09](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3c1e9174-221f-4cd1-966e-6556a03b8e99)

# DHCP

## sobre 

O DHCP (Dynamic Host Configuration Protocol) é um protocolo de rede utilizado para fornecer configuração automatizada de endereços IP e outras informações de rede para dispositivos em uma rede. Ele simplifica a administração de redes, eliminando a necessidade de configurar manualmente cada dispositivo individualmente.

## Instalando

Instalando DHCP, após finalizar a instalação não feche pois tem uma pequena configuração que é muito importante.

[Instalando DHCP1.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3ccdc85d-1a82-4d00-b62c-03638b3d0b0c)

Após instalar clique em **Complete DHCP configuration** para finalizarmos a configuração, caso não seja configurado nessa etapa pode não funcionar corretamente o seu serviço de DHCP. Após finalizar é só fechar.

[Instalando DHCP2.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c6c98198-3d70-4f84-88ee-c24e04979f3b)

## Configurando

Em **Tools > DHCP** vamos chegar nessa tela onde faremos nossas configurações de **DHCP**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/102afd7f-a765-4456-8c07-fa3cd51a378a)

Clicando com o botão direito do mouse encima de **IPV4** vamos clicar na opção **New Scope** para configurarmos nosso serviço.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/24190395-6e81-4963-9f82-d84051da8fb1)

Aqui nessa tela vamos definir o nome da nossa configuração e a sua descrição 

![Captura de tela de 2023-06-17 21-27-19](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4aaa1bde-5103-419e-8792-0386bbbee552)

Nessa tela vamos definir a faixa de IP que o **DHCP** irá entregar para as máquinas, no meu caso eu coloquei a faixa de 20 a 254, logo abaixo vamos configurar a mascara de rede que no meu caso coloquei no tamanho **24** e com submascara de **255.255.255.0**

![Captura de tela de 2023-06-17 21-28-43](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f75a1aca-1da1-46eb-b340-51eb8021c47a)

Nessa parte é onde você configura uma faixa a qual deseja excluir, essa configuração é para caso você deseja excluir uma faixa de IP que fique entre a faixa que colocou anteriormente, como não é o nosso caso vamos passar para a próxima configuração.

![Captura de tela de 2023-06-17 21-29-06](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/7c40fe96-5b70-4175-92d0-cfbb65fc9929)

Aqui vamos configurar o tempo que uma máquina permanece com o mesmo IP que é um aspecto importante do DHCP que determina por quanto tempo um dispositivo pode usar um endereço IP atribuído pelo servidor DHCP antes de renovar a solicitação.

Esse tempo é importante pois há ambientes com alta rotatividade de disposivos como shoppings que caso esse tempo seja muito alto, logo logo os IPs disponíveis acabariam fazendo com que novos dispotivos não consigam se conectar na rede. 

Você já tentou se conectar em alguma redes dessas e recebeu a mensagem *"Não foi possível obter endereço IP"* isso acontece devido a esse problema, e para evitar isso devemos configurar esse tempo de forma condizente ao ambiente em que esse servidor funcionará.

No nosso caso coloquei o tempo de 1 dia para renovar os IPs das máquinas.

![Captura de tela de 2023-06-17 21-29-24](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/71f00279-61af-4cbc-bd2f-304f9ffb5855)

Agora é apertar em **Next**

![Captura de tela de 2023-06-17 21-30-01](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/61941243-2877-4ebe-8ed4-b71724c2f608)

Aqui é onde definimos quem será o Geteway que as maquinas irão receber, no meu caso eu coloquei para o Gateway ser o próprio servidor.

![Captura de tela de 2023-06-17 21-30-51](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/e5fb7a7c-8a18-49bf-929f-e8ca105fb1d2)

Aqui é onde definimos os servidores DNS que as máquinas iram receber no meu caso coloquei para que o principal servidor seja o meu servidor e o segundo sendo o **1.1.1.3** 

![Captura de tela de 2023-06-17 21-31-45](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/09b1b5de-5f0d-443c-badd-f6cd1a83264a)

Aqui é só apertar **Next**.

![Captura de tela de 2023-06-17 21-32-15](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/96f71f95-bdd8-461b-9136-99e64e2742c9)

E **Next** novamente. 

![Captura de tela de 2023-06-17 21-32-20](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c9c4b85a-67ca-4b7b-b325-181f0f7b8850)

Agora é só apertar **Finish**

![Captura de tela de 2023-06-17 21-32-25](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2f60c4f4-f2be-4e1c-ae0c-d9ec5b78511d)

Aqui podemos ver nossa configuração criada

![Captura de tela de 2023-06-17 21-32-35](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ff28cf73-8241-45d1-8f45-03a10383fdd2)

Indo em nossa configuração vemos a pasta **Reservation**, clicando com o botão direito do mouse e depois em **New Reservation** podemos criar IPs reservados para máquinas especificas, como por exemplo uma impressora. 

![Captura de tela de 2023-06-17 21-38-29](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5745ea62-2481-46b1-b196-b4096a9194a1)

Aqui podemos ver nossa reserva criada.

![Captura de tela de 2023-06-17 21-38-48](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ac992632-0c0d-49f1-8437-f6c7b7100c68)

Clicando com o botão direito do mouse encima de **IPV4** vamos clicar na opção **Reconcile All Scope** depois em **Verify**, para verificarmos se nossa configuração está Ok, como podemos ver aqui está Ok. 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/df43aabd-50ef-4d32-869b-800dc639c130)

Clicando com o botão direito do mouse encima de **IPV4** vamos clicar na opção **Properties** e ativar a opção de atualizar as estatisticas e vamos definir para atualizar acada 8 horas.

![Captura de tela de 2023-06-17 22-21-18](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/cdb06e72-653d-401f-aa8e-5e671d23b0ed)

Clicando com o botão direito do mouse encima de **IPV4** vamos clicar na opção **Display statistcs** para vermos as estatisticas do nosso DHCP.

![Captura de tela de 2023-06-17 22-21-34](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c18ad142-3cf5-4f10-87aa-c1c663d601de)

# Servidor de Impressão

## Sobre 

O Print and Document Services (Serviços de Impressão e Documentos) é um conjunto de recursos e serviços que permitem a administração centralizada de impressoras, gerenciamento de filas de impressão e compartilhamento de documentos. Ele fornece uma infraestrutura para configurar, gerenciar e monitorar impressoras e documentos em uma rede.

## Instalando

Essa primeira parte você já deve está acostumado a mexer então citarei somente os passos existentes.

Passo 1

![Captura de tela de 2023-06-01 17-28-04](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/caf7d346-d8aa-4fca-8edd-a39bbdbc9a9c)

Passo 2

![Captura de tela de 2023-06-01 17-28-14](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8cbdd1c3-9736-44de-998f-b3ff251f42ec)

Passo 3

![Captura de tela de 2023-06-01 17-28-37](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/e3cd5678-dad8-413c-a9a5-53a4dff757f0)

Passo 4

![Captura de tela de 2023-06-01 17-39-55](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fcd769c5-bfe4-4b9c-ad48-deffefbc35af)

Passo 5

![Captura de tela de 2023-06-01 17-40-01](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f83a5dba-f2bf-461a-9307-368ee62bb8dc)

Passo 6

![Captura de tela de 2023-06-01 17-41-13](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5c279f64-ab1f-4618-9420-a603d937c8b9)

Passo 7

![Captura de tela de 2023-06-01 17-41-30](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/acd5ade9-7544-4bce-99f1-c4c8c5811af3)

Passo 8

![Captura de tela de 2023-06-01 17-41-39](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0e9e77ab-2524-4765-baf5-2da21e8392ad)

Passo 9

![Captura de tela de 2023-06-01 17-42-20](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a12342d1-f269-4698-acdd-b71c07d6914f)

Passo 10

![Captura de tela de 2023-06-01 17-44-03](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2b29a4b7-e14f-41ef-a1d7-2578fd260476)

## Configurando

Para abrirmos a janela de configuração dessa função vamos em **Tools** depois em **Print Management**

![Captura de tela de 2023-06-01 17-44-55](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4078e08d-eb68-4b31-b3f2-3a1e434a3e4a)

Essa é a janela onde configuramos todos os detalhes dessa função 

![Captura de tela de 2023-06-01 17-45-12](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/073fe9b0-bfcf-4c61-8093-5cad99989ffc)

Em **Print Servers** é onde ficam todos os servidores de impressão dentro dele tem as pastas **Drivers** que guarda todos drivers das impressoras, o **Forms** que guada todas as formas de papel que podem ser impressas, as **Ports** que guarda todas as portas de cada impressora, e a **Prints** que guarda todas as impressoras.

![Captura de tela de 2023-06-01 17-46-12](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c7026a0d-2c92-4826-8009-fabeee6bcea4)

Agora vamos adicionar uma porta padrão para as impressoras vamos clicar com o botão direito encima do servidor e logo após cliacar em **Properties** 

![Captura de tela de 2023-06-01 17-46-52](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/57b38020-cd58-43d4-9edb-5aff134129b5)

Vamos na aba **Ports** e vamos clicar em **Add Port** depois em **Standard TCP/IP** e em **New Port**

![Captura de tela de 2023-06-01 17-47-59](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2c768ce2-8f64-4b1f-afc3-0075da3b63c8)

Aqui você coloca o IP da impressora e a porta.

![Captura de tela de 2023-06-01 17-48-31](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/acc01a3b-72f9-46c6-b201-4aaa419228a1)

Aqui é só apertar **Next**.

![Captura de tela de 2023-06-01 17-49-34](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/057d5077-3ef3-45bc-9b4c-2df1b392ff89)

Agora é só apertar em **Finish**

![Captura de tela de 2023-06-01 17-49-46](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/438e67b7-5062-4e1b-ad40-1ba5d5edd58f)

Aqui podemos ver nossa porta adicionada

![Captura de tela de 2023-06-01 17-49-54](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b9acfa43-470d-4e41-bb20-1563f6970e3c)

Agora vamos adicionar um drive para uma nova impressora, basta vim na aba **Drivers** e depois em **Add**

![Captura de tela de 2023-06-01 17-50-03](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/15fd398e-8569-462e-94fd-65e449a05c84)

Aqui é só apertar **Next**

![Captura de tela de 2023-06-01 17-50-09](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/20344a74-e00f-4465-a85e-48008db28c1c)

Aqui é só escolher se é 32 ou 64 bits, no meu meu caso é 64.

![Captura de tela de 2023-06-01 17-50-13](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0779d806-f934-4cef-a34f-b1226222a198)

Aqui você pode escolher o driver para instalar, já vem com varios drivers, escolhi um que já vem com o servidor para instalar. 

![Captura de tela de 2023-06-01 17-50-18](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/de63b149-f865-4d0b-ad4b-9429d48daef9)

Após isso é só clicar em **Finish** e temos nosso driver da impressora instalado

![Captura de tela de 2023-06-01 17-50-26](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fb2a55e3-910f-4b34-bd93-47b0d7643aed)

Aqui podemos ver o driver que acabamos de adicionar

![Captura de tela de 2023-06-01 17-50-32](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/53481ddd-76f1-462d-8497-69e3cd982809)

Podemos ver a página web, que fica em `127.0.0.1/printers/`, que a função fornece para vermos se está funcionando, porém não temos nenhuma impressora instalada ainda por isso está vazio.

![Captura de tela de 2023-06-01 17-59-12](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/147f6a87-d9e6-4555-87d3-1b8a0c2be9f5)

Agora vamos adiocionar uma impressora vamos clicar com o botão direito do mouse encima de **Printers** e depois em Add **Printer** 

![Captura de tela de 2023-06-01 18-14-03](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/99c2963c-9d58-45d6-a085-e06f809df194)

Vamos clicar em **Add a new printer using an existing port** para adicionar uma impressora em uma porta existente.

![Captura de tela de 2023-06-01 18-15-44](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b04edcd3-fdd6-48d8-b7da-97f13a416d5f)

Vamos clicar em **Install a New Driver** para instalar um novo drive para essa impressora

![Captura de tela de 2023-06-01 18-15-49](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/37f504ca-315e-45ce-8840-102d0e4180a1)

Podemos escolher o Driver pela mesma tela que vimos anteriormente

![Captura de tela de 2023-06-01 18-15-59](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/bb4b5fa1-3768-4673-98ce-4f3a92d6cc87)

Aqui você pode escolher um nome para a impressora para melhor indentifica-la

![Captura de tela de 2023-06-01 18-16-34](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/e0fdfda5-bb68-49a4-beb5-875b3c3b5253)

Após isso é só clicar em **Finish**

![Captura de tela de 2023-06-01 18-16-41](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9d55c7ef-eb52-4ff3-966e-f65c4a392120)

Agora podemos voltar a página web das impressoras e ver ela adicionada lá

![Captura de tela de 2023-06-01 18-17-05](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0053224e-d987-4700-acea-3cf1118f2b7c)

Clicando nela temos mais detalhes, aqui podemos ver todas as impressoras, pausar, resumir, cancelar a impressão de todos os documentos tanto para o documento quanto para a impressora.

![Captura de tela de 2023-06-01 18-17-20](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2e0c3537-144e-447f-bca3-61797f78aa69)

Indo em **Properties** podemos ver mais detalhes sobre a impressora 

![Captura de tela de 2023-06-01 18-17-26](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2c509d15-d678-4235-900e-bc8e4e70cafb)

# Active Directory

## Sobre

O Active Directory é um serviço de diretório desenvolvido pela Microsoft e é uma das principais ferramentas de gerenciamento de rede em ambientes baseados no sistema operacional Windows Server. Ele fornece uma estrutura centralizada para armazenar, organizar e gerenciar informações sobre usuários, computadores, grupos e outros objetos de rede em um domínio.

Alguns pontos sobre o Active Directory:

> Diretório Hierárquico: O Active Directory é baseado em uma estrutura hierárquica de objetos. O objeto principal é o domínio, que é uma unidade lógica de gerenciamento de rede. Vários domínios podem ser agrupados em uma floresta, que é uma coleção de domínios conectados.

> Autenticação e Autorização: O Active Directory é responsável pela autenticação e autorização dos usuários em um domínio. Ele verifica as credenciais dos usuários durante o processo de login e concede ou nega acesso com base nas permissões definidas.

> Gerenciamento de Políticas: O Active Directory permite que os administradores definam e gerenciem políticas de segurança, políticas de grupo e configurações de diretiva em toda a rede. Isso ajuda a garantir consistência e conformidade nas configurações dos computadores e usuários.

> Serviços de Nomes: O Active Directory fornece serviços de nomes, como o sistema de nomes DNS (Domain Name System), que permite a resolução de nomes de domínio em endereços IP e vice-versa.

> Replicação de Dados: O Active Directory oferece recursos de replicação, o que significa que as informações de diretório são replicadas em vários controladores de domínio em uma rede. Isso garante a disponibilidade e a redundância dos dados.

> Gerenciamento Centralizado: Com o Active Directory, é possível gerenciar centralmente usuários, grupos, computadores e outros objetos de rede. Isso simplifica as tarefas administrativas, permitindo o gerenciamento eficiente de grandes redes.

> Integração com outros Serviços Microsoft: O Active Directory é amplamente integrado com outros serviços e produtos da Microsoft, como Exchange Server, SharePoint e muitos outros. Isso permite a sincronização de informações e a colaboração entre diferentes aplicativos e serviços.

Essa é uma ferramenta da Microsoft que é bastante útil em ambientes corporativos por essa gama de possibilidades e funções.

## Instalando

Essa primeira parte você já deve está acostumado a mexer então citarei somente os passos existentes.

Passo 1

![Captura de tela de 2023-06-05 23-12-01](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c48d7059-671f-48b6-aa23-478b9215cdcf)

Passo 2

![Captura de tela de 2023-06-05 23-11-53](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3ac392bf-067d-4b15-b34f-08fc0297325f)

Passo 3

![Captura de tela de 2023-06-05 23-12-06](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f89d10d2-3658-470d-9347-a425c1849f69)

Passo 4

![Captura de tela de 2023-06-05 23-12-11](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4e1a44a7-dba5-4359-97fe-749db8dd8f1c)

Passo 5

![Captura de tela de 2023-06-05 23-12-18](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/07f310d1-3f4f-4920-8d1d-67aaec01637f)

Passo 6

![Captura de tela de 2023-06-05 23-12-24](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/319fb533-2813-474f-8dfa-0e4db7b81d37)

Após instalado vamos clicar em **Promote this server a domain controller** caso não clique nessa configuração a função instalada não irá funcionar corretamente. 

![Captura de tela de 2023-06-05 23-12-51](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6ca05992-80fd-44d2-91f6-1c301750552e)

Caso tenha fechado a janela sem querer pode clicar na bandeirinha no canto superior direito que aparecerá a opção para você clicar.

![Captura de tela de 2023-06-05 23-13-11](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/230d62a0-426c-490a-a315-edac259bd7cf)

Aqui vamos selecionar a opção **Add a new forest** logo abaixo é só escolher o nome do domínio que irá usar, no meu caso escolhi IFMA.ELVIS

![Captura de tela de 2023-06-05 23-13-58](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f2d53067-b0a0-4e65-bf42-d4891988b45b)

Em **Forest functional level** é reconmendado sempre deixar uma versão anterior do servidor para maior compatibilidade com os computadores que iram se conectar a ele, ja em **Domain functional level** vamos deixar a versão atual do nosso servidor, logo abeixo vamos marcar a opção do servidor de DNS e depois vamos criar a nossa senha de administrador.

> :warning: Crie uma senha com letras maiúsculas e minúsculas, numeros e caracteres especiais! para maior segurança.

![Captura de tela de 2023-06-05 23-17-56](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/5801e5fd-0bb1-4419-aa81-1cf557213178)

Aqui é só apertar **Next**

![Captura de tela de 2023-06-05 23-18-05](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4274e3dd-fcee-48f6-9e4d-70e69919af46)

Aqui você escolhe o nome da NetBios do servidor

![Captura de tela de 2023-06-05 23-18-27](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/429111fb-f931-4f2f-b785-983bc24a3681)

Aqui vamos apertar em **Next**

![Captura de tela de 2023-06-05 23-18-42](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2d45de0f-47de-4ed6-8103-0277f5be7c70)

Aqui mostra um resumo das configurações que fizemos, vamos apertar em **Next**

![Captura de tela de 2023-06-05 23-19-09](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/301bfd66-2e60-4c5e-8da4-f6a87cf75017)

Aqui ele irá fazer uma análize no computador se está tudo OK esses avisos em amarelo são normais de acontecer, porém caso tenha algum aviso vermelho é por que tem algum problema crítico em seu servidor, nesse caso você teria que resolver o problema antes de continuar, ai é só apertar em **Install**.

![Captura de tela de 2023-06-05 23-19-28](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/2e2c3aff-f154-4254-a08b-8018dd507b21)

Após a instalação ser concluida seu computador deverá ser reiniciado.

![Captura de tela de 2023-06-05 23-20-11](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ddaf1221-ea36-474c-9f9b-dcdda91c885b)

![Captura de tela de 2023-06-05 23-20-24](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/89ac03af-8bce-40eb-a1be-6ddb0aff5ed1)

![Captura de tela de 2023-06-05 23-21-46](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/4c53943c-3573-4f3e-848e-80ab0370072f)

Após ligar novamente vemos que a tela inicial mudou, e agora para você poder acessar o servidor deverá usar a nova senha criada anteriormente.

![Captura de tela de 2023-06-05 23-29-03](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b0dc3d91-80c4-486c-8862-519c9bff4daa)

## Configurando 

Para iniciarmos nossa configuração vamos em **Tools** depois em **DNS**.

![Captura de tela de 2023-06-05 23-29-59](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6805bda0-1ced-43cd-b0b5-9f8dbf26908b)

Aqui nessa tela você pode configurar seu DNS e ver as configurações pre definidas

![Captura de tela de 2023-06-05 23-30-28](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8c500a5a-5a2f-4567-b4ea-822ef754322b)

Caso você queira criar uma nova configuração de DNS você pode clicar com o botão direito do mouse encima do nome de dominio que escolheu e aparecerá varias configurações como **New Host** e **New Alias**

![Captura de tela de 2023-06-05 23-30-43](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9fd35463-bccf-43fd-ad33-69426337540f)

Clicando em **New Host** temos essa janela que você pode adicionar seus host aqui, essa configuração é bastante útil caso queira que um determinado site não seja acessado, bastando colocar o ip que leve para sua propria página, por exemplo se a pessoa entrar em youtube.com ela cairia no site da empresa ao invés do youtube original.

![Captura de tela de 2023-06-05 23-31-54](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f9d82c7b-e021-4a30-b2ce-b7fbe8e70c4e)

Agora vamos em **tools** depois em **Active Directory Users and Computers** 

![Captura de tela de 2023-06-05 23-29-59](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6805bda0-1ced-43cd-b0b5-9f8dbf26908b)

Nessa janela é onde vamos fazer toda a configuração de políticas de grupos do windows. Podemos ver na pasta **Users** varios usuários, porém não criaremos nossos usuários nessa pasta pois ficaria muito bagunçado.

![Captura de tela de 2023-06-05 23-32-51](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/755c17f9-6ad7-4fda-b2af-3a524017063f)

Para resolver isso iremos encima de **IFMA.ELVIS** vamos clicar com o botão direito do mouse após vamos clicar em **New** depois em **Organizational Unit** para criarmos uma unidade organizacional como por exemplo um setor da empresa  

![Captura de tela de 2023-06-05 23-33-33](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/72df926b-61bb-43a2-91d4-bd2dc3d19af5)

Aqui coloquei o nome da unidade de alunos, onde ficará separado todos os alunos, por exemplo se fosse uma escola. Também criei uma unidade para professores.

![Captura de tela de 2023-06-05 23-34-05](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a2e5c041-be6a-4f08-b18a-13658ba6a055)

Agora clicando encima da Unidade dos professores com o botão direito do mouse depois em **User** vamos criar um novo usuário.

![Captura de tela de 2023-06-05 23-34-15](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/85826b34-5cfd-4a56-b1cf-3a8d1e223cc4)

Nessa tela não tem muito segredo, você coloca o nome e sobrenome depois o usuário de login, esse nome deve ser unico e caso apareça pessoas com o mesmo nome você pode usar varias estratégias para contorna isso, como inverter o nome e sobrenome ou usar o segundo sobrenome da pessoa.

![Captura de tela de 2023-06-05 23-35-05](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a5190f75-9729-4cc1-8a48-b1afdd29e847)

Aqui nessa tela você coloca a senha do usuário, essa senha deve ser uma senha padrão para todo usuário novo, pois marcaremos a opção **User must change password at next logon** que é para o usuário ser obrigado a trocar a senha no próximo login e peça para ele criar uma senha que somente ele saiba, para maior segurança da empresa, e também pois cada usuário é responsável por sua conta pois tudo que ele fizer ficará resgistrado em seu nome.

> :warning: Lembre que a senha deve conter os requisitos minimos de segurança que é letras maiúsculas, minúsculas e numeros! 

![Captura de tela de 2023-06-05 23-35-28](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/3d8cdd90-c2cd-40b5-9861-54311b59215c)

Agora nessa tela é só finalizar clicando em **Finish**

![Captura de tela de 2023-06-05 23-36-28](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/edf70520-0524-47f2-9a66-3c92308090b5)

Após criado podemos clicar com o botão direito encima do usuário e depois em **Properties**

![Captura de tela de 2023-06-05 23-39-37](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1b058e62-472d-43f4-aa8b-25d6d9606470)

Aqui vemos todas as propriedades do usuário como:

> **Account:** inclui informações sobre o nome de usuário, senha, status da conta (ativa ou desativada) e opções de bloqueio de conta.

> **General:** fornece detalhes gerais sobre o usuário, como nome completo, nome de usuário, descrição e foto.

> **Address:** contém informações de endereço, como endereço de rua, cidade, estado, CEP, país e outras informações de contato.

> **Telephones:** inclui números de telefone, como telefone residencial, telefone comercial, celular e fax.

> **Organization:** fornece detalhes sobre a organização à qual o usuário pertence, incluindo nome da empresa, departamento, cargo e gerente.

> **Account:** contém configurações adicionais relacionadas à conta do usuário, como a exigência de alteração de senha no próximo logon, senha nunca expira, usuário não pode alterar a senha, etc.

>**Profile:** inclui informações de perfil do usuário, como pasta inicial, caminho do script de logon, unidade de mapeamento, configurações de diretiva de grupo, entre outros.

> **Member Of:** mostra os grupos dos quais o usuário é membro.

![Captura de tela de 2023-06-05 23-39-43](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/963c4e17-a79c-449a-bc05-367ffbb2ee70)

Em **Member Of** vamos confiurar as permições do nosso usuário, nesse caso criei mais um usuário para ser o administrador do servidor. Para isso vamos em **Add**

![Captura de tela de 2023-06-06 16-27-40](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8e972233-d069-4dd8-8f19-73bc27f7555f)

Depois em **Advanced**

![Captura de tela de 2023-06-06 16-35-13](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/25d808c7-5efe-4c16-81dd-cd03092325e4)

Depois vamos clicar em **Find Now** para listar todos os tipos de usuários, depois disso é só ir selecionando quais permições quer dar a esse usuário.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/12e1841f-151d-41f6-95c2-d81f0952b90a)

No meu caso escolhi essas permições pois esse usuário será o administrador, antes de fechar clique em **set primary group** para definir esse usuário como administrator de dominio, caso contrário ele não terá acesso a algumas configurações. Dessa maneira temos nosso usuário configurado.

![Captura de tela de 2023-06-06 16-36-21](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6b9e9812-a5ab-41cf-b673-fd7b1a618086)

Agora vamos em **Tools** depois em Group **Group Policy Management** para configurarmos as políticas de grupos. 

![Captura de tela de 2023-06-06 16-38-02](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/55cd47bf-44b1-4acd-81e0-5447b8492249)

Essa é a janela onde vamos fazer as configurações

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f6a5f2bb-f085-4580-8ff4-c5fae4566c59)

Em **Domains > IFMA.ELVIS > Default Domain Policy** vamos clicar com o botão direito do mouse e logo após em **Edit** para editarmos as configurações padrão do nosso domínio.

![Captura de tela de 2023-06-06 16-40-55](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/383c1b54-6617-41da-8d88-f5ee813404ff)

Aqui temos duas categorias principais que são as **Computer Configuration** e as **User Configuration** as configurações de computador elas são aplicadas para as máquinas em si, independentemente do usuário que fazer login na máquina a regra será aplicado para todos, já nas configurações de usuário, essas são aplicadas ao usuário podendo cada usuário ter regras diferentes mesmo usando o mesmo computador por exemplo.

Existem muitas mas muitas configurações, podendo você deixar somente um programa disponivel para o usuário utilizar até criar configurações extremamente personalizada para cada usuário ou grupo de usuários. Dito isso vou mostrar algumas configurações que você pode criar aqui.

![Captura de tela de 2023-06-06 16-42-05](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/46906208-0b82-4008-aea4-6601df273e99)

Em **Computer Configuration > Windows Settings > Security Settings > Acount Policy > Password Policy** Temos algumas configurações de controle de senha, sendo: 

> **Enforce password history:** Determina o número de senhas anteriores que devem ser lembradas e impede que os usuários escolham uma senha que já foi usada recentemente.

> **Maximum password age:** Define a duração máxima de uma senha antes que o sistema exija que o usuário a altere.

> **Minimum password age:** Define a duração mínima que uma senha deve ser mantida antes que o usuário possa alterá-la novamente.

> **Minimum password length:** Especifica o número mínimo de caracteres necessários para uma senha.

> **Password must meet complexity requirements:** Exige que as senhas atendam a requisitos de complexidade, como a inclusão de letras maiúsculas, letras minúsculas, números e caracteres especiais.

> **Store passwords using reversible encryption:** Determina se as senhas são armazenadas usando criptografia reversível. É recomendável manter essa configuração desabilitada por motivos de segurança.

![Captura de tela de 2023-06-06 16-48-54](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b2d72199-70a8-42fa-a918-c956a3976f57)

Em **Password must meet complexity requirements** vamos desabilitar por exemplo, nesse caso a senha que o usuário tem que criar não precisa ter requisitos de complexibilidade podendo assim ele criar uma senha que contenha somente letras ou somente numeros

![Captura de tela de 2023-06-06 16-50-54](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fee51e8b-bc9a-414f-bcd4-c9cc12302b49)

![Captura de tela de 2023-06-06 16-51-01](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/186eef6b-4cdc-4c13-9509-93670fd06b1b)

Agora em **Minimum password length**

![Captura de tela de 2023-06-06 16-51-14](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/feeb7ea6-3c1a-4eb4-b5ea-8e06b1934c09)

Vou definir que o tamanho minimo da senha seja de 4 digitos, não é recomendado mas aqui é só um exemplo

![Captura de tela de 2023-06-06 16-51-20](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/8d425707-b631-47e6-aecc-694dd5368b91)

Após essa simples configuração vamos criar uma configuração específica para o grupo de usuários Alunos, para isso vamos clicar com o botão direito do mouse encima da pasta Alunos e depois clicar em **Create a GPO in this domain, and Link it here**

![Captura de tela de 2023-06-11 10-49-01](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1e55b5ba-f827-42e5-96c6-024403293e8a)

Vamos definir o nome da nossa configuração

![Captura de tela de 2023-06-11 10-49-18](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/295cf656-4ef9-4b21-a319-dfd637a3dd71)

E pronto, agora vamos clicar com o botão direito do mouse encima da nossa configuração recém criada para podermos editar clicando em **Edit**

![Captura de tela de 2023-06-11 10-49-24](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/eb43f797-9dcf-488e-be6d-e5202c425e7e)

Indo em **Computer Configuration > Policies > Windows Settings > Security Settings > Local Policies > Security Options** encontramos varias configurações e dentre elas a **Interactive Logon: Message text for users attempting to log on** ou melhor dizendo Logon interativo: Texto da mensagem para usuários que tentam fazer logon. Essa configuração permite que você defina uma mensagem personalizada que será exibida aos usuários quando eles tentarem fazer login no sistema

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/1ecffbcf-914f-4475-a1ce-aa532c5f79b0)

Aqui é só marcar a caixinha e escrever o texto que deseje que apareça.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/67ef0144-0243-4a33-9ad6-43d683df65bf)

também podemos colocar um título a essa mensagem em **Interactive Logon: Message title for users attempting to log on**

![Captura de tela de 2023-06-19 16-02-20](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/78f70d54-c2d3-44e9-b898-31b2b2ebf518)

Aqui podemos ver nossas configurações criadas

![Captura de tela de 2023-06-19 16-02-25](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ba5a5030-eec7-4493-94c6-7600c42809a2)

Aqui está um teste dessa pequena configuração que fizemos funcionando

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/72e62cf0-5410-4263-9f75-1e2db358b86f)

Aqui temos mais uma configuração de exemplo que é para definir um papel de parece para os usuários, para chegar nela você vai em **User Configuration > Policies > Administrative Templates > Desktop > Desktop** depois você clica em **Desktop Wallpaper** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c84c39a5-514e-4ee2-8a19-2ef5acbc541b)

Aqui você clica em **Enable** para habilitar escolhe o caminho da imagem, podendo passar um caminho remoto, e o estilo em que a imagem ficará por exemplo ao centro.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/f0681c24-1d4d-4a98-9b6f-72e206129cf9)

Esses foram apenas algums exemplos desssa configuração, e com ela termino essa trajetória, espero que tenha gostado e caso queira ver meus projetos que fiz ou estou participando no momento é só acessar [Elvis Rodrigues Almeida](https://github.com/Elvis-Almeida)
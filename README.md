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

[Instalando função samba.webm](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/200daf0b-adb3-4a15-9b63-017d84be659d)


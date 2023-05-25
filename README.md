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

Essa parte irei colocar **30GB** de disco para ser usado pela maquina vitual, e conforme o espaço que você tiver disponível pode colocar mais ou menos, porém não deixe menos que **25GB** pois pode não ser sufuciente. Após isso é só clicar em  **Próximo**

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

> :warning: A senha necessita ter letras **maiúsculas**, **minúsculas** e **números**!

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/0ac3c16a-cc88-4250-955a-994fd4f671ed)

Agora podemos entrar no nosso servidor, para aparecer a tela de senha basta precionar **Ctrl + Alt + Delete**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/6f8b4885-6339-4f89-bc28-16ed1adea6f2)

Caso você tenha o mesmo problema que eu tive que mesmo precionando as teclas não funcionava você pode usar um teclado virtual para precionar esse botões, é só ir em **Entrada** depois **Teclado** e depois em **Teclado de Tela**.

![gif](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/56359612-4a4c-431f-a403-f63a2422f028)

# Visão Geral

Após instalar nosso servidor temos essa tela inicial

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/dc483aa5-e564-4af8-8bc9-41b2598e0230)

Agora vamos abrir o programa **Server Manager** (*que é o uma ferramenta de gerenciamento do servidor feito para facilitar a administração e o monitoramento*), caso esse programa já não tenha aberto automaticamente.

> :warnig: Para abrir qual quer programa que eu mensionar você pode ir na lupa na barra inferior e logo após escrever o nome do programa.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/31627595-3f8e-4ffb-8a62-24f35e1290d4)

Essa é a pricipal tela que vamos usar durante toda nossa jornada onde temos no lado esquerdo temos **Dashboad**, **Local Server**, **All Servers** e o **File and Storage Services** que são:

- Em **Dashboad** você pode ver o status geral do seu servidor de forma resumida.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/149672ab-9e6a-432b-a3cd-915bc5c5b66c)

- No **Local Server** é onde vemos todas as informações do servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/eec62fe0-6881-4928-9635-50904022fbd0)

- Em **All Servers** ira mostrar todos os servidores conectados (*sim, é possível gerenciar um servidor apartir do outro*)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9705a177-73f9-41b0-86b7-a55cf87dab79)

- E em **File and Storage Services** é o serviço de compartilhamento de arquivo que já vem instalado no servidor, porém não é recomendado usar ele com a configuração que veio, vamos ajustar isso mais afrente. 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/b3753a59-14e0-42fc-9f02-c2b12f73dc8a)

No canto superior direito temos as opções **Maneger** e **Tools** onde:

O **Maneger** é onde podemos adicionar ou remover funções e recursos, adicionar servidores, criar grupos de servidores e gerenciar as propriedades do servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/78173dc3-afbf-4b67-bc0c-f43f2c5139d7)

O **Tools**  é onde fica as configurações de todas as funções adicionadas no servidor.

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/41532634-296e-431d-86ad-eb31beeb5e95)

# Configurações iniciais 


a



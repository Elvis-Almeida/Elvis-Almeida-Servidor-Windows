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

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fc557443-4024-4188-8260-5379908f9401)


## Criando máquina virtual 

Agora que já temos o `.iso` vamos criar nossa maquina virtual, basta abrir o **VirtualBox** e clicar em **Novo** 

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/d53f3d10-30a5-4991-a4c7-a2a9cff7d6c5)

Irá abrir uma janela como essa, e nela você colocará o nome da sua maquina vitual, selecionará a `.iso` e irá marca a opção **pular instalação desassistida** *(Caso não marque essa opção irá apresentar uma falha na instalação)* agora após isso é só clicar em **Próximo**

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/9caaaa7c-286e-4773-b42e-1264b737af63)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/a3650ea4-bef7-42f7-b215-d60a98c32266)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/c1faa25c-c74f-4b4c-83fd-c356e91e580c)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/ac144bdf-7167-479a-be7d-7781aa3abc66)

![image](https://github.com/Elvis-Almeida/Elvis-Almeida-Servidor-Windows/assets/70353348/fd570ade-4517-4892-bdc7-f6f0ff7f319f)

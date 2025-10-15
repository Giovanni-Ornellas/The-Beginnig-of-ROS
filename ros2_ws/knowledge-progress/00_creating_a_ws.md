## **1. Tópico de Estudo**

Nesta parte estudaremos como criar um workspace do ROS, suas funcionalidades e pré-requisitos. 

- **Onde criar um workspace?**
    
    Um workspace não precisa ser criado dentro de nenhuma pasta específica, contanto que se tenha permissão de leitura e escrita. 
    
    Para mudar as permissões do workspace, podemos primeiro descobrir quais estão setadas e depois aplicar o comando chmod, da seguinte maneira:
    
    ```bash
    ls -l
    chmod u=rw,g=rw,o=rw <nome_do_ws>
    ```
    
    Podemos fazer a pasta em qualquer lugar do computador porque - após buildarmos o workspace - indicamos ao ROS onde a pasta se encontra ao rodar o comando:
    
    ```bash
    source <caminho_da_pasta>
    ```
    
- **O que é um workspace?**
    
    O workspace é onde os arquivos de builds, as configurações e instalações estão. Ele é, em última análise, o local onde todos os pacotes estão armazenados.Quando damos o comando para buildar o workspace, são gerados vários diretórios úteis, exceto o **src**, que deve ser criado pelo usuário para armazenar os scripts.
    
- **O Comando de build**
    
    O comando colcon vem de Collective Construction, ao darmos o colcon build no terminal, ele varre o workspace e compila todos os pacotes na ordem correta criando - caso já não exista - os diretórios de /install /log /build automaticamente.
    
    ```bash
    colcon build
    ```
    
- **Apontando para o diretório de forma correta**
    
    Como dito acima, para que o ROS reconheça o diratório criado, precismos sempre rodar o comando:
    
    ```bash
    source setup.bash
    ```
    
    Para evitar isso, podemos colocar o caminho até o arquivo setup.bash direto no arquivo com as variáveis de ambiente. Desse modo, o ROS Sempre achará a pasta do noso workspace automaticamente.
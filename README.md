# webmf-python-flask

Este é um projeto baseado em Python e Flask destinado a ser executado por meio do Jenkins. O objetivo é fornecer uma estrutura simples para facilitar a integração contínua e a entrega contínua (CI/CD).

## Como Executar o Projeto via Jenkins:

1. **Baixe e Execute o Repositório do Jenkins:**
   - Clone o repositório do Jenkins disponível em: [https://github.com/joseMarcus/jenkins](https://github.com/joseMarcus/jenkins)

2. **Conceda as Permissões Necessárias e Adicione o Usuário Jenkins:**
   - Vá até o diretório onde se encontra o docker.sock :
     ```bash
     cd /var/run
     ```
   - Dê todas as permissões (Observação: não recomendável para ambientes de produção) : 
     ```bash
     sudo chmod 777 docker.sock
     ```
   - Aicione o usuário Jenkins :
     ```bash
     useradd jenkins
     ```
   - Adicione o Jenkins ao grupo Docker e root :
     ```bash
     sudo usermod -aG docker jenkins
     ```
     ```bash
     sudo usermod -aG root jenkins
     ```
   - Visualize se eles foram adicionados :
     ```bash
     grep docker /etc/group
     ```
     ```bash
     grep root /etc/group
     ```
   - Adicione o usuário da máquina local ao grupo Docker :
     ```bash
     sudo usermod -aG docker $USER
     ```

3. **Crie a Pipeline:**
   - Após conceder as permissões, efetue o login no Jenkins e crie a pipeline para o projeto:
     - Acesse "Nova Tarefa" -> {nome} + Pipeline + "Tudo certo"
     - Configure a Definição como "Pipeline script from SCM", selecione o SCM como "Git" e adicione o link deste repositório.
     - Especifique o Branch como `{*/main}` e salve a configuração.

4. **Execute a Pipeline:**
   - Clique em "Construir Agora" para executar a pipeline e observe o status em "Open Blue Ocean".
  
Se tudo der certo é esta imagem que irá aparecer quando executar a pipeline.
![Imagem de Exemplo](/Terminal(projeto).png)


Este projeto é uma base sólida para iniciar a integração contínua e a entrega contínua de aplicativos Python com Flask. Certifique-se de ajustar as configurações de acordo com as necessidades específicas do seu projeto.

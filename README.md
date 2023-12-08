# webmf-python-flask



## Para executar o projeto via Jenkins:

Baixe e execute o repositório: https://github.com/joseMarcus/jenkins 

## Dê as permissões necessárias e adicione o usuário Jenkins

Utilize os comandos abaixos para dar as permissões necessárias: \

cd /var/run \
sudo chmod 777 docker.sock \
useradd jenkins \
sudo usermod -aG docker jenkins \
sudo usermod -aG root jenkins \
grep docker /etc/group \
grep root /etc/group \
sudo usermod -aG docker $USER

## Crie a pipeline

Após as permissões, efetue o login e crie a pipeline para o projeto: \

Nova tarefa -> {nome} + Pipeline + "Tudo certo" \
{descrição} + Definition(Pipeline script from SCM) + SCM(Git) + {Adicione o link deste repositório} + Branch{*/main} -> Salvar

## Execute a pipeline
Clique em "Construir agora" para executar a pipeline e observe o status em "Open Blue Option" 



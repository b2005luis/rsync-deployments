# workflow-training

#### RSync - Upload com sincronização diferencial

Este é um projeto de modelo para realização de sincronização diferencial de arquivos e pastas para servidores remotos.

Este processo se baseia na configuração de um ou mais workflows do Github Actions.

Além disso, é necessário preparar alguns segredos para cada repositório em questão.

#### Os segredos do repositório

> **DICA:** Os nomes dos segredos são da sua escolha, só deve se atentar em alterá-los em cada arquivo de workflow qie estiver usando o segredo. 

**SERVER:** DNS, domínio ou IP do servidor de destino.<br>
**PORT:** Número da porta aberta no servidor. Se não informado, será usado SSH na porta 22.<br>
**USER:** O login do usuário do serviço de SSH, FTP, ou o que for determinado pela sua plataforma de serviços.<br>
**SOURCE:** Caminho relativo mnaorigem, onde se encontram os arquivos a seren copiados para o servidor.<br> 
**TARGET:** O caminho onde os arquivos devem ser enviados, o caminho de origem, lá no servidor.<br>
**SSH_PRIVATE_KEY:** O conteúdo copiado da chave privada, gerada e autorizada pela sua plataforma, ou gerada por você, com ou sem senha e autorizada pela sua plataforma.<br>
**LOCAL_KEY:** O local no qual o step de configuração deve gerar, guardar e acessar a chave privada no container do Github Actions.<br> 
**SWITCHES:** São os comandos para o RSync, sobre como proceder mna sincronização.<br>~~~~

> **IMPORTANTE:** cuide muito bem desses segredos, pois caindo em mãos erradas, podem te render uma grande dor de cabeça!

#### Estratégias de sincronização

Para maiores informações da implementação, confira o ["arquivo de workflow""](.github/workflows/rsync-deploy.yaml)

As estratégias de sincronização vão depender da sua necessidade, podendo ser alterados formas de gatilhos como PULL REQUEST, PUSH entre outros.

Os nomes de branches podem ser alterados também, para direcionar os workflows de DEV, HOMOL, PROD, usando exemplos como main, e release para produção, e bugfix, hotfix e feature para desenvolvimento e homologação.

Você pode também criar steps de configuração, build, teste e muito mais.

Boa sorte! ✌

Qualquer dúvida sugestão, ou contribuição, entre em contato, ou faça o seu pull request!

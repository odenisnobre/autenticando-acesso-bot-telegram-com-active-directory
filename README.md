<h1 align="center">
<br>
Autenticando Acesso do Bot do Telegram com Active Directory
</h1>

<p align="center"> Que o uso de Bots, sejam eles de qualquer plataforma(Telegram, Whatsapp, Facebook, etc.), já é uma realidade isso é fato. Agora um item que é muito comentado e que se torna preocupante é o acesso a estes Bots principalmente quando falamos de dados de operacionais de empresas, independente do qual ramo.</p>
<p align="center"> Existem várias formas de conceder acesso a estes Bots, seja de forma manual ou automática. Fato que é que na maioria das vezes os desenvolvedores não possuem uma rotina de verificar se o usuário se encontra apto ou não para acessar tais dados. Essa aptidão pode ser tanto mudança de área, cargo e até mesmo saída da empresa, o que é o mais preocupante.</p>

<p align="center"> Neste projeto vamos detalhar uma forma de garantir o acesso do usuário ao Bot do Telegram através de autenticação do mesmo no Active Directory.</p>

<p align="center">
  <a href="https://www.apache.org/licenses/LICENSE-2.0">
    <img src="https://img.shields.io/badge/apache-2.0-blue" alt="License Apache">
  </a>
</p>


## Desenvolvimento

Vamos pensar no seguinte cenário: um usuário pediu para ter acesso ao Bot e esta permissão após aprovações foi liberada.
O administrador identificou o 'userId' do usuário e adicionou em algum lugar onde conseguisse, a cada acesso, consultar esse 'userId'.

Este modelo de liberação funciona muito bem só que gera um trabalho pois o administrador sempre tem que monitorar se este usuário está ativo ou não. Caso não esteja deverá remover o 'userID' da lista de pessoas liberadas para acesso. Isso nem sempre funciona ou para funcionar tem que term uma rotina muito bem detalhada para verificar se este usuário pode ou não pode ter o acesso.

O mais crítico é quando o usuário não faz mais parte da empresa e continua acessando as informações.

Pensando de forma centraliza, quando um usuário é admitido na empresa, na maioria da vezes, este colaboradores possui um nome de usuário de rede para poder acessar os recursos disponibilizados pela empresa. Este usuário é criado no 'Active Directory - AD', onde é feito toda a parte de permissionamentos deste usuário, definindo quais recursos ele pode acessar. Estes recursos podem ser desde o acesso a pasta específica da rede até mesmo quais sites ele pode abrir quando estiver navegando na internet.

Então se quando o usuário entra na empresa é solicitado a criação do usuário do 'AD' quando o mesmo sai também é solicitado a remoção.

Com todos estes detalhes então temos que podemos "travar" o aceso ao Bot desde que o mesmo continue na empresa. Como fazer isso?

Para isto precisamos de três pontos de configurações, uma do lado do usuário(no smartphone), outra no lado do programador e outro do lado da TI.

Do lado da TI é criar um grupo para gerenciar os usuários que terá acesso ao Bot. O nome é conforme padrão de cada empresa e este deverá ser passado para o progrmador.

Quando um usuário é criado no 'AD', este possui diversos atributos de identificação, como nome, sobrenome, empresa, local de trabalho, e por ai vai. A ideia principal é procurar um atributo único que identifique o usuário. Não existe um atributo padrão, mesmo que o 'username' seja o mais comum utilizado. Mas pode ser o número do telefone, registro, etc. A TI deverá passar qual atributo o desenvolver deverá considerar para fazer os filtros.

Com esta informação é aí que entra a configuração do lado do usuário no seu smartphone. O Telegram disponibiliza um item de configuração que se chama 'username':

<img src="https://github.com/dedynobre/autenticando-acesso-bot-telegram-com-active-directory/blob/master/imagens/acesso-01.png"/>





## Conclusão









## Help

Caso precisem te ajuda ou tenham alguma sugestão, deixe seu comentário [Aqui](https://github.com/dedynobre/autenticando-acesso-bot-telegram-com-active-directory/issues).
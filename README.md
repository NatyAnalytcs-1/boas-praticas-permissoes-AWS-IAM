# 🏰 Boas práticas de permissões na AWS (IAM) 🔐



### 👑 1. O Usuário Root – O Rei
````
 Nunca usar no dia a dia.
 Só para:
 Alterar configurações de faturamento.
 Ativar MFA na conta root.
 Configurações iniciais críticas.
 Sempre com MFA ativado.
````
> O Root é o 👑 Rei do Reino AWS.
Ele governa tudo, mas não deve sair para batalhas do dia a dia.
O Rei fica protegido no castelo com senha forte + MFA, aparecendo apenas em momentos realmente críticos.

### 🛡️ 2. Usuários IAM – Os Cavaleiros
````
Crie usuários individuais para cada pessoa.
Nunca compartilhar credenciais.
Atribua permissões mínimas necessárias (princípio do menor privilégio).
````
> Cada usuário é como um 🛡️ cavaleiro do reino.
Cada um recebe sua própria espada (credencial) e apenas as missões (permissões) que precisa cumprir.
Assim, se um cavaleiro cair em batalha, o dano ao reino é limitado.

### ⚔️ 3. Grupos IAM – As Tropas
````
Use grupos para gerenciar permissões, nunca usuários isolados.

Exemplos comuns:
Administradores → Acesso total para gerenciar recursos.
Desenvolvedores → Acesso limitado a serviços necessários (ex.: EC2, S3, Lambda).
Analistas de BI → Acesso de leitura a dados no S3, Athena, Redshift etc.
RH ou Financeiro → Apenas acesso a relatórios e faturas (Billing).
````
> Em vez de treinar cavaleiros individualmente, organizamos tropas ⚔️.
Assim, quando chega um novo guerreiro, basta colocá-lo no batalhão certo e ele já sabe suas funções. 

### 📜 4. Políticas IAM – As Leis do Reino
````
Prefira políticas gerenciadas pela AWS (mais seguras e atualizadas).
Use políticas personalizadas apenas se necessário.
Sempre revise e remova permissões desnecessárias.
````
> As políticas são 📜 leis que governam o reino.
As leis criadas pela AWS são confiáveis e mantidas pelo "Conselho Real".
Criar novas leis deve ser raro e muito bem pensado, para não abrir brechas no castelo.

### 🔑 5. Acesso temporário e chaves – As Chaves do Castelo
````
Evite chaves de acesso permanentes.
Use roles (funções) com permissões temporárias.
Ferramentas como AWS SSO ou IAM Identity Center são recomendadas para controle centralizado.
````
> Uma chave permanente é como deixar a chave do castelo 🏰 esquecida na taverna.
Prefira chaves mágicas ✨ que somem depois de usadas (acesso temporário com roles).
O IAM Identity Center funciona como o portal oficial do reino para entrada segura.


### 👀 6. Monitoramento – Os Espiões do Reino
````
Ative CloudTrail para auditoria de acessos.
Use IAM Access Analyzer para revisar permissões abertas.
Habilite alarms no CloudWatch para atividades suspeitas.
````
> Nenhum reino sobrevive sem espiões 👀.
> 
> CloudTrail: o escriba que registra cada movimento no reino.
> 
> Access Analyzer: o conselheiro que avisa quando uma porta do castelo ficou aberta.
> 
> CloudWatch Alarms: o sino da torre que toca quando há perigo.
>


### 👉 Resumindo – O Código do Reino

- 👑 Root: só para emergências reais.

- ⚔️ Grupos: tropas organizadas, nunca cavaleiros soltos.

- 🛡️ Menor privilégio: cada guerreiro com a missão exata.

- 🔐 MFA: escudo sagrado de proteção contra invasores.

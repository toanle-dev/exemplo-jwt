1. Autenticação

   Login: Após um usuário fornecer suas credenciais (como nome de usuário e senha), um servidor pode gerar um JWT que é assinado com uma chave secreta. Esse token é então enviado ao cliente (por exemplo, um navegador ou um aplicativo móvel).
   Autenticação de requisições subsequentes: Em vez de enviar as credenciais do usuário em cada requisição, o cliente pode enviar o JWT. O servidor pode validar o token e garantir que ele não foi alterado. Se válido, o servidor pode confiar que o usuário está autenticado.

2. Autorização

   Controle de Acesso: Após autenticar o usuário, o JWT pode incluir informações sobre os privilégios ou permissões do usuário (por exemplo, se ele é um administrador). Com base nessas informações, o servidor pode conceder ou negar acesso a recursos específicos.
   Scopes: No contexto de APIs, JWTs podem ser usados para especificar "scopes" ou permissões que um token tem, determinando o que o usuário pode acessar.

3. Troca de Informações

   Transporte Seguro de Dados: Como o JWT pode conter informações no payload, ele pode ser usado para transmitir dados entre partes de forma compacta e segura. Essas informações podem ser verificadas e confiadas pelo destinatário, uma vez que o token é assinado.
   Clams: O payload do JWT pode conter "claims", que são declarações sobre uma entidade (tipicamente, o usuário) e dados adicionais. Por exemplo, um claim pode indicar o tempo de expiração do token (exp), o emissor do token (iss), e assim por diante.

4. Session Management

   Sessões Stateless: Com o JWT, as sessões podem ser gerenciadas de maneira "stateless", ou seja, o servidor não precisa manter uma sessão no lado do servidor para cada usuário. Toda a informação necessária está no próprio token. Isso é particularmente útil em sistemas distribuídos e escaláveis, como microserviços.
   Logout e Revogação de Tokens: Embora JWTs sejam "stateless", é possível implementar mecanismos de revogação de tokens (como listas negras) para invalidar tokens após o logout ou por outras razões de segurança.

5. Autenticação Federada

   Single Sign-On (SSO): JWTs são comumente usados em sistemas de autenticação federada, como SSO, onde o token emitido por um provedor de identidade (por exemplo, Google, Facebook) pode ser usado para autenticar o usuário em diferentes serviços.

6. Compactação e Segurança

   Formato Compacto: O JWT é um formato compacto e autossuficiente que pode ser facilmente passado por meio de URLs, parâmetros POST ou cabeçalhos HTTP.
   Assinatura: O JWT é assinado usando algoritmos como HMAC ou RSA, o que garante que o token não foi adulterado.

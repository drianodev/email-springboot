# Email Spring Boot Service

Este é um projeto Spring Boot para envio de e-mails. Ele utiliza o framework Spring Boot e integra o envio de e-mails por meio do pacote `spring-boot-starter-mail`. O projeto inclui um controlador REST que permite o envio de e-mails com facilidade.

## Configuração

Antes de usar o serviço, é necessário configurar as propriedades do e-mail no arquivo `application.properties`. Certifique-se de fornecer as informações corretas para o servidor SMTP, incluindo o host, porta e credenciais (username e password). Abaixo está um exemplo de configuração usando [Mailtrap](https://mailtrap.io/) para fins de desenvolvimento:

```properties
spring.mail.host=sandbox.smtp.mailtrap.io
spring.mail.port=587
# spring.mail.username= Seu username do Mailtrap
# spring.mail.password= Sua senha do Mailtrap
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
```

## Estrutura do Projeto

O projeto consiste em três partes principais:

1. **`Email` Record:**
   - Um registro Java que representa um e-mail, com campos para destinatário, assunto e corpo.

2. **`EmailService` Classe:**
   - Um serviço que encapsula a lógica de envio de e-mails usando o `JavaMailSender` fornecido pelo Spring Boot.

3. **`EmailController` Classe:**
   - Um controlador REST que expõe um endpoint `POST` para enviar e-mails. Aceita dados no formato JSON no corpo da solicitação.

## Como Usar

1. **Clone o Repositório:**
   - Clone este repositório para a sua máquina local.

2. **Configuração:**
   - Configure as propriedades do e-mail no arquivo `application.properties` conforme necessário.

3. **Execução:**
   - Execute o aplicativo Spring Boot.

4. **Envie um E-mail:**
   - Faça uma solicitação `POST` para `http://localhost:8080/email` com os detalhes do e-mail no corpo da solicitação no formato JSON.

   Exemplo de Payload JSON:
   ```json
   {
     "to": "destinatario@email.com",
     "subject": "Assunto do E-mail",
     "body": "Corpo do E-mail"
   }
   ```

   Você pode usar ferramentas como cURL, HTTPie ou Postman para fazer a solicitação.

## Dependências

O projeto utiliza as seguintes dependências principais:

- `spring-boot-starter-mail`: Fornece suporte para envio de e-mails no ambiente Spring Boot.
- `spring-boot-starter-web`: Facilita o desenvolvimento de aplicativos da web usando o Spring MVC.

Certifique-se de verificar a [documentação do Spring Boot](https://docs.spring.io/spring-boot/docs/current/reference/html/index.html) para obter mais informações sobre como trabalhar com aplicativos Spring Boot.

# Desafio Back-end para Fintech

## Avisos antes de começar

-   Crie um repositório no seu GitHub **sem citar nada relacionado a empresa**;
-   Faça seus commits no seu repositório;
-   Envie o link do seu repositório para o local informado pelo recrutador;
-   Você poderá consultar o Google, Stackoverflow ou algum projeto particular na sua máquina;
-   Dê uma olhada em como será a [entrevista](#para-o-dia-da-entrevista-técnica).

### Sobre o ambiente da aplicação:

-   Você deve utilizar o framework Fastify em um projeto com Node.JS para implementação deste desafio.

-   Tente evitar usar muito métodos mágicos ou atalhos já prontos, como bibliotecas, boilerplates e trechos de códigos pronto. Sabemos que essas facilidades aumentam a produtividade no dia-a-dia mas aqui queremos ver o **seu** código e a sua forma de resolver problemas.

-   Valorizamos uma boa estrutura de containeres criada por você.

## Para o dia da entrevista técnica

Na data marcada pelo recrutador tenha sua aplicação rodando na sua máquina local para execução dos testes e para nos mostrar os pontos desenvolvidos e possíveis questionamentos.
Faremos um code review junto contigo como se você já fosse do nosso time :heart:, você poderá explicar o que você pensou, como arquitetou e como pode evoluir o projeto.

## Objetivo: Transferência entre Contas Simplificada

Temos 2 tipos de usuários, os comuns e lojistas, ambos têm carteira com dinheiro e realizam transferências entre eles. Vamos nos atentar **somente** ao fluxo de transferência entre dois usuários.

Requisitos:

-   Para ambos tipos de usuário, precisamos do Nome Completo, CPF, e-mail e Senha. CPF/CNPJ e e-mails devem ser únicos no sistema. Sendo assim, seu sistema deve permitir apenas um cadastro com o mesmo CPF ou endereço de e-mail;

-   Usuários podem enviar dinheiro (efetuar transferência) para lojistas e entre usuários;

-   Lojistas **só recebem** transferências, não enviam dinheiro para ninguém;

-   Validar se o usuário tem saldo antes da transferência;

-   Antes de finalizar a transferência, deve-se consultar um serviço autorizador externo. Crie um mock para essa consulta que deve retornar aleatóriamente se foi autorizado ou não;

-   A operação de transferência deve ser uma transação (ou seja, revertida em qualquer caso de inconsistência) e o dinheiro deve voltar para a carteira do usuário que envia;

-   No recebimento de pagamento, o usuário ou lojista precisa receber notificação (envio de email, sms) enviada por um serviço de terceiro e eventualmente este serviço pode estar indisponível/instável. Crie um mock para esse envio que deve retornar aleatóriamente se foi enviado ou não;

-   Este serviço deve ser RESTFul.

### Payload

Faça uma **proposta** :heart: de payload, se preferir, temos uma exemplo aqui:

POST /transaction

```json
{
    "value": 100.0,
    "payer": uuid,
    "payee": uuid
}
```

# Avaliação

Atente-se a cumprir a maioria dos requisitos, pois você pode cumprir-los parcialmente e durante a avaliação vamos bater um papo a respeito do que faltou.

A correção qualitativa será durante a entrevista e levará em conta os seguintes critérios:

## O que será avaliado e valorizamos :heart:

-   Documentação;
-   Se for para vaga sênior, foque bastante no **desenho de arquitetura**;
-   Código limpo e organizado (nomenclatura, etc);
-   Conhecimento de padrões (PSRs, design patterns, SOLID);
-   Ser consistente e saber argumentar suas escolhas;
-   Apresentar soluções que domina;
-   Modelagem de Dados;
-   Manutenibilidade do Código;
-   Tratamento de erros;
-   Cuidado com itens de segurança;
-   Arquitetura (estruturar o pensamento antes de escrever);
-   Carinho em desacoplar componentes (outras camadas, service, repository).

De acordo com os critérios acima, iremos avaliar seu teste para avançarmos para a entrevista técnica.
Caso não tenha atingido aceitavelmente o que estamos propondo acima, não iremos prosseguir com o processo.

## O que NÃO será avaliado :warning:

-   Fluxo de cadastro de usuários e lojistas
-   Frontend (só avaliaremos a (API Restful)[https://www.devmedia.com.br/rest-tutorial/28912])
-   Autenticação

## O que será um Diferencial

-   Uso de Docker;
-   Testes de [integração](https://www.atlassian.com/continuous-delivery/software-testing/types-of-software-testing);
-   Testes [unitários](https://www.atlassian.com/continuous-delivery/software-testing/types-of-software-testing);
-   Uso de Design Patterns;
-   Documentação;
-   Proposta de melhoria na arquitetura.

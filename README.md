# PUC Rio - Engenharia de Software
# MVP da **Sprint Arquitetura de Software** 

Esse MVP tem como objetivo resolver a dor de pessoas dentro do espectro autista nível 2 e 3. Essa dor está relacionada a identificação de possíveis mudanças de comportamentos.

O sistema desenvolvido foi nomeado como Comporta.io.

O sistema é capaz de identificar possíveis causas de mudanças de comportamentos, auxiliando assim no entendimento, para os responsáveis pela pessoa autista, e na execução da melhor ação para minimizar as alterações comportamentais.

O processo operacional do sistema consiste nas entradas de dados relacionados a rotina da pessoa autista. 
A primeira configuração a ser realizada é o cadastro de Eventos rotineiros executados pela pessoa autista. Após o cadastro dos eventos é feito o cadastro de rotina padrão por dia da semana.

Realizada as configurações iniciais, o próximo passo será a marcação se o evento foi realizado ou não, com o isso o sistema poderá minerar os dados dos dias e retornará o resultado, mostrando se a pessoa autista terá ou não alteração no comportamento.

## Pré-visualização

<p align="center" style="margin: 40px 0">
    <img src="https://github.com/elianoestevampuc/comportaio-frontend/raw/main/img/tela.png" height="100%">
</p>


## Arquitetura
A solução é composta por 2 camadas:
1) [Frontend](../comportaio-frontend/) >> Aplicação visual do sistema, onde o usuário executa as funcionalidades;
2) Microsserviços:
- [API Rotina](../comportaio-api-rotina/)  >> API para manter as operações da rotina;
- [API Pessoa](../comportaio-api-pessoa/)  >> API para manter as operações de cadastro da pessoa, eventos e padrões;
- [API de Imagens](https://www.pexels.com/pt-br/api/) >> API externa, pública, para recuperar fotos com expressões. 

<p align="center" style="margin: 40px 0">
    <img src="https://github.com/elianoestevampuc/comportaio-frontend/raw/main/img/arquitetura_mvp.jpg" height="100%">
</p>

## API de Imagens
Para ilustrar a representação do comportamento da pessoa, o sistema está consumindo uma API externa, pública, que retorna imagens a partir da consulta requerida, no caso são de pessoas sorrindo, para a situação onde não há possíbilidade de alteração de comportamento e pessoas tristes, para representar pessoas com possíveis alterações de comportamento.
A API se chama [PEXELS](https://www.pexels.com/pt-br/api/).

<p align="center" style="margin: 40px 0">
    <img src="https://github.com/elianoestevampuc/comportaio-frontend/raw/main/img/api_externa.png" height="100%">
</p>

Antes de usar a API, é necessário realizar o cadastro na plataforma e gerar um token de acesso.

Exemplo de uso:
<p align="center" style="margin: 40px 0">
    <img src="https://github.com/elianoestevampuc/comportaio-frontend/raw/main/img/exemplo_api_externa.png" height="100%">
</p>

O uso das fotos da API são gratuitas, conforme descrito na página:
<p align="center" style="margin: 40px 0">
    <img src="https://github.com/elianoestevampuc/comportaio-frontend/raw/main/img/api_externa_licenca.png" height="100%">
</p>
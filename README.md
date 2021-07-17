# regras-negocio-raro-academy

## Expectativa com esse tema: 

Aprender mais o funcionamento das regras de negócio voltadas à área de desenvolvimento. Encontrar maneiras de traduzir e comunicar de maneira eficiente entre as diversas áreas: cliente x equipe de desenvolvimento, por exemplo.

## Realidade com esse tema:



### Extração de modelos:

`Banco
-- nome
-- codigo

TipoConta
-- nome
-- codigo

Favorecido
-- banco: Banco
-- tipoConta: TipoConta
-- Agencia
-- Conta
-- Digito
-- CPF_CNPJ
-- titularidade

Limites
-- minimo
-- maximo
-- saldo

DadosRecorrencia
-- mesesRecorrencia
-- listaDataTransferencia - (gerado no back-end)

feriados: [Feriado]
listaBancos: [Banco]

Transferência
-- origem: Favorecido
-- favorecido: Favorecido
-- Valor
-- Data
-- recorrencia: DadosRecorrencia
`


Transferência
  - Banco
    - É o mesmo banco?
    - Tipo de conta
    - Agência
    - Número da conta
    - Dígito da conta
  - Titularidade
    - É mesma titularidade?
      - Sim     
      - Não:
        - Nome
        - Email?
        - CPF ou CNPJ   
  - Data de transferência
    - Hoje
      - Mesma instituição?
        - Sim
          - Horários próprios
        - Não 
          - Horários diferentes
      - Está dentro do horário definido?
        - Sim
          - Vai para tela de valor
        - Não
          - Vai para agendamento: gostaria de agendar?
            - Sim
              - Escolha de data
              - Vai para tela de valor
            - Não
              - Envia informação de volte depois
       - Transferência recorrente?
   - Tela de valor
     - Define o limite de transfência conforme opções anteriores
     - Valor está dentro do limite?
        - Sim
           - Vai para tela de confirmação
        - Não
           - Notifica na validação
           - Não permite avançar
           - Destaca o limite em vermelho          


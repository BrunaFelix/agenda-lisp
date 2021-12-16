# Agenda Lisp #

> Projeto desenvolvido para a disciplina **Linguagens de Programação Não Convencionais**, ministrada pelo [Professor Dr. Thiago Gottardi](https://bv.fapesp.br/pt/pesquisador/104729/thiago-gottardi/), durante o sexto semestre da graduação em [Bacharelado em Ciências da Computação na Unesp de Rio Claro](https://igce.rc.unesp.br/#!/departamentos/demac/pagina-do-curso-de-bcc/home/).


## Para iniciar o projeto, faça: ##
* Inicialize o contâiner Docker com:
```docker
    docker run -d -t --name clisp Cl foundation/clisp
```

* Copie os arquivos com as funções para o contâiner:
```bash
    docker cp .\functions\agenda.lisp clisp:/home/agenda.lisp
    docker cp .\functions\eventos.lisp clisp:/home/eventos.lisp
    docker cp .\functions\auxiliares.lisp clisp:/home/auxiliares.lisp
```

* Acesse o contâiner "clisp" e chame o REPL clisp:
```bash
    docker exec -it clisp bash
    cd home
    clisp
```

* No interpretador CLISP, importe o arquivo agenda.lisp:
``` lisp
    (load "agenda.lisp")
```

* Para adicionar eventos na agenda acesse o arquivo ("eventos.lisp") e adicione uma linha seguindo aseguinte ordem:
``` lisp
    (:inicio '(2021 1  7 19) :fim '(2021 1  7 22) :nome "Jantar Empresa")
```
  Na qual, primeiro é especificado as informações sobre o inicio do evento, o primeiro parâmetro é o ano, em seguida o mês, o dia e a hora. A segunda parte deve ser preenchida 
  com informações sobre o fim desse evento, acompanhado dos mesmos campos da seção de inicio, sendo eles: ano, mês, dia e hora, assim respectivamente. E por último, deve ser 
  adicionado o nome do evento em questão. 
  
  
* A agenda possui três funções(calendario, calendario-eventos e mostra-eventos). Para executar a função calendário basta invocar da seguinte forma:
``` lisp
    (calendario :ano 2021 :mes 7 :dia 10)
```
O programa deve retornar essa data, para sinalizar caso exista algum evento nesse dia especificado, o dia aparecerá destacado do um asterisco '*'.
``` lisp
    
```
Para a função calendário, o único parâmetro obrigatório é o do ano, todos os outros são opcionais.

* A função calendario-eventos tem como objetivo listar todos os meses de um ano especifico, com todos os dias e os dias com eventos sinalizados por um asterisco. Para chamar
esta função basta:
``` lisp
    (calendario-eventos :ano 2021)
```
Para essa função o parâmetro 'ano' é obrigatório.

* A função mostra-eventos tem como objetivo listar todos os eventos encontrados de acordo como os campos invocados na função. Sua chamada se dá, pela seguinte forma:
``` lisp
    (mostra-eventos :ano 2021 :mes 1 :dia 12)
```
Irá assim retornar o evento na data especificada, caso não encontre nenhum, retornará NIL. Para a função mostra-eventos, o único parâmetro obrigatório é o do ano, todos os 
outros são opcionais.





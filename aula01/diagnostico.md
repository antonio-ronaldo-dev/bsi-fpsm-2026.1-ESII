ANTONIO RONALDO COSTA DA SILVA FILHO 

Matrícula: 2023022460

E-mail: ronaldo.silva.filho724@gmail.com



Problema 1



O que a documentação diz: a RN02 informa que o prazo mínimo de empréstimo deve ser de 1 dia.

O que o código faz: o método: registrar() recebe a quantidade de dias e calcula a data de devolução sem verificar se o número informado é maior que zero.

Por que é um problema: o sistema pode aceitar empréstimo com 0 dias ou até com dias negativos, criando um registro incorreto sem avisar o usuário.

Já documentado? não.



Problema 2



O que a documentação diz: lá no UC03, quando não houver empréstimos em atraso, o sistema deve mostrar a mensagem “Nenhum empréstimo em atraso”.

O que o código faz: o método: listar_atrasados() só mostra alguma coisa quando encontra um empréstimo atrasado. Quando não existe atraso, ele não imprime nenhuma mensagem.

Por que é um problema: o usuário fica sem resposta e pode pensar que a opção não funcionou ou que o sistema travou.

Já documentado? não.



Problema 3



O que a documentação diz: o RI02 diz que toda operação feita com sucesso deve exibir uma confirmação clara para o usuário.

O que o código faz: ao registrar um empréstimo, o sistema apenas mostra uma mensagem de: [EMAIL] com a data de devolução, mas não mostra uma frase direta dizendo que o empréstimo foi registrado com sucesso.

Por que é um problema: o usuário pode ficar em dúvida se o empréstimo realmente foi salvo ou se o sistema apenas exibiu uma notificação.

Já documentado? não.



Problema 4



O que a documentação diz: o RI03 diz que toda operação inválida deve mostrar uma mensagem de erro descritiva sem encerrar o sistema.

O que o código faz: no menu principal, se o usuário digitar uma opção que não existe, como 9, o sistema não mostra erro e apenas volta para o menu.

Por que é um problema: o usuário não entende o que errou e não recebe orientação sobre as opções válidas.

Já documentado? não.



Problema 5



O que a documentação diz: o documento de projeto registra a DT04, dizendo que o cálculo de multa está duplicado em dois métodos.

O que o código faz: o cálculo da multa aparece dentro de: devolver() e também dentro de: listar_atrasados()  .

Por que é um problema: se o valor da multa mudar, será necessário alterar em mais de um lugar, aumentando a chance de esquecer uma parte e deixar o sistema com resultados diferentes.

Já documentado? sim.



Problema 6



O que a documentação diz: o documento de projeto registra a DT03, dizendo que a notificação está misturada com a lógica de negócio.

O que o código faz: os métodos principais imprimem mensagens de: [EMAIL] diretamente dentro da regra de empréstimo, devolução e listagem de atrasados.

Por que é um problema: a parte de regra do sistema fica misturada com a parte de aviso ao usuário, deixando o código mais difícil de entender, testar e mudar depois.

Já documentado? sim.



Problema 7



O que a documentação diz: o documento de projeto registra a DT02, dizendo que existem variáveis globais acessadas diretamente pela classe.

O que o código faz: a classe (Sistema) usa diretamente as listas globais (equipamentos) e (emprestimos_registrados).

Por que é um problema: os dados ficam espalhados fora da classe, o que dificulta controlar o estado do sistema e aumenta o risco de erro quando o código crescer.

Já documentado? sim.

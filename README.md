```
/*Separar as regras de negócio, remover elas dos Widgets e colocar em Actions.
Criamos uma variável, numérica, que receberá o incremento, e uma função para executar este incremento em mais um, toda vez que o botão é pressionado.*/ 
import 'package:mobx/mobx.dart';
//unificamos os aruivos com o que foi gerado
part 'counter.g.dart';
//utilizamos herança para transformar nosso contador em Store
abstract class _Counter with Store{
  //tornar o objeto observavel, ou seja, um tipo o qual nosso widget ficará sempre olhando para ele
  @observable
  int value = 0;

  //observaveis só são alterados através de ações
  @action
  increment(){
    value++;
  }

  //após criar os dois precisamos gerar o código pelo comando flutter packages pub run build_runner build
  //este comando irá olhar os arquivos que utilizam o MixinStore (with Store) e gerar um arquivo secundario
  //sempre que fizermos uma alteração nesta codigo precisamos utilizar o comando
  //para limpar estes arquivos gerados utilizamos flutter packages pub run build_runner clean

}```

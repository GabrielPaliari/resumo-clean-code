# **Introdução**

Este texto é um resumo do livro Clean Code, de Robert C. Martin, publicado em 2008. Nele eu busquei transcrever os pontos fundamentais do livro mas tomei a liberdade de adicionar alguns diagramas e interpretações minhas. No entanto, a imensa maioria do texto é uma tradução das partes do livro que eu achei mais importantes, inclusive os exemplos. 

A intenção principal do livro é ensinar princípios e práticas que auxiliem xs programadorxs a escrever um bom código, legível e eficiente, ou seja, um código limpo. Mais do que isso, ao ensinar a essência de um bom código, o autor nos convida a enxergar a programação com profissionalismo, encurtando os caminhos para a excelência na arte de programar. Espero que este resumo te ajude a melhorar a qualidade do seu código isso te faça bem no dia a dia. :)       

## **Código ruim**

Se você já programou por algum tempo, com certeza já ficou emperradx em um código ruim de alguém. Se programou por alguns anos, com certeza já ficou emperradx no seu próprio código ruim alguma vez. Sabemos que código ruim nos atrapalha, no entanto, porque escrevemos o código de forma mal feita? 

![](https://tenor.com/view/coding-programando-computadora-gif-8749684.gif)

Talvez seja por causa das cobranças, estávamos muito atoladxs, precisávamos fazer aquela entrega que tínhamos prometido, precisávamos mostrar serviço, se não poderíamos ser demitidos, ou simplesmente não tínhamos tempo, então apenas tentamos deixar "funcionando" e cruzamos os dedos para nada quebrar. 

Isso tudo acontece, e nem sempre é nossa culpa, mas se nós não cuidarmos da qualidade do código, quem irá cuidar? E esse simples fator, a qualidade do código, tem um impacto gigantesco em qualquer time, e consequentemente, nas empresas de tecnologia como um todo.

## **O ciclo vicioso do código ruim**

O que geralmente acontece quando as equipes não se preocupam ativamente com a qualidade do código é que com o tempo, o projeto se torna um peso indesejável para todxs que trabalham nele. 

![](https://tenor.com/view/data-code-review-star-trek-shocked-mind-blown-gif-5637869.gif)

Os bugs começam a não ser concertados de uma versão para a outra, a manutenção se torna demorada, a implementação de novas features é custosa. O seguinte ciclo ilustra melhor o que ocorre:        

Cobrança Excessiva -> Código ruim -> Diminui a produtividade -> Mais cobrança

Esse ciclo é mais comum do que gostaríamos na nossa área, e muitas empresas de tecnologia acabam falindo por não entenderem a importância de um código bem escrito. O que ocorre é que com o tempo a produtividade tende a zero, porque cada mudança se torna muito custosa e geralmente faz surgir outros bugs, o que torna o desenvolvimento muito lento, não importando a quantidade  de pessoas trabalhando no projeto.

![image-20200603060749623](/home/gabriel/.config/Typora/typora-user-images/image-20200603060749623.png)

O que muitas vezes se faz para tentar solucionar é fazer um projeto novo do zero que tenha as mesmas funcionalidades. No entanto o sistema antigo deve continuar funcionando enquanto o novo é desenvolvido. E se a equipe não tomar cuidado, o novo projeto pode ter de ser redesenhado antes mesmo de substituir o antigo.

## **Então como codar mais rápido?**

![](https://tenor.com/view/struggle-homework-programmer-wtf-gif-6090371.gif)

﻿O que geralmente pensamos é que escrever um código de qualquer jeito irá nos ajudar a cumprir os prazos. No entanto, o que ocorre na verdade é que um código bagunçado nos atrasa imediatamente e nos faz perder muito mais tempo do que perderíamos com um código bem escrito. ***O único jeito de codar rápido é manter o código o mais limpo possível a todos os instantes.*** Mas afinal, o que é código limpo e porque é tão importante? 

## O que é código limpo?

![](https://tenor.com/view/gopi-bahu-laptop-gif-8834959.gif)

O livro traz algumas frases de grandes nomes da área de desenvolvimeto de software para ilustrar o que é código limpo para esses grandes programadores.

**Bjarne Stroustrup, inventor of C++**

*"I like my code to be elegant and efficient.[...] Clean code does one thing well."*

*(eu gosto que meu código seja elegante e eficiente [...] Um código limpo faz uma coisa bem feita.)*

**Grady Booch, author of Object Oriented Analysis and Design with Applications**

*Clean code reads like well-written prose. Clean code is simple and direct. Clean code never obscures the designer’s intent.* 

(Código limpo se lê como uma prosa bem escrita. Código limpo é simples e direto. Código limpo nunca a intenção de quem o fez.)

**Michael Feathers, author of Working Effectively with Legacy Code**

*Clean code always looks like it was written by someone who cares.* 

*(Um código limpo sempre parece que foi **escrito por alguem que se importa**)*

## **Somos Autorxs**

![](https://tenor.com/view/thumbsup-computer-kid-gif-4533805.gif)

Da próxima vez que for programar, lembre-se que você é um/a autor/a que escreve o código para pessoas lerem. Por isso, tente causar uma boa impressão. Mas isso não é uam simples questão de agradar nossxs colegas. Para a nossa surpresa, **o tempo que gastamos lendo código é 10 vezes maior do que o tempo que gastamos escrevendo código**. 

Nós estamos constantemente lendo código antigo para escrever código novo.  Dessa forma, nós queremos fazer a leitura ser mais fácil, mesmo que isso torne a escrita mais difícil. Não há como escrever código novo se não lermos o código antigo em volta. **Então, se você quer tornar a escrita de novo código mais fácil, torne a leitura mais fácil.**   

## **A regra de ouro** 

*"Deixe o mundo um pouco melhor do que quando você o encontrou..."*

*"Deixe o código um pouco melhor do que quando você o encontrou."*

Não precisam ser grandes mudanças: renomeie uma variável, remova uma duplicação, crie um método mais descritivo... O importante é que você melhore o código em comparação a antes de você modificá-lo. Assim, o projeto irá melhorar com o tempo, ao invés de piorar.

_____

# Dicas e heurísticas

![](https://tenor.com/view/kios-angry-computer-stare-gif-16068406.gif)

Esta seção se destina a resumir as dicas e heurísticas consideradas mais essenciais ao longo do livro. Nâo estão perto de estarem completas, mas com elas já é possível melhorar bastante o código.

## **Elimine a Repetição (DRY)**

Evitar a repetição no código é a regra mais importante para se ter um código limpo. Essa regra é famosamente conhecida pelo acrônimo DRY (*don't repeat yourself*). Na verdade, a maioria dos padrões de design de código que surgiram nos últimos 15 anos são apenas maneiras bem conhecidas de eliminar a repetição. Até mesmo a programação orientada a objetos é ela própria uma estratégia para organizar módulos e eliminar a duplicação.

Toda vez que você ver uma repetição no código isso significa uma oportunidade perdida para alguma abstração. A repetição poderia se tornar uma função ou até uma outra classe. Ao criar uma abstração para encapsular tal repetição, você torna o seu código mais modular facilita a sua reutilização, diminuindo também as probabilidades de erro, e facilitando mudanças.

Por isso, encontre e elimine a repetição onde você puder.

#### **Seja consistente**

Se você faz uma coisa de um jeito, faça todas as coisas similares da mesma forma. Seja cuidadosx com as convenções que você escolhe e uma vez escolhidas, continue seguindo-as. A simples consistência faz o código se tornar muito mais fácil de ler e modificar.

# Nomes

## **Escolha nomes descritivos**

Escolher nomes é o que mais fazemos na programação. Nomeamos variáveis, funções classes, arquivos, projetos, etc. Por isso: não escolha nomes de qualquer jeito. Tenha certeza de que o nome é descritivo. Nomes são 90% do que é necessário para um código ser legível. Nomes são muito importantes para serem tratados sem cuidado.

Os nomes devem revelar a intenção de se criar cada coisa no seu código e não ser simplesmente letras ou palavras sem sentido. 

Compare este trecho:

```java
public int x() {
    int q = 0;
    int z = 0;
    for (int kk = 0; kk < 10; kk++) {
        if (l[z] == 10)
        {
            q += 10 + (l[z + 1] + l[z + 2]);
            z += 1;
        }
        else if (l[z] + l[z + 1] == 10)
        {
            q += 10 + l[z + 2];
            z += 2;
        } else {
            q += l[z] + l[z + 1];
            z += 2;
        }
    }
    return q;
}
```

  Com este:

 ```java
public int score() {
   int score = 0;
   int frame = 0;
   for (int frameNumber = 0; frameNumber < 10; frameNumber++) {
    if (isStrike(frame)) {
     score += 10 + nextTwoBallsForStrike(frame);
     frame += 1;
    } else if (isSpare(frame)) {
     score += 10 + nextBallForSpare(frame);
     frame += 2;
    } else {
     score += twoBallsInFrame(frame);
     frame += 2;
    }
   }
   return score;
  }
 ```

## **Faça distinções significativas**

Funções, classes, variáveis, etc... com nomes muito parecidos dificultam o seu entendimento e uso. Pense sempre que uma outra pessoa irá ler o seu código. Faça distinções significativas para que qualquer um saiba do que se trata. Por exemplo, as variáveis a seguir são difíceis de distinguir:

```java
  getActiveAccount();
  getActiveAccounts();
  getActiveAccountInfo();
```

Qual delas utilizar? Faça nomes distintos para não causar confusões...

Evite também nomes ambíguos ou genéricos. Os nomes devem ser específicos e dizer exatamente o porque você criou uma variável ou função. 

## **Substitua números/símbolos "mágicos" por constantes**

É uma má ideia ter números à mostra no seu código. É sempre melhor esconder os números ou símbolos em constantes do que deixá-los espalhados pelo código. por exemplo o número 86,400 deve ser escondido atrás da constante `SECONDS_PER_DAY`. Isso também é válido para strings, como no exemplo abaixo: 

```java
// antes:
assertEquals(7777, Employee.find(“John Doe”).employeeNumber());

// depois:
assertEquals(EMPLOYEE_ID, Employee.find(EMPLOYEE_NAME).employeeNumber());	

```

## **Use variáveis explicativas**

Para melhorar a legibilidade do seu código, um recurso muito poderoso é a utilização de variáveis intermediárias explicativas. Assim fica muito mais fácil de entender a sua linha de raciocínio. Considere o próximo exemplo:

```java
  Matcher match = headerPattern.matcher(line);
  if(match.find()) {
    String key = match.group(1);
    String value = match.group(2);
    headers.put(key.toLowerCase(), value);
  }
```

O simples uso das variáveis explicativas esclarece que o primeiro grupo do *match* é a chave (*key*) e o segundo, o valor (*value*).

# Funções

## **Funções devem ser pequenas**

**A primeira regra sobre funções é que elas devem ser pequenas**; A segunda regra sobre funções é que elas devem ser menores do que isso. As funções nao devem passar de uma algumas dezenas de linhas. Isso garante que elas se tornam fáceis de ler e de entender. Quando você se força a criar funções menores, está se esforçando por abstrair pequenas tarefas com nomes descritivos. O resultado é um código muito omais limpo e legível.

## **Funções devem fazer apenas uma coisa**

É tentador escrever funções que fazem várias operações em sequência. Essas funções fazem mais do que uma coisa e devem ser convertidas em funções menores que fazem uma única coisa, cada uma cuidando do nível de abstração próprio da sua tarefa. 

Se você está escrevendo uma função que faz mais de uma coisa, crie funções menores a partir dela e as utilize. Isso faz com que o código fique muito mais fácil de ler, pois assim ele fica mais próximo de um texto,onde cada função é uma tarefa com suas subtarefas. 

## **Os nomes das funções devem dizer o que elas fazem**

O que esse código faz?

```
Date newDate = date.add(5);
```

Você espera que ele adicione dias ou horas à data? E o método modifica a intância `date` ou apenas retorna uma nova data sem mudar a instância antiga? Você não consegue inferir apenas pelo nome o que a função faz.

Se você tem de olhar para implementação ou documentação para saber o que a função faz então você deve tentar achar um nome melhor para a função.

If you have to look at the implementation (or documentation) of the  function to know what it does, then you should work to find a better  name or rearrange the functionality so that it can be placed in  functions with better names.

## **Evite parâmetros que mudam o comportamento da função**

Não crie funções que se comportem de forma diferente baseadas em um determinado parâmetro. Isso viola o princípio de que uma função deve fazer uma única coisa. É melhor criar duas ou mais funções menores que façam apenas uma coisa. 

O mais comum é que esse parâmetro seja booleano: a função faz uma coisa quando recebe `true` e outra quando recebe `false`, mas ele também pode ser um enum ou string.   

## **Entenda o algoritmo**

Muitas pessoas estão satisfeitas em fazer o código "funcionar", mas isso não é o bastante. É necessário entender exatamente *como* o código funciona. Isso é essencial para que saibamos se estamos utiizando o algoritmo correto, se ele é eficiente o bastante, se é possível mudá-lo caso necessário, etc. 

Geralmente a melhor forma de obter este conhecimento sobre como o código funciona é refatorar determinada função de tal forma que o resultado seja um método tão claro e expressivo que fica *óbvio* como ele funciona.

## **Crie funções para encapsular condições** 

A lógica booleana já é dificil o suficiente sem estar dentro de um `if` ou `while`. Crie funções que expliquem a intenção das condicionais que você utilizar. 

Boolean logic is hard enough to understand without having to see it in the context of an `if` or `while` statement. Extract functions that explain the intent of the conditional.

Por exemplo, o código seguinte:

```java
if (timer.hasExpired() && !timer.isRecurrent())
```

pode ser substituído por:

```java
if (shouldBeDeleted(timer))
```

# Comentários

Os comentários também fazem parte do código, também precisam constantemente ser mantidos pelo time. Dessa forma, só escreva comentários se eles forem realmente úteis, e se for escrever algum, faça bem feito. **Prefira criar um código que seja auto explicativo ao invés de criar um código confuso e tentar explicá-lo através dos comentários.**     

## Bons comentários:

1. Comentários legais

   ```java
      // Copyright (C) 2003,2004,2005 by Object Mentor, Inc. All rights reserved.
      // Released under the terms of the GNU General Public License version 2 or later.
   ```

2. Explicar a intenção

   ```java
      public int compareTo(Object o)
      {
        if(o instanceof WikiPagePath)
        {
          WikiPagePath p = (WikiPagePath) o;
          String compressedName = StringUtil.join(names, “”);
          String compressedArgumentName = StringUtil.join(p.names, “”);
          return compressedName.compareTo(compressedArgumentName);
        }
        return 1; // we are greater because we are the right type.
          		   // (somos maiores porque somos do tipo certo)
      }
   ```

3. Comentários de TODO

   ```java
      // TODO-MdM these are not needed
      // We expect this to go away when we do the checkout model
      // (Esperamos que isso seja removido quando fizermos o modelo de pagamento) 
      protected VersionInfo makeVersion() throws Exception
      {
        return null;
      }
   ```

4. Amplificação

   Amplifica a importância de algum trecho que passaria despercebido

     ```java
      String listItemContent = match.group(3).trim();
      // the trim is real important.  It removes the starting
      // spaces that could cause the item to be recognized
      // as another list.
      // (O trim é realmente importante. Ele remove os espaços iniciais que poderiam 
      // provocar o reconhecimento do item como outra lista)
      new ListItemWidget(this, listItemContent, this.level + 1);
      return buildList(text.substring(match.end()));	
     ```

   

## Comentários ruins:

1. #### Informações inapropriadas

   - Comentários não devem conter informações inapropriadas a um comentário, como por exemploa versão do programa ou quem alterou o código por último. Essas informações são melhor armazenadas no git. **Comentários devem ter apenas notas técnicas sobre o código, não sobre o git.**

     Exemplo:

     ```
      * Changes (from 11-Oct-2001)
      * --------------------------
      * 11-Oct-2001 : Re-organised the class and moved it to new package 
      *               com.jrefinery.date (DG);
      * 05-Nov-2001 : Added a getDescription() method, and eliminated NotableDate 
      *               class (DG);
      * 27-Aug-2002 : Fixed bug in addMonths() method, thanks to N???levka Petr (DG);
      * 03-Oct-2002 : Fixed errors reported by Checkstyle (DG);
      * 13-Mar-2003 : Implemented Serializable (DG);
      * 29-May-2003 : Fixed bug in addMonths method (DG);
      * 04-Sep-2003 : Implemented Comparable.  Updated the isInRange javadocs (DG);
      * 05-Jan-2005 : Fixed bug in addYears() method (1096282) (DG);
     ```

2. ### Comentários redundantes:

   - **Comentários não devem dizer aquilo que o código consegue dizer por si mesmo.** 

     Exemplos:

     ```java
        /** Returns the day of the month.
        	*
        	* @return the day of the month.
        	*/
       public int getDayOfMonth() {
        return dayOfMonth;
       }
     ```

     - **Não utilize regras de comentários obrigatórios.** Se foi decidido que todas as funções e classes devem ter um comentários obrigatórios, repense essa escolha com o seu time. Comentários obrigatórios geralmente são redundantes e inúteis, e acabam por ser ignorados por todos com o passar do tempo, se tornando um ruído desnecessário que só atrapalha.

       Exemplos:

       ```java
       /**
           * 
           * @param title The title of the CD
           * @param author The author of the CD
           * @param tracks The number of tracks on the CD
           * @param durationInMinutes The duration of the CD in minutes
           */
          public void addCD(String title, String author, 
                             int tracks, int durationInMinutes) {
            CD cd = new CD();
            cd.title = title;
            cd.author = author;
            cd.tracks = tracks;
            cd.duration = duration;
            cdList.add(cd);
          }
       ```

       ```java
          /** The name. */
          private String name;
       
          /** The version. */
          private String version;
       
          /** The licenceName. */
          private String licenceName;
       
          /** The version. */
          private String info;
       ```

   - #### Não utilize um comentário onde você poderia utilizar uma função ou variável

     Quando escrevemos um código confuso ou bagunçado, às vezes pensamos: *"esse código está muito confuso, melhor comentá-lo"*. Na verdade melhor seria reescrever o código de forma mais descritiva e organizada. Para isso, utilize funções e variáveis com nomes descritivos e auto explicativos. 

     O que é melhor? Isso:

     ```java
     // Check to see if the employee is elegible for full benefits
     // (Conferir se o empregado pode receber todos os benefícios)
     if ((employee.flags & HOURLY_FLAG) && (employee.age > 65))
     ```

     Ou isso?

     ```java
     if (employee.isEligibleForFullBenefits())
     ```

     **Sempre que possível, utilize o código como meio de expressar sua intenção, e o seu raciocínio, ao invés de usar comentários para explicar um código mal escrito.** 

      

3. #### Comentários obsoletos ou desatualizados 

   - Os comentários ficam desatualizados rápido. É melhor não escrever um comentário que vai ficar desatualizado. Se você achar um comentário obsoleto, atualize-o ou livre-se dele. Eles mais atrapalham do que ajudam.

4. #### Mal escrito

   - **Se você vai gastar o seu tempo escrevendo um comentário, é melhor fazer isso direito.** Se você escrever o comentário de qualquer jeito a próxima pessoa a lendo o seu código (que pode ser até você mesmo do futuro) pode demorar para entender, ou pior, entender errado. Portanto, 
     - escolha as palavras com cuidado, 
     - utilize a gramática e a pontuação correta, 
     - seja breve e sucinto.

5. #### Código comentado

   - O código comentado é uma **abominação**. Ninguém sabe se aquele código tem sentido ou não, há quanto tempo ele está lá... No entanto, ninguém vai deletar, simplesmente porque assume-se que alguém vai precisar daquele código ou tem planos pra ele. 
   - Código comentado apodrece, ficando cada dia menos relevante. Ele chama funções que não existem, usa variáveis que mudaram de nome, ele polui o código e atrapalha as pessoas que estão tentando ler as informações realmente relevantes.
   - **Se hoje temos git, porque deixar o código comentado?** Se você achar algum código comentado, delete! Se alguém precisar dele depois é só olhar no histórico do git.

# Formatação

### Mantenha consistência no idioma

É muito importante se ter um idioma como padrão no seu código. Imagine um código que tem variáveis em inglês e outras em português, ou ainda o nome de uma variável que é metade em inglês e metade em português. Fica muito difícil de ler e entender o código. Por isso, defina um padrão. Geralmente as bibliotecas utilizadas são todas em inglês, então para que não ocorra este problema é melhor definir que todo o código será em inglês.

### **Espaçamento vertical: **

- Variáveis e funções devem ser definidas perto da onde elas serão utilizadas; 

- Variáveis locais devem ser declaradas logo antes do seu primeiro uso. Não queremos variáveis locais declaradas centenas de linhas acima da onde serão usadas.

- Funções auxiliares devem estar próximas das funções que as utilizam, quando possível. 

- É interessante que variáveis ou linhas semelhantes sejam agrupadas verticalmente e separadas de grupos que não tem a afinidade de conceito, mesmo dentro do mesmo escopo. Você pode usar linhas em branco para isso, como no exemplo abaixo onde a declaração de variáveis privadas foi separada da declaração da função publica.

  ```java
  public class ReporterConfig {
     private String m_className;
     private List<Property> m_properties = new ArrayList<Property>(); 
  
     public void addProperty(Property property) {
      m_properties.add(property);
     }
  }
  ```

### **Mantenha consitência no estilo de código**

É importante se ter um padrão no estilo de código, para que todxs trabalhando no projeto falem a mesma língua no que se refere à forma como formatam o código. Para isso pode-se utilizar bibliotecas de estilo, como o pacote ***prettier*** utilizado largamente entre xs desenvolvedorxs  ***javascript***. Assim, não é necessário gastar tempo pensando-se no estilo do código, e se todos utilizarem a mesma configuração os estilos ficarão constistentes em todos os arquivos, facilitando a leitura.

# Testes

![](https://tenor.com/view/bug-programmer-life-gif-14891409.gif)

Testes também são código. E eles devem ter a mesma importância do código de produção. As mudanças feitas no código de produção requerem uma mudança nos testes. Se não fazemos um código de testes limpo, vamos ter problemas sempre que algum teste quebrar e tivermos que mudar. Com o tempo vamos querer descartar os testes. Descartando os testes perdemos a coragem de limpar o código, o código apodrece com o tempo e no final temos um sistema que tem um custo de manutenção muito alto.

Testes são importantes porque fazem o seu código:

1. Ser mais flexível, 
2. Ser mais fácilmento reutilizável 
3. Ter alta manutenabilidade (fácil manutenção)
4. Possuir uma melhor documentação do projeto, de como se espera que o código funcione.

Sem testes a equipe toda irá ter medo de adicionar novas funcionalidades ou de fazer mudanças que trazem benefícios para o código. Assim, leva-se muito mais tempo para fazer alguma alteração, e o código vira um frankeinstein. Com o tempo, o código apodrece, e qualquer mudança leva tempo e faz surgir bugs imprevistos. 

#### **Faça testes suficientes**:

Os testes deem cobrir tudo o que pode vir a quebrar.

#### **Use uma ferramenta para obter a cobertura de testes**

Com as ferramentas de cobertura é mais fácil encontrar lugares do código que ainda não foram suficientemente testados.

#### **Não pule testes triviais**

Eles são faceis de escrever e seu valor de documentação é maior que o custo de escrevê-los.

#### **Entenda a importância do TDD**

Considere as seguintes regras do TDD:

1. Você não deve escrever um teste de produção enquanto não escrever um teste que falhe. 
2. Você não deve escrever mais testes do que o suficiente para falhar um determinado cenário. E não compilar é falhar.
3. Você não deve escrever mais código de produção do que o suficiente para passar o teste que você escreveu.

Se trabalharmos deste modo, iremos criar um ciclo com rápido feedback, onde os testes e o código são escritos **juntos**, validando rapidamente o código que estamos criando. Assim, garantimos que o código tenha praticamente 100% de cobertura e realizamos todos os testes necessários, garantindo os benefícios citados anteriormente.  

_____

# Conclusão

Espero que este resumo tenha esclarecido sobre a importância de um código bem escrito e que desperte o interesse para a leitura completa do livro, que é muito mais aprofundado. Esta lista de dicas e heurísticas está longe de ser completa, e talvez nunca seja, mas é um bom guia para começar a deixar o código mais limpo e legível. 

Que possamos a cada dia nos apaixonar mais pela arte de programar, entendendo sua essência e marchando rumo a excelência,  realizando profissionalmente e transformando nossa área de atuação positivamente.

"*Até agora os filósofos se preocuparam em interpretar o mundo de várias formas. O que importa é transformá-lo. "- Karl Marx*  

Template Method

O Template Method é um padrão de projeto comportamental que define o esqueleto de um algoritmo na superclasse mas deixa as subclasses sobrescreverem etapas específicas do algoritmo sem modificar sua estrutura.

![image](https://user-images.githubusercontent.com/88672689/208714726-4d2e9497-36b9-477b-b0e5-f19003e720e6.png)

Aplicabilidade:

   1. Utilize o padrão Template Method quando você quer deixar os clientes estender apenas etapas particulares de um algoritmo, mas não todo o algoritmo e sua estrutura.

   O Template Method permite que você transforme um algoritmo monolítico em uma série de etapas individuais que podem facilmente ser estendidas por subclasses enquanto ainda mantém intacta a estrutura definida em uma superclasse.

   2. Utilize o padrão quando você tem várias classes que contém algoritmos quase idênticos com algumas diferenças menores. Como resultado, você pode querer modificar todas as classes quando o algoritmo muda.

   Quando você transforma tal algoritmo em um Template Method, você também pode erguer as etapas com implementações similares para dentro de uma superclasse, eliminando duplicação de código. Códigos que variam entre subclasses podem permanecer dentro das subclasses.

Como implementar:

   1. Analise o algoritmo alvo para ver se você quer quebrá-lo em etapas. Considere quais etapas são comuns a todas as subclasses e quais permanecerão únicas.

   2. Crie a classe abstrata base e declare o método padrão e o conjunto de métodos abstratos representando as etapas do algoritmo. Contorne a estrutura do algoritmo no método padrão ao executar as etapas correspondentes. Considere tornar o método padrão como final para prevenir subclasses de sobrescrevê-lo.

   3. Tudo bem se todas as etapas terminarem sendo abstratas. Contudo, alguns passos podem se beneficiar de ter uma implementação padrão. Subclasses não tem que implementar esses métodos.

   4. Pense em adicionar ganchos entre as etapas cruciais do algoritmo.

   5. Para cada variação do algoritmo, crie uma nova subclasse concreta. Ela deve implementar todas as etapas abstratas, mas pode também sobrescrever algumas das opcionais.

Prós:

   1. Você pode deixar clientes sobrescrever apenas certas partes de um algoritmo grande, tornando-os menos afetados por mudanças que acontece por outras partes do algoritmo.

   2. Você pode elevar o código duplicado para uma superclasse.

Contras:

   1. Alguns clientes podem ser limitados ao fornecer o esqueleto de um algoritmo.
 
   2. Você pode violar o princípio de substituição de Liskov ao suprimir uma etapa padrão de implementação através da subclasse.
 
   3. Implementações do padrão Template Method tendem a ser mais difíceis de se manter quanto mais etapas eles tiverem.

# ReciclagemEAprofundamentoC-
Reciclagem e aprofundamento de C# feita no curso da Udemy do Gabriel Artigas Pierri 

### Seção 4: Variáveis, Constantes e tipos de dados
#### Numéricos Inteiros
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoC-/assets/95232367/ed744511-384b-48ec-8c1c-f84b83483a8b)

Integral assinado - suportam números negativos (sbyte, short, int, long)   
Integral sem sinal - não suportem números negativos (byte, ushort, uint, ulong)

#### Numéricos Reais
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoC-/assets/95232367/6c404704-b575-411b-bcf9-33c25083260a)

#### Tipo Caractere
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/afae6138-5827-468b-be60-5c61a9f90838)

#### Tipo String
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/6cd856b8-e7e1-4940-94a6-6719f79cc761)

#### Enums
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/7a4a0c76-14f2-41fd-8b28-1a756261119e)

#### Structs
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/f090d943-b95a-4490-8600-85a4059bcdcd)

É um tipo de dado que permite agrupar diferentes tipos de dados sob um único nome. O principal objetivo das structs é organizar dados relacionados e facilitar a manipulação desses dados como uma unidade.    
Ao contrário das classes, as `structs` são tipos de valor, o que significa que elas são armazenadas diretamente na memória onde são declaradas, em vez de em uma referência alocada no heap. Isso pode ser útil em situações em que você deseja otimizar o desempenho e a eficiência de memória, especialmente para tipos pequenos e imutáveis.  
São úteis quando você tem um conjunto pequeno de dados que faz sentido ser tratado como uma única unidade, e a cópia direta dos dados é preferível à referência. Elas são frequentemente usadas para representar conceitos simples, como coordenadas, cores ou outras estruturas de dados pequenas e imutáveis.

### Seção 5: Entrada e Saída de dados
#### Saída de dados
**Console.WriteLine():**  
```
int idade = 25;
Console.WriteLine("A idade é: " + idade);
```
Este método exibe uma linha de texto no console, seguida por uma quebra de linha.

**Console.Write():**
```
double salario = 3000.50;
Console.Write("O salário é: " + salario);
```
Similar ao Console.WriteLine(), mas não adiciona automaticamente uma quebra de linha.  

#### Entrada de dados
**Console.ReadLine():**  
```
Console.WriteLine("Digite algo:");
string input = Console.ReadLine();
```      
Este método lê uma linha de texto da entrada padrão (normalmente, o console).  

**Console.Read():**  
```
Console.WriteLine("Digite um caractere:");
int charCode = Console.Read();
char character = (char)charCode;
```  
lê o próximo caractere da entrada padrão como um número inteiro. É necessário converter para um caractere, se necessário.  

**Console.ReadKey():**  
```
Console.WriteLine("Pressione uma tecla:");
ConsoleKeyInfo keyInfo = Console.ReadKey();
char keyChar = keyInfo.KeyChar;
```  
Este método aguarda até que uma tecla seja pressionada e retorna informações sobre a tecla pressionada, incluindo o caractere associado.

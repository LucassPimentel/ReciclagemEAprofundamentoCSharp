# ReciclagemEAprofundamentoCSharp
Reciclagem e aprofundamento de C# feita no curso da Udemy do Gabriel Artigas Pierri 

## Seção 4: Variáveis, Constantes e tipos de dados 
### Numéricos Inteiros
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoC-/assets/95232367/ed744511-384b-48ec-8c1c-f84b83483a8b)

Integral assinado - suportam números negativos (sbyte, short, int, long)   
Integral sem sinal - não suportem números negativos (byte, ushort, uint, ulong)

### Numéricos Reais
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoC-/assets/95232367/6c404704-b575-411b-bcf9-33c25083260a)

### Tipo Caractere
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/afae6138-5827-468b-be60-5c61a9f90838)

### Tipo String
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/6cd856b8-e7e1-4940-94a6-6719f79cc761)

### Enums
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/7a4a0c76-14f2-41fd-8b28-1a756261119e)

### Structs
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/f090d943-b95a-4490-8600-85a4059bcdcd)

É um tipo de dado que permite agrupar diferentes tipos de dados sob um único nome. O principal objetivo das structs é organizar dados relacionados e facilitar a manipulação desses dados como uma unidade.    
Ao contrário das classes, as `structs` são tipos de valor, o que significa que elas são armazenadas diretamente na memória onde são declaradas, em vez de em uma referência alocada no heap. Isso pode ser útil em situações em que você deseja otimizar o desempenho e a eficiência de memória, especialmente para tipos pequenos e imutáveis.  
São úteis quando você tem um conjunto pequeno de dados que faz sentido ser tratado como uma única unidade, e a cópia direta dos dados é preferível à referência. Elas são frequentemente usadas para representar conceitos simples, como coordenadas, cores ou outras estruturas de dados pequenas e imutáveis.

## Seção 5: Entrada e Saída de dados   
### Saída de dados
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

### Entrada de dados
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

## Seção 6 - Conversão de tipos de dados
### Conversão implícita de tipos numéricos
As conversões implícitas de tipos numéricos referem-se à capacidade do compilador de converter automaticamente um tipo de dado para outro sem a necessidade de intervenção explícita do programador. **Essas conversões ocorrem quando não há perda de dados e quando a conversão é segura.**  

**De tipos menores para tipos maiores:**
```
int inteiro = 42;
long longo = inteiro;  // Conversão implícita de int para long
```
Nesse caso, a conversão é segura, pois não há perda de dados ao passar de int para long.  

**De ponto flutuante para ponto flutuante de maior precisão:**  
```
float numeroFlutuante = 3.14f;
double numeroDuplo = numeroFlutuante;  // Conversão implícita de float para double
```
Aqui, o valor é convertido implicitamente de float para double.  

**De literais int para outros tipos numéricos:**
```
long numeroLongo = 1000000000000L;  // Literal int sendo implicitamente convertido para long
```
O literal L ao final do número indica que o valor é do tipo long.

**De tipos menores para tipos de ponto flutuante:**
```
int inteiroPequeno = 5;
float numeroFlutuante = inteiroPequeno;  // Conversão implícita de int para float
```
Aqui, o valor inteiro é convertido implicitamente para um número de ponto flutuante.

### Conversão explícita de tipos numéricos
A conversão explícita de tipos numéricos em C# envolve a intervenção explícita do programador para converter um valor de um tipo de dado para outro. Isso é necessário quando há **potencial para perda de dados durante a conversão**, quando você está convertendo de um tipo de dado maior para um menor, ou quando você deseja realizar uma conversão que não é tratada implicitamente pelo compilador.  
Para realizar uma conversão explícita, você utiliza um operador de cast.  
**De tipos maiores para tipos menores:**  
```
long numeroLongo = 1000;
int numeroInteiro = (int)numeroLongo;  // Conversão explícita de long para int
```

Aqui, estamos convertendo explicitamente um long para um int. Se o valor do long for maior do que o intervalo possível para um int, pode ocorrer uma perda de dados.  

**De ponto flutuante para inteiro (truncamento):**  
```
double numeroDuplo = 3.75;
int numeroInteiro = (int)numeroDuplo;  // Conversão explícita de double para int (truncamento)
```
Nesse exemplo, a parte decimal do número double é truncada ao converter para int.   

**De uma enumeração para um tipo numérico:**  
```
enum DiaDaSemana { Domingo, Segunda, Terca, Quarta, Quinta, Sexta, Sabado };
int diaAtual = (int)DiaDaSemana.Quarta;  // Conversão explícita de enum para int
```
Você pode converter uma enumeração para seu valor numérico correspondente.

### Método Parse
O método Parse() é uma função disponível em tipos de dados específicos que permite converter uma representação de string desse tipo em uma instância do tipo correspondente. Geralmente, é usado para converter dados inseridos pelo usuário ou provenientes de fontes de entrada de string em valores dos tipos de dados apropriados.  
Os tipos mais comuns que possuem o método Parse() incluem tipos numéricos, como int, double, float, e tipos relacionados, como DateTime.  

**int.Parse():**
```
string numeroString = "123";
int numeroInteiro = int.Parse(numeroString);
```

**double.Parse():**
```
string numeroDecimalString = "3.14";
double numeroDecimal = double.Parse(numeroDecimalString);
```  

**DateTime.Parse():**
```
string dataString = "2023-11-10";
DateTime data = DateTime.Parse(dataString);
```  
O método Parse() tenta converter a string fornecida para o tipo correspondente. Se a conversão for bem-sucedida, ele retorna o valor convertido. Se a string não for válida para o tipo especificado, uma exceção do tipo FormatException será lançada.
Se houver a possibilidade de a entrada ser inválida, é mais seguro usar métodos como TryParse(), que retornam um booleano indicando se a conversão foi bem-sucedida, e o resultado convertido é retornado através de um parâmetro de saída.  
**TryParse():**
```
string numeroString = "abc";
int numeroInteiro;

if (int.TryParse(numeroString, out numeroInteiro))
{
    // Conversão bem-sucedida, númeroInteiro contém o valor convertido
}
else
{
    // Tratar caso a conversão falhe
}
```
**Isso ajuda a evitar exceções indesejadas em situações em que a string de entrada pode ser inválida para a conversão desejada.**  

### Classe Convert
A classe Convert faz parte do namespace System e oferece métodos estáticos para converter valores entre diferentes tipos de dados. Essa classe é útil quando você precisa realizar conversões explícitas entre tipos primitivos ou converter valores de string para outros tipos de dados.  

**ToByte(object value) e ToByte(string value):**  
```
string byteString = "42";
byte byteValor = Convert.ToByte(byteString);
```

**ToDateTime(object value) e ToDateTime(string value):**  
```
string dataString = "2023-11-10";
DateTime data = Convert.ToDateTime(dataString);
```
Estes são apenas alguns exemplos e existem outros métodos na classe Convert para lidar com diferentes tipos de dados. É importante notar que, assim como com o método Parse(), os métodos na classe Convert podem lançar exceções se a conversão não for possível. Se você precisar de uma abordagem mais segura, pode preferir usar métodos como TryParse() para evitar exceções em casos de conversão mal-sucedida.

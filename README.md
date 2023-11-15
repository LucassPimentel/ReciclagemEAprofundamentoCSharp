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

## Seção 7 - Operadores 
### Operadores aritméticos
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/38731157-289c-4af2-8942-fb0dcc657884)

### Operadores de atribuição
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/9246103e-33ea-4435-9fec-922f1717b364)

### Operadores de igualdade e relacionais
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/b6c80d2e-d1a2-4cd3-8483-3b496ae4f617)

### Operadores lógicos
![image](https://github.com/LucassPimentel/ReciclagemEAprofundamentoCSharp/assets/95232367/a0f5e2b1-6477-4f08-98e3-134ded038e8b)

## Seção 8 - Coleções do tipo Array
### Vetor - Array unidimensional
Array unidimensional é uma estrutura de dados que armazena elementos do mesmo tipo em uma sequência contígua de memória. Ele fornece um meio eficiente de armazenar e acessar múltiplos valores usando um único nome de variável. 
``` 
// Declaração e inicialização de um array de inteiros com 5 elementos
int[] meuArray = new int[5];

// Atribuição de valores aos elementos do array
meuArray[0] = 10;
meuArray[1] = 20;
meuArray[2] = 30;
meuArray[3] = 40;
meuArray[4] = 50;

// OU

var meuArray = new int[]
{
    10,
    20,
    30,
    40,
    50
}; 
```
### Matriz - Array bidimensional
Array bidimensional é uma estrutura de dados que armazena elementos em duas dimensões. Isso significa que você pode acessar os elementos usando dois índices: um para a linha e outro para a coluna.
```
int[,] arrayBidimensional = new int[2, 3];

// Inicializar os elementos individualmente
arrayBidimensional[0, 0] = 1;
arrayBidimensional[0, 1] = 2;
arrayBidimensional[0, 2] = 3;
arrayBidimensional[1, 0] = 4;
arrayBidimensional[1, 1] = 5;
arrayBidimensional[1, 2] = 6;

// OU

//sintaxe de inicialização de array
int[,] arrayBidimensional =
{
    { 1, 2, 3 },
    { 4, 5, 6 }
};
```
**Independente da forma escolhida, você pode acessar os elementos usando a notação de colchetes duplos, como arrayBidimensional[linha, coluna].**        
``` 
// Acessando um elemento específico
int elemento = arrayBidimensional[0, 1]; // Obtendo o valor da primeira linha, segunda coluna (índices 0 e 1)

// OU

int[,] arrayBidimensional =
{
    { 1, 2, 3 },
    { 4, 5, 6 }
};

// Iterando sobre todos os elementos
for (int i = 0; i < arrayBidimensional.GetLength(0); i++) // percorre as linhas
{
    for (int j = 0; j < arrayBidimensional.GetLength(1); j++) // percorre as colunas
    {
        Console.WriteLine($"Elemento [{i}, {j}]: {arrayBidimensional[i, j]}");
    }
}

```
## Seção 9 - Estruturas condicionais
### Estruturas condicionais simples
Estruturas condicionais são usadas para tomar decisões com base em condições específicas.
``` 
// Exemplo de estrutura condicional simples

// Definindo uma variável
int numero = 10;

// Verificando uma condição usando 'if'
if (numero > 0)
{
    Console.WriteLine("O número é positivo.");
}

// O programa continua aqui após o bloco 'if'
Console.WriteLine("Fim do programa.");
```
### Operador ternário
O operador ternário é uma construção compacta e concisa em C# (e em muitas outras linguagens de programação) que permite expressar uma decisão em uma única linha. Ele é uma forma abreviada de escrever uma instrução if-else. 
sintaxe: **condicao ? expressaoSeVerdadeira : expressaoSeFalsa;**    
```
// Exemplo de operador ternário

// Definindo uma variável
int numero = 10;

// Usando o operador ternário para determinar se o número é positivo
string mensagem = (numero > 0) ? "Positivo" : "Não positivo";
 ```
## Seção 10 - Estruturas de controle
### Estrutura Switch-case
A estrutura de controle switch em C# é usada quando você tem várias condições possíveis e deseja executar diferentes blocos de código com base no valor de uma expressão. Ela é uma alternativa mais limpa e legível do que uma série de instruções if-else aninhadas quando você está lidando com múltiplas possibilidades.
``` 
switch (expressao)
{
    case valor1:
        // Código a ser executado se expressao for igual a valor1
        break;

    case valor2:
        // Código a ser executado se expressao for igual a valor2
        break;

    case valor3:
    case valor4:
        // opção combinada, caso sejam valor3 e valor4 executam um comando, evitando duplicação de código.
        break;

    // Pode haver mais casos aqui...

    default:
        // Código a ser executado se nenhum dos casos anteriores for correspondido
        break;
}
```
**É importante notar que, após a execução de um bloco de código de um caso correspondente, a instrução break é usada para sair do switch. Se o break não for usado, a execução continuará nos casos seguintes, o que pode não ser desejado.**        

## Seção 11 - Estruturas de repetição
### Estrutura while
Utilizada para criar um loop que continua executando enquanto uma condição específica é verdadeira.     
**A condição é avaliada antes de cada iteração do loop.**    
``` 
int contador = 1;

// enquanto verdadeiro, continuará sendo executado
while (contador <= 5)
{
    Console.WriteLine(contador);
    contador++;
}
```
**É importante ter cuidado ao usar estruturas de repetição while para evitar loops infinitos. Certifique-se de que a condição do while eventualmente se torne falsa para que o loop possa ser encerrado. Caso contrário, o programa ficará preso em um loop infinito, o que pode levar a problemas de desempenho ou travamento do programa.**

### Estrutura Do While
A estrutura de repetição do-while é semelhante à estrutura while, mas a diferença fundamental está na avaliação da condição. No do-while, o bloco de código é executado pelo menos uma vez, mesmo que a condição seja inicialmente falsa. A avaliação da condição ocorre após a execução do bloco de código.     
``` 
int contador = 1;

do
{
    Console.WriteLine(contador);
    contador++;
} while (contador <= 5);
```    
### Estrutura For
Utilizada para criar loops que têm uma estrutura mais compacta e geralmente são usados quando o número de iterações é conhecido antecipadamente.    
Sintaxe: 
```
for (inicialização; condição; incremento)
{
    // Código a ser executado em cada iteração
}

// Exemplo

for (int i = 1; i <= 5; i++)
{
    Console.WriteLine(i);
}
```
### Estrutura Foreach
Usada para percorrer os elementos de uma coleção, como um array ou uma lista, de uma maneira mais simples e legível. é como um "ajudante de iteração" que torna mais fácil percorrer os elementos de uma coleção.  
A principal vantagem do foreach é a simplicidade. Ele lida automaticamente com a iteração pelos elementos da coleção, tornando o código mais fácil de entender e menos propenso a erros relacionados a índices. É uma escolha conveniente quando você precisa apenas percorrer todos os itens de uma coleção, sem se preocupar com detalhes de índices ou contadores.    
```
string[] cores = { "vermelho", "verde", "azul" };

foreach (string corAtual in cores)
{
    Console.WriteLine(corAtual);
}
```

## Seção 12 - Programação Orientada a Objeto
### O que é Programação Orientada a Objeto    
A Programação Orientada a Objetos (POO) é um paradigma de programação que organiza o código em torno de objetos, que são instâncias de classes. Um objeto é uma estrutura que contém dados (atributos) e métodos (funções) que operam sobre esses dados. O principal objetivo da POO é modelar o mundo real de uma maneira mais natural e eficiente.    
### Classes e Objetos    
#### Classes 
Uma classe é uma estrutura que define um tipo de objeto. Ela serve como um modelo para criar objetos. As classes encapsulam dados (atributos) e comportamentos (métodos) relacionados a um conceito específico.     
 Por exemplo, se estivermos modelando um sistema de gerenciamento de biblioteca, poderíamos ter uma classe Livro:    
``` 
public class Livro
{
    // Atributos
    public string Titulo { get; set; }
    public string Autor { get; set; }
    public int AnoPublicacao { get; set; }

    // métodos
    public void ExibirDetalhes()
    {
        Console.WriteLine($"Livro: {Titulo}, Autor: {Autor}, Ano: {AnoPublicacao}");
    }
}
```
Neste exemplo, a classe Livro possui três atributos (Titulo, Autor, AnoPublicacao), e um método (ExibirDetalhes).    
#### Objetos    
Os objetos são instâncias de uma classe. Eles são criados a partir de uma classe e representam entidades específicas.    
```
class Program
{
    static void Main()
    {
        // Criar objetos da classe Livro
        Livro livro1 = new Livro("C# Programming", "John Doe", 2022);
        Livro livro2 = new Livro("Data Structures", "Jane Smith", 2019);

        // Usar métodos e acessar atributos dos objetos
        livro1.ExibirDetalhes(); // Saída: Livro: C# Programming, Autor: John Doe, Ano: 2022
        livro2.ExibirDetalhes(); // Saída: Livro: Data Structures, Autor: Jane Smith, Ano: 2019
    }
}
```
Neste exemplo, livro1 e livro2 são objetos da classe Livro. Eles têm atributos específicos (como Titulo, Autor e AnoPublicacao) que foram definidos na classe Livro. Cada objeto é independente dos outros e pode ter valores diferentes para esses atributos.    

### Atributos das classes
Os campos são variáveis que pertencem à classe e armazenam dados. Eles são frequentemente definidos com um modificador de acesso (como private, public, protected) para controlar o nível de visibilidade.       
```
public class Livro
{
    // Campos (fields)
    private string titulo;
    private string autor;
    private int anoPublicacao;

    // Outros métodos...
}
```

### Métodos Simples e com Parâmetros
#### Métodos Simples    
Também conhecidos como métodos sem parâmetros, são aqueles que não recebem nenhum dado específico quando são chamados. Eles geralmente realizam uma ação ou cálculo e podem ou não retornar um valor.    
```
public class Exemplo
{
    // Método simples sem parâmetros e sem retorno
    public void ExibirMensagemSimples()
    {
        Console.WriteLine("Esta é uma mensagem simples.");
    }

    // Método simples com retorno
    public int SomarNumeros()
    {
        int resultado = 5 + 3;
        return resultado;
    }
}
```

#### Métodos com Parâmetros
Permitem que você passe dados específicos para serem usados dentro do método. Os parâmetros são variáveis que recebem valores quando o método é chamado.    
```
public class Calculadora
{
    // Método com parâmetros e retorno
    public int Somar(int a, int b)
    {
        int resultado = a + b;
        return resultado;
    }

    // Método com parâmetro e sem retorno
    public void ExibirMensagemPersonalizada(string mensagem)
    {
        Console.WriteLine($"Mensagem: {mensagem}");
    }
}
```

#### Passagem de Parâmetro por Referência    
permite que você passe uma referência à variável original para o método, em vez de apenas o valor. Isso significa que as alterações feitas no parâmetro dentro do método afetarão diretamente a variável original fora do método. Em C#, você usa a palavra-chave `ref` para indicar a passagem por referência.    
```
public class Exemplo
{
    // Método que modifica o valor do parâmetro por referência
    public void ModificarPorReferencia(ref int numero)
    {
        numero = numero * 2;
    }
}
```
**Ao usar o método:**
```
class Program
{
    static void Main()
    {
        Exemplo exemplo = new Exemplo();
        int valor = 5;

        Console.WriteLine($"Antes da modificação: {valor}");

        exemplo.ModificarPorReferencia(ref valor);

        Console.WriteLine($"Depois da modificação: {valor}");
    }
}
```
**Saída:**
```
Antes da modificação: 5
Depois da modificação: 10
```
Observe que, ao chamar o método ModificarPorReferencia, usamos ref antes do parâmetro numero. Isso indica que estamos passando a variável valor por referência, permitindo que o método modifique diretamente o valor da variável original.

É importante notar que a passagem de parâmetro por referência tem implicações em termos de segurança e previsibilidade do código. Ela pode tornar o código mais difícil de entender e manter, pois a modificação de uma variável dentro de um método pode afetar seu estado em outros lugares do programa.    

### Métodos com Retorno de Valores    
São aqueles que realizam alguma operação e retornam um valor específico para o local de onde foram chamados. O valor retornado pode ser de qualquer tipo de dado, como inteiros, strings, objetos, etc. A palavra-chave return é usada para especificar o valor que o método retorna.     
```
public class Calculadora
{
    // Método com retorno de valor (soma de dois números)
    public int Somar(int a, int b)
    {
        int resultado = a + b;
        return resultado;
    }

    // Método com retorno de valor (concatenação de duas strings)
    public string Concatenar(string str1, string str2)
    {
        string resultado = str1 + str2;
        return resultado;
    }
}
```

### Sobrecarga de Métodos (overloading)
É um conceito em programação orientada a objetos que permite que uma classe tenha vários métodos com o mesmo nome, mas com diferentes parâmetros. Cada método na sobrecarga de métodos realiza uma tarefa específica com base nos parâmetros fornecidos.    
```
public class Calculadora
{
    // Método para somar dois inteiros
    public int Somar(int a, int b)
    {
        return a + b;
    }

    // Método para somar três inteiros
    public int Somar(int a, int b, int c)
    {
        return a + b + c;
    }

    // Método para concatenar duas strings
    public string Concatenar(string str1, string str2)
    {
        return str1 + str2;
    }

    // Método para concatenar três strings
    public string Concatenar(string str1, string str2, string str3)
    {
        return str1 + str2 + str3;
    }
}
```
A sobrecarga de métodos é uma maneira poderosa de tornar o código mais flexível e fácil de usar, pois permite que os métodos tenham a mesma semântica (mesmo nome) enquanto operam com diferentes conjuntos de dados. Isso aumenta a legibilidade do código e a capacidade de reutilização.

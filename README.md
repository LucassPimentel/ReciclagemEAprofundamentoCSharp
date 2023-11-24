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

### Termo this
A palavra-chave this é utilizada para se referir à instância atual de uma classe. Ela é usada principalmente para evitar ambiguidades entre membros de uma classe e parâmetros de métodos ou construtores que compartilham o mesmo nome.    
```
public class Exemplo
{
    private int valor;

    public void SetValor(int valor)
    {
        // Usando "this" para distinguir entre o parâmetro e o membro da classe
        // esse "this" referencia a classe Exemplo, logo o this.valor equivale a variável externa
        this.valor = valor;
    }
}    
```

### Delegates
Delegate é um tipo que representa referências a métodos. Ele é frequentemente usado para criar métodos seguros e flexíveis, permitindo que você passe métodos como argumentos para outros métodos, crie callbacks e implemente eventos. É necessário que os métodos tenham a mesma assinatura do delegate.
```
// Definindo um delegate chamado MeuDelegate
public delegate void MeuDelegate(string mensagem);

public class ExemploDelegado
{
    // Um método que se encaixa na assinatura do delegate
    public static void Metodo1(string mensagem)
    {
        Console.WriteLine("Método1: " + mensagem);
    }

    public static void Metodo2(string mensagem)
    {
        Console.WriteLine("Método2: " + mensagem);
    }

public static void Main()
{
        // Instanciando o delegate com o método1
        MeuDelegate delegate1 = new MeuDelegate(Metodo1);

        // Invocando o delegate (chamando o Método1)
        delegate1("Olá, Mundo!");

        // Alterando a referência do delegate para apontar para o Método2
        delegate1 = new MeuDelegate(Metodo2);

        // Invocando o delegate novamente (chamando o Método2)
        delegate1("Hello, World!");

        // Para fazer com que um delegate execute mais de um método em uma única chamada, faça:

        // Instanciando o delegate com o método1
        MeuDelegate delegate1 = Metodo1;

        // Adicionando o método2 ao delegate
        delegate1 += Metodo2;

        // Adicionando o método3 ao delegate
        delegate1 += Metodo3;

        // Invocando o delegate, que executará todos os métodos associados
        delegate1("Olá, Mundo!");
    }
}
```
Os delegates oferecem uma maneira flexível de trabalhar com métodos, permitindo que você os trate como objetos e, assim, forneça uma forma poderosa de implementar padrões como callbacks e eventos. Eles são frequentemente usados em conjunto com eventos para permitir que objetos notifiquem outros objetos sobre a ocorrência de determinados eventos.    

### Método construtor
Construtor é um método especial dentro de uma classe que é chamado automaticamente quando um objeto da classe é criado. O construtor é usado para inicializar os membros da classe e realizar outras operações de inicialização necessárias.     
Sintaxe básica:    
```
public class Pessoa
{
    public string Nome { get; set; }
    public int Idade { get; set; }

    // Construtor padrão
    public Pessoa()
    {
        Nome = "Sem Nome";
        Idade = 0;
    }
}

```
Os construtores desempenham um papel fundamental na criação de objetos e garantem que os objetos sejam configurados corretamente desde o início. Eles são parte integrante da programação orientada a objetos em C#.

### Sobrecarga de construtor (overloading)
É a capacidade de ter múltiplas versões de um construtor em uma classe, cada uma com uma lista diferente de parâmetros. Isso permite que você crie objetos da classe de diferentes maneiras, com base nos argumentos fornecidos ao chamar o construtor.    
A sobrecarga de construtor é útil quando você deseja fornecer flexibilidade na forma como os objetos são inicializados, permitindo que os usuários da sua classe forneçam diferentes conjuntos de parâmetros, conforme necessário. Isso facilita a criação de objetos de uma maneira que seja mais intuitiva ou conveniente para o usuário da classe.    
```
public class ExemploSobrecargaConstrutor
{
    private string nome;
    private int idade;

    // Construtor padrão
    public ExemploSobrecargaConstrutor()
    {
        nome = "Sem Nome";
        idade = 0;
    }

    // Construtor com um parâmetro
    public ExemploSobrecargaConstrutor(string nome)
    {
        this.nome = nome;
        idade = 0;
    }

    // Construtor com dois parâmetros
    public ExemploSobrecargaConstrutor(string nome, int idade)
    {
        this.nome = nome;
        this.idade = idade;
    }
}
```

### Classes estáticas
São classes que não podem ser instanciadas. Os membros estáticos de uma classe estão associados à própria classe em vez de instâncias individuais dessa classe. Isso significa que você pode acessar membros estáticos sem criar uma instância da classe.    
Um exemplo básico:    
```
public static class MinhaClasseEstatica
{
    // Membro de dados estático
    public static int NumeroEstatico = 10;

    // Método estático
    public static void MeuMetodoEstatico()
    {
        Console.WriteLine("Este é um método estático.");
    }
}
```
Acesso:    
```
// Acesso à variável estática
int valor = MinhaClasseEstatica.NumeroEstatico;

// Chamada ao método estático
MinhaClasseEstatica.MeuMetodoEstatico();
```

**Existem algumas características e restrições importantes associadas a classes estáticas em C#:**
1. Não podem ser instanciadas: Você não pode criar uma instância de uma classe estática usando o operador new.
2. Membros devem ser estáticos: Todos os membros de uma classe estática (campos, propriedades, métodos, etc.) devem ser declarados como estáticos.
3. Acesso direto: Os membros estáticos podem ser acessados diretamente através do nome da classe, sem a necessidade de criar uma instância.
4. Inicialização única: Os membros estáticos são inicializados apenas uma vez, geralmente quando a classe é carregada pela primeira vez no aplicativo.
5. Uso comum: As classes estáticas são frequentemente usadas para agrupar funcionalidades relacionadas que não precisam de estado de instância.
6. Utilidade em métodos auxiliares: Métodos estáticos em classes estáticas são frequentemente usados para fornecer funcionalidades auxiliares que não dependem do estado do objeto.

As classes estáticas são úteis para agrupar funcionalidades relacionadas que não exigem estado de instância. Por exemplo, classes utilitárias que fornecem métodos de apoio, como funções de cálculo, manipulação de strings, ou configurações globais.    

### Membros estáticos
Membros estáticos são componentes de uma classe que pertencem à própria classe, em vez de pertencerem a instâncias específicas da classe. Isso significa que, ao contrário dos membros de instância, os membros estáticos são compartilhados entre todas as instâncias da classe e podem ser acessados sem a necessidade de criar uma instância da classe.    
Existem vários tipos de membros estáticos em C#, incluindo campos, métodos, propriedades e construtores.
Campo estático:    
```
public class MinhaClasse
{
    public static int CampoEstatico = 42;
}
```

### Classes parciais (partial)    
Classes parciais (partial classes) permitem dividir a definição de uma classe em várias partes, que podem estar em diferentes arquivos. Cada parte é definida usando a palavra-chave `partial`. Quando o compilador compila o código, ele combina todas as partes da classe em uma única definição de classe.    
A principal finalidade das classes parciais é permitir que diferentes partes de uma classe sejam desenvolvidas, mantidas e estendidas de forma independente. Isso é particularmente útil em cenários onde parte da implementação da classe é gerada automaticamente por uma ferramenta, enquanto outras partes são escritas manualmente.    

```
// Arquivo 1: MinhaClasseParte1.cs
partial class MinhaClasse
{
    public void MetodoParte1()
    {
        Console.WriteLine("Parte 1");
    }
}

// Arquivo 2: MinhaClasseParte2.cs
partial class MinhaClasse
{
    public void MetodoParte2()
    {
        Console.WriteLine("Parte 2");
    }
}

// Arquivo 3: Programa.cs
class Programa
{
    static void Main()
    {
        MinhaClasse instancia = new MinhaClasse();
        instancia.MetodoParte1(); // Saída: Parte 1
        instancia.MetodoParte2(); // Saída: Parte 2
    }
}
```
Neste exemplo, a classe MinhaClasse é dividida em duas partes (MinhaClasseParte1 e MinhaClasseParte2). Ambas as partes são necessárias para criar uma única classe funcional. O compilador do C# combina automaticamente essas partes quando o código é compilado, tratando-as como se fossem uma única definição de classe.    

**Considerações:**
1. Membros Compartilhados: Membros como campos, propriedades e métodos podem ser compartilhados entre as partes da classe.
2. Assinatura Consistente: As partes de uma classe parcial devem ter a mesma assinatura (nome, tipo de retorno, parâmetros) para membros compartilhados.
3. Ordem Não Importante: A ordem em que as partes são definidas não importa.
4. Herança: As partes podem estar em classes base e derivadas.
5. Mesmo Assembly: Todas as partes devem estar no mesmo assembly (arquivo de saída do compilador).    

### Propriedades da classe (get - set)
São membros de uma classe que permitem acessar ou modificar valores de campos privados de maneira controlada. As propriedades são frequentemente usadas para encapsular o acesso aos campos, permitindo que você defina lógica personalizada (como validações) ao ler ou escrever valores. As propriedades geralmente consistem em dois métodos chamados get e set.    
```
public class ExemploClasse
{
    // Propriedade automática
    public int MinhaPropriedade { get; set; }

    // você também pode alterar se o campo poderá ser escrito ou somente lido

    // somente leitura
    public int MinhaPropriedade { get; }

    // pode ser escrito e lido
    public int MinhaPropriedade { get; set; }

}
```    
Em resumo, as propriedades em C# oferecem uma maneira de encapsular campos e fornecer acesso controlado a eles, permitindo que você defina lógica personalizada ao ler ou escrever valores. As propriedades são uma parte fundamental do conceito de encapsulamento em programação orientada a objetos.    

### Encapsulamento   
O encapsulamento é um dos princípios fundamentais da programação orientada a objetos (POO). Ele refere-se à ideia de agrupar os dados (campos) e os métodos (operações) que operam nesses dados em uma única unidade chamada classe. Além disso, o encapsulamento implica na restrição do acesso direto aos detalhes internos da implementação da classe, exigindo que a interação com os objetos seja realizada por meio de interfaces públicas bem definidas.    
Em C#, o encapsulamento é implementado usando modificadores de acesso, como `public`, `private`, `protected` e `internal`, para controlar o acesso aos membros de uma classe.    
```
public class ExemploClasse
{
    // Campo privado
    private int _meuDado;

    // Propriedade pública
    public int MinhaPropriedade
    {
        get { return _meuDado; }
        set { _meuDado = value; }
    }

    // Método público
    public void MeuMetodo()
    {
        // Lógica do método
    }
}
```
Chamada:
```
ExemploClasse objeto = new ExemploClasse();

// Acesso a propriedade pública
objeto.MinhaPropriedade = 42;

// Chamada a método público
objeto.MeuMetodo();
```
O encapsulamento ajuda a 'esconder' a complexidade interna de uma classe e promove um design mais modular, onde as interações são realizadas por meio de interfaces públicas bem definidas. Essa abordagem facilita a manutenção do código, já que as alterações internas em uma classe não afetam o código que a utiliza, desde que a interface pública permaneça consistente.    

### Herança
A herança é um dos conceitos fundamentais da programação orientada a objetos (OOP) que permite que uma classe herde características (campos e métodos) de outra classe. Isso permite a criação de uma hierarquia de classes, onde as classes derivadas (ou subclasses) herdam as propriedades e comportamentos da classe base (ou superclasse). A herança promove a reutilização de código e facilita a criação de hierarquias de classes que refletem a estrutura do problema que está sendo modelado.        
```
// Classe base (superclasse)
public class Animal
{
    public void Comer()
    {
        Console.WriteLine("O animal está comendo.");
    }
}

// Classe derivada (subclasse)
public class Mamifero : Animal
{
    public void Amamentar()
    {
        Console.WriteLine("O mamífero está amamentando.");
    }
}
```
1. Herança de Métodos e Campos: A classe derivada herda todos os métodos e campos públicos e protegidos da classe base. No exemplo acima, a classe Mamifero herda o método Comer da classe Animal.
2. Adição de Novos Membros: Além de herdar membros da classe base, a classe derivada pode adicionar novos membros, como métodos ou campos adicionais.
3. Sobrescrita de Métodos: Uma classe derivada pode substituir (sobrescrever) um método da classe base usando a palavra-chave override. Isso permite que a classe derivada forneça uma implementação específica para esse método.
```
// Sobrescrita de método
public class Cachorro : Mamifero
{
    public override void Comer()
    {
        Console.WriteLine("O cachorro está comendo ração.");
    }
}
```
C# não suporta herança múltipla de classes, ou seja, uma classe não pode herdar diretamente de mais de uma classe. No entanto, você pode implementar herança múltipla por meio de interfaces.    
Exemplo:    
```
public interface IFelino
{
    void Rugir();
}

public class Leao : Animal, IFelino
{
    public void Rugir()
    {
        Console.WriteLine("O leão está rugindo.");
    }
}
```        
A herança é uma ferramenta poderosa, mas deve ser usada com cuidado. É importante garantir que a hierarquia de classes faz sentido do ponto de vista do modelo de domínio, evitando hierarquias profundas e excessivamente complexas. O uso adequado de herança contribui para um design mais flexível, modular e fácil de entender.    

### Classes abstratas    
Uma classe abstrata em C# é uma classe que não pode ser instanciada diretamente e que pode conter membros abstratos. Membros abstratos são métodos que são declarados na classe abstrata, mas não fornecem uma implementação. A implementação desses membros é deixada para as classes derivadas. Classes abstratas fornecem uma base para outras classes e são frequentemente usadas para criar hierarquias de classes.    
Pontos importantes:    
1. Declaração de uma Classe Abstrata: use a palavra-chave `abstract` para declarar uma classe abstrata. Uma classe abstrata pode conter métodos abstratos (sem implementação), bem como métodos concretos (com implementação).
```
public abstract class Animal
{
    // Método abstrato
    public abstract void EmitirSom();

    // Método concreto
    public void Dormir()
    {
        Console.WriteLine("O animal está dormindo.");
    }
}
```
2. Membros Abstratos: membros abstratos são marcados com a palavra-chave `abstract` e não fornecem uma implementação na classe abstrata. As classes derivadas devem fornecer uma implementação para esses membros.    
```
public abstract class Animal
{
    // Método abstrato
    public abstract void EmitirSom();
}

public class Cachorro : Animal
{
    // Implementação do método abstrato
    public override void EmitirSom()
    {
        Console.WriteLine("O cachorro está latindo.");
    }
}
```

3. Instanciação e Herança: não é possível criar uma instância de uma classe abstrata. Você deve criar uma classe derivada não abstrata e, em seguida, instanciar essa classe.
```
Animal animal = new Cachorro();
animal.EmitirSom(); // Chama a implementação de Cachorro
```

As classes abstratas são valiosas quando você quer definir uma estrutura comum para um grupo de classes relacionadas, enquanto ainda permite a personalização através da implementação de membros abstratos nas classes derivadas. Isso facilita a criação de hierarquias de classes mais flexíveis e reutilizáveis.    

### Classes sealed
A palavra-chave sealed é usada para restringir a herança de uma classe. Quando uma classe é marcada como sealed, ela não pode ser usada como classe base para outras classes. Em outras palavras, você não pode derivar uma nova classe a partir de uma classe sealed.    
```
// classe selada
public sealed class MinhaClasseSelada
{
    // Membros da classe
}

// Isso gerará um erro de compilação
public class MinhaClasseDerivada : MinhaClasseSelada
{
    // Membros da classe derivada
}

```
Essa restrição pode ser útil em alguns casos. Por exemplo, se você tem uma classe que fornece funcionalidades completas e não deseja que outras classes herdem dela para estender ou modificar seu comportamento, você pode marcá-la como sealed. Isso ajuda a garantir que a implementação original não seja alterada ou estendida inadvertidamente.    

### Membros sealed
Além de poder selar uma classe, é possível selar membros específicos dentro de uma classe usando a palavra-chave sealed. Essa abordagem permite que você impeça que métodos, propriedades ou indexadores sejam sobrescritos em classes derivadas. O uso de sealed em membros é comumente aplicado a métodos, mas também pode ser usado em propriedades e indexadores.    
```
public class MinhaClasseBase
{
    public virtual void MetodoBase()
    {
        Console.WriteLine("Método base.");
    }
}

public class MinhaClasseDerivada : MinhaClasseBase
{
    public sealed override void MetodoBase()
    {
        Console.WriteLine("Método na classe derivada, selado.");
    }
}

public class MinhaClasseFilha : MinhaClasseDerivada
{
    // Tentar sobrescrever o método selado gerará um erro de compilação.
    // public override void MetodoBase() { } 
}
```
Neste exemplo: 
- MinhaClasseBase define um método virtual chamado MetodoBase.
- MinhaClasseDerivada herda de MinhaClasseBase e sobrescreve o método, marcando-o como sealed.
- MinhaClasseFilha tenta sobrescrever o método MetodoBase, mas isso resultaria em um erro de compilação, pois o método na classe base já foi selado.
  
Isso é útil quando você quer garantir que determinados métodos (ou outros membros) não sejam alterados nas classes derivadas além de um certo ponto na hierarquia de herança.

### Modificadores de acesso    
Modificadores de acesso são palavras-chave que definem a visibilidade e acessibilidade de classes, membros de classes (como campos, métodos, propriedades etc.) e outros elementos em um programa. Os principais modificadores de acesso são:    
1. `public`: Um membro declarado como público é acessível de qualquer lugar. Isso significa que ele pode ser acessado por qualquer classe ou código que tenha uma referência para o tipo que contém o membro público.
2. `private`: Um membro declarado como privado só é acessível dentro da própria classe em que foi declarado. Isso é fundamental para o encapsulamento, impedindo que detalhes internos da implementação sejam acessados diretamente de fora da classe.
3. `protected`: Um membro declarado como protegido é acessível dentro da própria classe e por classes derivadas. Ele não pode ser acessado de fora da classe ou de classes que não são derivadas.
4. `internal`: Um membro declarado como interno é acessível dentro do mesmo assembly. Um assembly em C# é, geralmente, um arquivo DLL ou EXE.
5. `protected internal`: Combina as características de protegido e interno. O membro é acessível dentro do mesmo assembly e por classes derivadas, independentemente de estarem no mesmo assembly ou não.
6. `private protected`: Introduzido no C# 7.2, este modificador é semelhante ao protected internal, mas apenas permite acesso em classes derivadas no mesmo assembly.

### Polimorfismo
O polimorfismo é um conceito importante em programação orientada a objetos que se traduz para "muitas formas" e permite que objetos de diferentes tipos sejam tratados de maneira uniforme. Isso ocorre por meio de dois tipos principais de polimorfismo: polimorfismo de subtipo (ou polimorfismo de herança) e polimorfismo de sobrecarga.    

#### Polimorfismo de Subtipo (Herança):
No polimorfismo de subtipo, objetos de classes derivadas podem ser tratados como objetos da classe base. Isso significa que você pode usar uma classe base para se referir a instâncias de suas classes derivadas.    
```
public class Animal
{
    public virtual void FazerSom()
    {
        Console.WriteLine("Algum som de animal.");
    }
}

public class Cachorro : Animal
{
    public override void FazerSom()
    {
        Console.WriteLine("Latindo...");
    }
}

public class Gato : Animal
{
    public override void FazerSom()
    {
        Console.WriteLine("Miando...");
    }
}

class Program
{
    static void Main()
    {
        Animal meuAnimal = new Cachorro();
        meuAnimal.FazerSom(); // Resultado: Latindo...

        meuAnimal = new Gato();
        meuAnimal.FazerSom(); // Resultado: Miando...
    }
}
```
Neste exemplo, Cachorro e Gato são classes derivadas de Animal. Mesmo que a variável meuAnimal seja declarada como do tipo Animal, ela pode referenciar instâncias tanto de Cachorro quanto de Gato, e a chamada ao método FazerSom() invoca a implementação específica da classe real do objeto.    

#### Polimorfismo de Sobrecarga (Interfaces ou Métodos com Mesmo Nome):
No polimorfismo de sobrecarga, diferentes classes ou interfaces podem ter métodos com o mesmo nome, mas com implementações diferentes.    
```
public interface IForma
{
    void Desenhar();
}

public class Circulo : IForma
{
    public void Desenhar()
    {
        Console.WriteLine("Desenhando um círculo.");
    }
}

public class Quadrado : IForma
{
    public void Desenhar()
    {
        Console.WriteLine("Desenhando um quadrado.");
    }
}

class Program
{
    static void Main()
    {
        IForma forma = new Circulo();
        forma.Desenhar(); // Resultado: Desenhando um círculo.

        forma = new Quadrado();
        forma.Desenhar(); // Resultado: Desenhando um quadrado.
    }
}
```
Neste exemplo, Circulo e Quadrado implementam a interface IForma. Apesar de terem o mesmo método Desenhar(), cada classe fornece sua própria implementação. No entanto, você pode tratar objetos dessas classes como objetos da interface IForma, permitindo que você os use de forma polimórfica.    

O polimorfismo torna o código mais flexível e extensível, facilitando a adição de novos tipos sem alterar o código existente. Ele é uma parte fundamental do paradigma de programação orientada a objetos.

## Seção 14 - Windows Forms App
O Windows Forms App é uma tecnologia de desenvolvimento de aplicativos para o sistema operacional Windows, fornecida pela Microsoft. Ele faz parte do conjunto de ferramentas de desenvolvimento chamado Windows Forms, que permite a criação de interfaces gráficas de usuário (GUI) para aplicativos Windows.    

### Propriedades das Forms    
No contexto do desenvolvimento de software com Windows Forms, uma "Form" (ou formulário) é uma janela ou tela na qual você pode projetar a interface do usuário para interagir com o aplicativo. As Forms no Windows Forms App têm várias propriedades que podem ser configuradas para controlar seu comportamento e aparência.     
**Por exemplo:**    
1. Name (Nome): Define um identificador único para a Form, permitindo referenciar o formulário em código.
2. Text (Texto): Especifica o texto que aparecerá na barra de título da Form.
3. Size (Tamanho): Define a largura e altura da Form em pixels.
4. StartPosition (PosiçãoInicial): Determina onde a Form será exibida na inicialização. Pode ser configurado para exibir no centro da tela, na posição padrão ou em uma posição específica.
5. BackColor (CorDeFundo): Define a cor de fundo da Form.
6. ForeColor (CorDoTexto): Define a cor do texto na Form.
7. Icon: Especifica o ícone que aparecerá na barra de título da Form.
8. MaximizeBox (MaximizarCaixaDeControle): Indica se o botão de maximizar deve ser exibido na barra de título.
9. MinimizeBox (MinimizarCaixaDeControle): Indica se o botão de minimizar deve ser exibido na barra de título.
10. ControlBox (CaixaDeControle): Indica se a caixa de controle (que contém os botões Minimizar, Maximizar e Fechar) deve ser exibida.
11. FormBorderStyle (EstiloDeBorda): Define o estilo de borda da Form, como janela normal, sem borda, borda fixa, etc.
12. TopMost: Determina se a Form deve ser exibida como a janela superior, mesmo se não estiver ativa.    

Essas são apenas algumas das propriedades disponíveis para configurar uma Form no Windows Forms. Cada propriedade oferece controle sobre diferentes aspectos do comportamento e da aparência da interface do usuário do aplicativo.    

### Eventos das Forms    
Em uma aplicação Windows Forms, eventos são ações ou ocorrências que podem ser detectadas e tratadas durante a execução do programa. Os eventos nas Forms são usados para responder a interações do usuário ou a mudanças de estado no aplicativo.     
1. Load: O evento Load ocorre quando a Form é carregada pela primeira vez na memória. É frequentemente usado para realizar inicializações e configurações iniciais.
```
private void Form1_Load(object sender, EventArgs e)
{
    // Código a ser executado quando a Form é carregada.
}
```

2. Click: O evento Click ocorre quando um controle é clicado pelo usuário. Pode ser associado a botões, caixas de texto, e outros controles interativos.        
```
private void button1_Click(object sender, EventArgs e)
{
    // Código a ser executado quando o botão é clicado.
}
```

3. Closing e Closed: O evento Closing ocorre antes da Form ser fechada, enquanto o evento Closed ocorre após a Form ter sido fechada. Pode ser usado para realizar operações de limpeza ou salvar dados antes que a aplicação seja encerrada.        
```
private void Form1_Closing(object sender, CancelEventArgs e)
{
    // Código a ser executado antes do fechamento da Form.
}

private void Form1_Closed(object sender, EventArgs e)
{
    // Código a ser executado após o fechamento da Form.
}
```
Esses são apenas alguns exemplos de eventos disponíveis em uma Form no Windows Forms. Cada evento permite que você associe código personalizado para lidar com interações do usuário ou alterações de estado.

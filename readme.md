# Atividade Ponderada - Semana 6

No repositório foi criado um código padrão, e nele apliquei alguns tipos de testes, como o MSTest, NUnit e xUnit.

## Conteúdo
### Testes xUnit
#### Descrição

xUnit é um framework de teste flexível e extensível para .NET. Ele usa atributos para marcar métodos de teste e fornece funcionalidade rica para asserções.

![teste_xunit](/assets/xunit_test.png)

##### Casos de uso

- Teste do ponto de congelamento: 

Cenário: Convertendo 32°F para Celsius.
Resultado Esperado: 0°C

Código: 

`[InlineData(32, 0)]
public void TestarConversaoTemperatura(double fahrenheit, double celsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(fahrenheit);
    Assert.Equal(celsius, valorCalculado);
}`

- Teste valor randômico:

Cenário: Convertendo 90.5°F para Celsius.
Resultado Esperado: 32.5°C

`[InlineData(90.5, 32.5)]
public void TestarConversaoTemperatura(double fahrenheit, double celsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(fahrenheit);
    Assert.Equal(celsius, valorCalculado);
}`

### Testes MSTest
#### Descrição

MSTest é um framework de teste suportado pela Microsoft e totalmente integrado ao Visual Studio. Ele permite a criação de casos de teste automatizados com atributos para métodos e classes de teste.

![teste_mstest](/assets/mstest_test.png)

##### Casos de uso

- Teste do ponto de congelamento:

Cenário: Convertendo 32°F para Celsius.
Resultado Esperado: 0°C

`[DataRow(32, 0)]
[DataTestMethod]
public void TesteConversaoTemperatura(double tempFahrenheit, double tempCelsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(tempFahrenheit);
    Assert.AreEqual(tempCelsius, valorCalculado);
}`

- Teste valor randômico:

Cenário: Convertendo 90.5°F para Celsius.
Resultado Esperado: 32.5°C

`[DataRow(90.5, 32.5)]
[DataTestMethod]
public void TesteConversaoTemperatura(double tempFahrenheit, double tempCelsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(tempFahrenheit);
    Assert.AreEqual(tempCelsius, valorCalculado);
}`

### Testes NUnit
#### Descrição

NUnit é um framework de teste amplamente utilizado para aplicações .NET. Ele permite a criação de casos de teste automatizados usando uma sintaxe simples baseada em atributos. O NUnit suporta diversas asserções e fornece uma estrutura flexível para a execução de testes unitários.

![teste_nunit](/assets/nunit_test.png)

##### Casos de uso

- Teste do ponto de congelamento:

Cenário: Convertendo 32°F para Celsius.
Resultado Esperado: 0°C

`[TestCase(32, 0)]
public void TesteConversaoTemperatura(double tempFahrenheit, double tempCelsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(tempFahrenheit);
    Assert.AreEqual(tempCelsius, valorCalculado);
}` 

- Teste valor randômico:

Cenário: Convertendo 90.5°F para Celsius.
Resultado Esperado: 32.5°C

`[TestCase(90.5, 32.5)]
public void TesteConversaoTemperatura(double tempFahrenheit, double tempCelsius)
{
    double valorCalculado = ConversorTemperatura.FahrenheitParaCelsius(tempFahrenheit);
    Assert.AreEqual(tempCelsius, valorCalculado);
}`
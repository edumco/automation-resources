# Como escrever um bom teste unitário

Um teste unitário é aquele que testa apenas uma pequena parte do código e verifica seu funcionamento.

O tamanho do código a ser testado varia de acordo com a linguagem e arquitetura mas de forma **simplificada** na programação orientada a objetos uma classe ou método pode ser vista como uma unidade.

O teste unitário verifica somente a funcionalidade, ou seja, se o programa faz as ações esperadas nos cenários de sucesso e nos fluxos alternativos. Verificar a comunicação, a performance ou qualquer outra carecteristica é papel de outros tipos de teste.

Esta é apenas uma lista resumida das principais práticas de escrita de teste unitário e está organizada em forma de mnemônicos baseados no livro **Pragmatic Unit Testing in Java 8 with JUnit**.

## O básico

Simples, fáceis de entender, seguem nomenclatura, seguem padrão Arrange, Act, Assert

## FIRST

### Fast

> Executa em alguns milisegundos. Suite executa em 10 segundos ou menos!

Para manter os testes rápidos mantenha um **design limpo**:

- Evite chamar trechos de código que são lentos; (pré-calcule)
- Refatore métodos longos;
- Ao invés de consultar receba valores por argumento (injeção e inversão)

### Isolated

> Foca em um pedaço pequeno de código.

Para manter o teste isolado remova as seguintes dependências:

- Chamadas a outros sistemas;
- Chamadas a outros **testes**;
- Código a ser testado chamando outros sistemas.

### Repeateble

> Encontra os mesmos resultados não importa quantas vezes ou como você o execute.

Para um teste ser reproduzível é necessário remover as seguintes dependências:

- Tempo de resposta. (se vc está esperando respostas não é um teste unitário)
- Tempo de execução. (tempo de execução é teste de performance)
- Configurações externas. (cada teste deve fazer sua própria configuração)

### Self-validating

> Verifica **sozinho** se as coisas aconteceram como esperado.

Para ser independente de interferencia humana é necessário automatizar:

- A configuração do sistema;
- A criação de dados de teste;
- A limpeza de recursos impactados pelo teste;
- Quando os testes serão executados; (Infinitest + git hooks + CI Server)
- A manutenção de boas práticas.

### Timely (Oportuno)

É escrito a tempo de causar impacto no código. (Durante o desenvolvimento)

#### Em código antigo

- Escrever testes imediatamente antes de refatorar;
- Selecionar um trecho PEQUENO de código para refatorar;

#### Em código novo

- Intercalar os testes com o desenvolvimento (mesmo que não se use TDD);
- Reduzir a quantidade de código escrito sem testes.

## Right-BICEP

Right    Right Results
B        Boundary conditions
I        Inverse relationship
C        Cros-check results
E        Error conditions
P        Performance within bounds

### Right Results

Verifica o caminho feliz e garante que o código faz ao menos esse caminho corretamente.

É o primeiro teste que deve ser garantido.

### Boundary conditions

Verifica se os limites dos intervalos de valores (início e fim) são respeitados, seja na entrada ou saída de dados.

Todo tipo de dado é finito e cada "campo" possui restrições e faixas de valores válidos e inválidos.

Valores inconsistentes com o tipo = letras no lugar de números
Dados mal formatados = casas decimais, espaços, pontuação
Overflow = operações que geram números grandes
Variáveis vazias ou nulas = Divisão por zero, null pointer, arquivos que não existem
Listas inconsistentes = duplicação, ordem
Ordem cronológica de ações = Chamadas fora de ordem, concorrência

### Inverse relationship

Verifica se a operção inversa desfaz ou traz resultado diferente.

Soma             Subtração
Multiplicação    Divisão
Potencia         Raiz
...

### Cros-check results

Verifica por outros meios se a reposta está correta.

Podemos usar uma implementação diferente para garantir a consistência como por exemplo uma lib de outro software.

### Error conditions

Verifica se ao forçar uma condição de erro o programa tem uma resposta adequada.

Falta de memória
Falta de espaço em disco
Mudanças no relógio do sistema
Rede
Carga
Incompatibilidades

### Performance within bounds

Verifica se o código está dentro de um limite razoável

- Versão nova está 2x mais lenta
- Teste é 20% mais lento que a média dos testes unitários
- Teste demora mais de 800ms pra executar

---
A importancia dos testes unitários na melhoria continua.

permite identificar efeitos colaterais
Facilita o refectoring

A importancia do refactoring pros testes unitários

Gerar unidades concisas de teste

---

## Referências

LANGR, Jeff. **Pragmatic Unit Testing in Java 8 with JUnit**

NICOLETTE, Dave. **Continuous Unit Checking: Part Three**
https://www.leadingagile.com/2018/07/continuous-unit-checkingpart-three/

NIELSEN, Jakob. **Powers of 10: Time Scales in User Experience**
https://www.nngroup.com/articles/powers-of-10-time-scales-in-ux/

ONOFRIO, Thayse; LOURENÇO, Marilene. **Demystifying the software engineering test pyramid. Agile & other ways of working**
https://leaddev.com/agile-other-ways-working/demystifying-software-engineering-test-pyramid

SEEMANN, Mark. **TDD test suites should run in 10 seconds or less**
https://blog.ploeh.dk/2012/05/24/TDDtestsuitesshouldrunin10secondsorless/

VOCKE, Ham Vocke. **The Practical Test Pyramid**
https://martinfowler.com/articles/practical-test-pyramid.html

# Calculadora com Pilhas de Operadores e Operandos

## Identificação

- **Aluno:** Samuel Araujo
- **RA:** 210025640
- **Curso:** Engenharia da Computação
- **Instituição:** UNISAL — Campus Campinas, Unidade São José

## Descrição do projeto

Aplicativo Android (Kotlin + Jetpack Compose) que implementa uma calculadora
utilizando a estrutura de **pilhas de operadores e operandos** apresentada em
aula para o tratamento das operações.

As operações binárias (soma, subtração, multiplicação, divisão, potenciação e
percentual) são resolvidas empilhando o operador e o operando pendentes e
processando-os quando o próximo operador ou o `=` é pressionado. As operações
unárias (seno, cosseno, tangente, raiz quadrada, inverso e fatorial) atuam
diretamente sobre o valor exibido no visor, sem uso da pilha.

## Operações implementadas

**Operações binárias (com pilha):**
- Soma (`+`)
- Subtração (`-`)
- Multiplicação (`*`)
- Divisão (`/`)
- Potenciação (`^`)
- Percentual (`%`, implementado como resto da divisão)

**Operações unárias (direto no visor):**
- Seno (`Sin`) — ângulo em graus
- Cosseno (`Cos`) — ângulo em graus
- Tangente (`Tan`) — ângulo em graus
- Raiz quadrada (`Sqrt`)
- Inverso (`Inv`) — `x⁻¹ = 1 / x`
- Fatorial (`!`)
- Constante Pi (`Pi`) — inserida como `3,14`

**Controles:**
- Igualdade (`=`)
- Limpar (`C`)
- Apagar último dígito (`<-`)
- Trocar sinal (`+/-`)

## Tratamento de situações inválidas

O aplicativo trata os seguintes casos sem encerrar inesperadamente,
exibindo `Erro` no visor:

- Divisão por zero
- Percentual por zero
- Raiz quadrada de número negativo
- Fatorial de número negativo, não inteiro ou grande demais
- Inverso de zero
- Qualquer resultado inválido (`NaN`/infinito)

Ao digitar um novo número após um erro, o visor é reiniciado normalmente.

## Estrutura do código

- Pacote: `br.com.unisal.samuelaraujo.calculadora`
- `MainActivity.kt`: contém a interface (Jetpack Compose) e toda a lógica de
  negócio da calculadora, incluindo:
  - `pilhaOperador` / `pilhaOperando`: pilhas usadas nas operações binárias
  - `numPress`: tratamento da entrada de dígitos
  - `opPress`: despacho das operações (binárias via pilha, unárias direto no visor)
  - `igualdade`: resolve o topo da pilha
  - `visorParaDouble` / `doubleParaVisor`: conversão entre o texto do visor
    (que usa vírgula como separador decimal) e `Double`

## Como executar

1. Abra a pasta do projeto no Android Studio
2. Aguarde a sincronização do Gradle
3. Execute em um emulador ou dispositivo físico

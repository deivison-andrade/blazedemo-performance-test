#  Teste de Performance - BlazeDemo

## Objetivo

Validar se o sistema suporta **250 requisições por segundo** com **tempo de resposta P90 inferior a 2 segundos**.

---

##  Ferramenta utilizada

* Apache JMeter

---

##  Cenário testado

Fluxo completo de compra:

* Acesso à home
* Seleção de voo
* Compra da passagem

---

##  Resultados obtidos

* Total de requisições: 1500
* Tempo médio: 885 ms
* Tempo máximo: 3093 ms
* Taxa de erro: 0%
* Throughput: 43.5 requisições/segundo

### Análise por etapa:

* Home: média de 1774 ms (maior latência)
* Seleção de voo: média de 447 ms
* Compra: média de 434 ms

---

##  Validação do critério de aceitação

Critério:

* 250 req/s
* P90 < 2000 ms

### Resultado:

* ✔ Sistema apresentou estabilidade (0% de erro)
* ❌ Vazão não atingiu o esperado (43.5 req/s < 250 req/s)
* ❌ Tempo máximo ultrapassou o limite esperado

---

##  Conclusão

O sistema demonstrou boa estabilidade e tempos de resposta aceitáveis na maior parte do fluxo, porém não foi possível atingir a vazão de 250 requisições por segundo.

Além disso, foi identificado que a requisição inicial (home) apresenta maior latência, podendo ser um possível gargalo na aplicação.

---

##  Possíveis causas

* Limitação do ambiente local de teste
* Capacidade limitada do servidor BlazeDemo
* Configuração de carga ainda insuficiente

---

##  Considerações finais

O teste foi executado simulando o fluxo completo do usuário, garantindo maior fidelidade ao comportamento real.

Para análises mais aprofundadas, seria recomendada a utilização de um ambiente controlado e aplicação de técnicas como distribuição de carga e correlação de dados dinâmicos.



##  Como executar o teste de performance localmente (JMeter)

Siga o passo a passo abaixo para rodar o projeto na sua máquina:

---

###  Pré-requisitos

Antes de começar, você precisa ter instalado:

* Java (JDK 8 ou superior)
* Apache JMeter

---

### 1. Baixar o projeto

Clone o repositório:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

Acesse a pasta:

```bash
cd seu-repositorio
```

---

###  2. Abrir o projeto no JMeter

1. Abra o Apache JMeter
2. Clique em **File → Open**
3. Navegue até a pasta do projeto
4. Selecione o arquivo:

```bash
test-plan/blazedemo.jmx
```

---

###  3. Configurar o relatório (opcional, mas recomendado)

1. Clique no listener **"Relatório de Sumário"** ou **"Relatório Agregado"**
2. No campo **"Nome do arquivo"**, informe:

```bash
reports/results.jtl
```

---

### ▶ 4. Executar o teste

Clique no botão **Start (▶️)** dentro do JMeter

---

###  5. Visualizar os resultados

Após a execução:

* Os resultados serão salvos em:

```bash
reports/results.jtl
```

* Você também pode visualizar diretamente nos listeners do JMeter:

  * Relatório de Sumário
  * Relatório Agregado
  * Ver Árvore de Resultados

---



## Autor 


Deivison Andrade

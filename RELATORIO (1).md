# Relatório — Ponderada 1 · Circuito RC de carga

**Aluno:** Eduardo Gabriel de Oliveira · eduardo.oliveira2@sou.inteli.edu.br
**Turma:** T26 · **Bancada:** G04
**Previsão registrada em:** 19/10/2026, 11:24:57 · último registro: 19/10/2026, 11:36:19 · alterada em: 19/10/2026, 11:30:24
**Primeiro dado registrado em:** 19/10/2026, 11:21:05 · **atenção: previsão registrada ou alterada depois do primeiro dado**

## 1. Contextualizar (previsão)
| Grandeza | Valor |
|---|---|
| R nominal | 23000 Ω |
| C nominal | 10 µF |
| Tolerância de fábrica | entre os resistores varia de ente 1% e 5% dependendo do fabricante, ja o capacitor entre 10% e 20% também dependendo do capacitor |
| Tensão da fonte V_S | 5 V |
| τ teórico (aluno) | 230 ms |
| Conta | 23000 Ω × 10 µF = 230 ms |
| V_C esperada em t = τ | 3.16 V |
| Tolerância aceitável | 25 % |

**Justificativa da tolerância:** Adotei uma tolerância aceitável de 25%, considerando as possíveis variações dos valores nominais dos resistores e do capacitor, além das limitações de precisão do conversor analógico do Arduino e dos intervalos de amostragem. Essa margem será utilizada para avaliar a diferença entre a constante de tempo teórica e a experimental.

Curva esperada: V_C(t) = 5 · (1 − e^(−t / 230 ms)). A curva teórica aparece no gráfico da etapa 4.

## 2. Consultar
- **Ferramenta:** ChatGPT
- **Pergunta (exata):** Por que a tensão do capacitor aumenta aos poucos, em vez de chegar a 5 V imediatamente? Como podemos calcular esse aumento ao longo do tempo?
- **O que acrescentou:** Entendi melhor por que a carga do capacitor é mais rápida no começo e vai ficando mais lenta. Também compreendi que a constante de tempo indica quando a tensão chega a aproximadamente 63,2% do valor final.

## 3. Construir (dados da bancada)
- **Instrumento:** Arduino Uno, entrada analógica A0 (ADC de 10 bits), com visualização no LCD 16x2 I2C.
- **V_S medida (final estabilizada):** 4922 V
- **Pontos:** 60 · 27 até 1 τ teórico

| # | t (ms) | V_C medido (V) | V_C teórico (V) | Desvio (V) |
|---:|---:|---:|---:|---:|
| 1 | 0 | 0,005 | 0,000 | 0,005 |
| 2 | 0 | 0,005 | 0,007 | -0,002 |
| 3 | 1 | 0,029 | 0,029 | 0,000 |
| 4 | 3 | 0,068 | 0,064 | 0,004 |
| 5 | 5 | 0,112 | 0,114 | -0,002 |
| 6 | 8 | 0,176 | 0,176 | -0,000 |
| 7 | 12 | 0,249 | 0,252 | -0,003 |
| 8 | 16 | 0,332 | 0,340 | -0,008 |
| 9 | 21 | 0,430 | 0,439 | -0,009 |
| 10 | 27 | 0,533 | 0,549 | -0,016 |
| 11 | 33 | 0,650 | 0,669 | -0,019 |
| 12 | 40 | 0,772 | 0,798 | -0,026 |
| 13 | 48 | 0,904 | 0,934 | -0,030 |
| 14 | 56 | 1,036 | 1,078 | -0,042 |
| 15 | 65 | 1,178 | 1,227 | -0,049 |
| 16 | 74 | 1,329 | 1,381 | -0,052 |
| 17 | 85 | 1,476 | 1,539 | -0,063 |
| 18 | 95 | 1,632 | 1,699 | -0,067 |
| 19 | 107 | 1,784 | 1,861 | -0,077 |
| 20 | 119 | 1,940 | 2,023 | -0,083 |
| 21 | 132 | 2,097 | 2,185 | -0,088 |
| 22 | 146 | 2,248 | 2,346 | -0,098 |
| 23 | 160 | 2,405 | 2,505 | -0,100 |
| 24 | 175 | 2,556 | 2,661 | -0,105 |
| 25 | 190 | 2,703 | 2,814 | -0,111 |
| 26 | 206 | 2,845 | 2,963 | -0,118 |
| 27 | 223 | 2,986 | 3,106 | -0,120 |
| 28 | 241 | 3,123 | 3,245 | -0,122 |
| 29 | 259 | 3,255 | 3,379 | -0,124 |
| 30 | 278 | 3,382 | 3,506 | -0,124 |
| 31 | 297 | 3,500 | 3,627 | -0,127 |
| 32 | 317 | 3,612 | 3,743 | -0,131 |
| 33 | 338 | 3,719 | 3,851 | -0,132 |
| 34 | 360 | 3,822 | 3,954 | -0,132 |
| 35 | 382 | 3,920 | 4,050 | -0,130 |
| 36 | 405 | 4,013 | 4,139 | -0,126 |
| 37 | 428 | 4,096 | 4,223 | -0,127 |
| 38 | 452 | 4,179 | 4,300 | -0,121 |
| 39 | 477 | 4,252 | 4,372 | -0,120 |
| 40 | 502 | 4,321 | 4,437 | -0,116 |
| 41 | 529 | 4,384 | 4,498 | -0,114 |
| 42 | 555 | 4,443 | 4,553 | -0,110 |
| 43 | 583 | 4,497 | 4,603 | -0,106 |
| 44 | 611 | 4,545 | 4,649 | -0,104 |
| 45 | 640 | 4,594 | 4,690 | -0,096 |
| 46 | 669 | 4,633 | 4,727 | -0,094 |
| 47 | 699 | 4,673 | 4,761 | -0,088 |
| 48 | 730 | 4,707 | 4,791 | -0,084 |
| 49 | 761 | 4,736 | 4,817 | -0,081 |
| 50 | 793 | 4,761 | 4,841 | -0,080 |
| 51 | 826 | 4,790 | 4,862 | -0,072 |
| 52 | 859 | 4,809 | 4,881 | -0,072 |
| 53 | 893 | 4,829 | 4,897 | -0,068 |
| 54 | 928 | 4,848 | 4,912 | -0,064 |
| 55 | 963 | 4,863 | 4,924 | -0,061 |
| 56 | 999 | 4,878 | 4,935 | -0,057 |
| 57 | 1.036 | 4,892 | 4,945 | -0,053 |
| 58 | 1.073 | 4,902 | 4,953 | -0,051 |
| 59 | 1.111 | 4,912 | 4,960 | -0,048 |
| 60 | 1.150 | 4,922 | 4,966 | -0,044 |

## 4. Confrontar
![Curva teórica e pontos experimentais](grafico-rc.png)

| | τ |
|---|---|
| Teórico (R · C) | 230 ms |
| Experimental · linearização (0 pontos, R² = —) | — |
| Experimental · ponto de 63,2 % | — |
| **Experimental adotado** | **240 ms** |

- **V_S usada no cálculo:** 4.922,000 V (medida)
- **Método:** Ponto de 63,2 % de Vs (interpolação)
- **Como obtive:** Para encontrar a constante de tempo experimental, utilizei os dados de tensão coletados pelo Arduino. Procurei o instante em que o capacitor atingiu aproximadamente 63,2% da tensão final e comparei esse tempo com os 230 ms calculados teoricamente.
- **Divergência:** +4,1 % (dentro da tolerância de 25 %)

## 5. Comprovar
**Análise da divergência:** A diferença entre os valores teóricos e experimentais pode acontecer porque os componentes não possuem valores exatamente iguais aos indicados pelos fabricantes. Além disso, o próprio Arduino pode apresentar pequenas diferenças durante a leitura da tensão e do tempo. Por isso, os resultados medidos nem sempre serão exatamente iguais aos calculados.

| Causa física | Teste que a confirmaria |
|---|---|
| Os resistores e o capacitor podem ter valores reais um pouco diferentes dos indicados. Isso altera o tempo que o capacitor leva para carregar. | Mediria a resistência total com um multímetro e a capacitância com um medidor apropriado. Depois, recalcularia o tempo teórico usando os valores encontrados. |
| O Arduino pode apresentar pequenas diferenças na leitura da tensão e no instante em que registra cada ponto, influenciando a curva experimental. | Repetiria a medição e compararia os valores do Arduino com os de um instrumento independente, verificando também a tensão real de alimentação. |
| O capacitor pode apresentar uma pequena corrente de fuga, fazendo com que a tensão durante a carga fique diferente da prevista na teoria. | Repetiria o experimento com outro capacitor de 10 µF e compararia as curvas. Se a diferença diminuir, isso indicaria que o primeiro capacitor pode estar influenciando os resultados. |

### Pergunta de transferência (sem consulta)
- **Pergunta:** Limitações da leitura analógica do Arduino O Arduino converte a tensão analógica lida no pino A0 em um valor digital entre 0 e 1023. Como essa conversão pode influenciar a precisão das tensões registradas no experimento? Em quais trechos da curva você esperaria que pequenas diferenças de leitura fossem mais relevantes para estimar a constante de tempo?
- **Resposta:** O arduino tem um conversor degital que converde a tensão em 1024 níves. Cada nivel então representa aproximadamente 0,005v dos 5v de entrada, essa aproximação, e divisão faz com q no valor real tenham pequenas alterações além do contexto fisico que podem ter problemas de conexão, solda fria, janpers mau conectados.

Declaro que as medições são da bancada e que respondi a pergunta de transferência sem consulta: sim

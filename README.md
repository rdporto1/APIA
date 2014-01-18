APIA
====

APIA - Biblioteca de funções para Análise e Projeção de Indicadores de Atividade Econômica

Apresentação

A modelagem econométrica produz modelos, relações entre variáveis econômicas, que traduzem os indícios de atividade economica em indicadores quantitativos objetivos. Este processo envolve a coleta e sintese de indicadores em diversos setores da economia, em diferentes frequências, para depois compor um quadro que balize os fomuladores de política
econômica.

O que é?

APIA é uma biblioteca de funções agiliza a geração de projeções de curto prazo (para um trimestre ou um mês) de indicadores (antecedentes e coincidentes) de atividade a partir de séries temporais de domínio público.

Cada série temporal é representada por uma estrutura contendo, além dos dados, metadados que informam a data de inicio da série, sua frequência (se mensal, trimestral ou anual) e a specificação (“spec”) de ajuste sazonal que deve ser usado pela rotina de ajuste sazonal X12. As projeções podem ser de dois tipos: contábeis, quando os pesos dos componentes são conhecidos, ou estatísticas, quando um procedimento de previsão univariada (SARIMA, Arima Sazonal) é usada para projetar valores futuros da série levando em conta sua sazonalidade. As funções foram concebidas pensando na construção de um script que se ajusta ao trimestre ou mês que se projeta (faz-se referência a M1, M2 e M3 como o primeiro, segundo e terceiro mês do trimestre) bem como à quantidade de informação disponível: pouca no início do trimestre (quando se usa mais projeções estatísticas) e vai aumentando até o final do segundo mês depois de terminado o trimestre (período conhecido como t+2) quando se deve ter todos os dados para antecipar, com projeções contábeis, os números oficiais do IBGE. 

Por que usar ?

Pelo uso desta biblioteca não apenas se elimina muitos erros operacionais de cálculo dos indicadores, mas também é possível entregar com maior frequência as estatísticas que resumem os movimentos da economia para fins de acompanhamento macroeconômico.

APIA
====

APIA - Biblioteca Matlab para Análise e Projeção de Indicadores de Atividade Econômica

1) Apresentação

A modelagem econométrica produz modelos, relações entre variáveis econômicas, que
traduzem os indícios de atividade economica em indicadores quantitativos objetivos. Este
processo envolve a coleta e sinteze de indicadores em diversos setores da economia, em
diferentes frequências, para depois compor um quadro que balize os fomuladores de política
econômica.

APIA é uma biblioteca de funções agiliza a geração de projeções de curto prazo (para um
trimestre ou um mês) de indicadores (antecedentes e coincidentes) de atividade a partir de
séries temporais de domínio público.

Cada série temporal é representada por uma estrutura contendo, além dos dados, metadados
que informam a data de inicio da série, sua frequência (se mensal, trimestral ou anual) e a
specificação (“spec”) de ajuste sazonal que deve ser usado pela rotina de ajuste sazonal X12.
As projeções podem ser de dois tipos: contábeis, quando os pesos dos componentes são
conhecidos, ou estatísticas, quando um procedimento de previsão univariada (SARIMA, Arima
Sazonal) é usada para projetar valores futuros da série levando em conta sua sazonalidade.
As funções foram concebidas pensando na construção de um script que se ajusta ao trimestre
ou mês que se projeta (faz-se referência a M1, M2 e M3 como o primeiro, segundo e terceiro
mês do trimestre) bem como à quantidade de informação disponível: pouca no início do
trimestre (quando se usa mais projeções estatísticas) e vai aumentando até o final do segundo
mês depois de terminado o trimestre (período conhecido como t+2) quando se deve ter todos
os dados para antecipar, com projeções contábeis, os números oficiais do IBGE.
Pelo uso desta biblioteca (toolbox), não apenas se elimina muitos erros operacionais de cálculo
dos indicadores, mas também é possível entregar com maior frequência as estatísticas que
resumem os movimentos da economia para fins de acompanhamento macroeconômico.


2) Principais conceitos e exemplos de uso

Há uma estrutura em memória com os parâmetros globais que estão disponíveis em todos os
programas. Trata-se do config com os campos:

ano0: 2003

mes0: 1

tri0: 1

ano: 2013

m1: 9

m2: 9

m3: 9


O início de uma série deve ser informado nos campos ano0, mes0 e tri0. Para não ter de informar o início de todas as séries usa-se os valores de config, config.ano0, config.mes0 e config.tri0. O campo ano se refere ao ano que se deseja projetar, assim como m1, m2 e m3 são os três meses do trimestre em estudo. Com essa estrutura, as rotinas podem chamar
config.m1 que será traduzido em janeiro no primeiro trimestre, abril no segundo, julho no terceiro e outubro no quarto. Assim não é preciso mudar o script a cada novo trimestre.

Observe nos campos m1, m2 e m3 acima há apenas o valor 9. Isso é como se inicializa o
config para projetar uma série mensal como a PIM. Os três meses são o mesmo, neste caso
setembro de 2013. Assim a expressão m1:m3 funciona para listar os três meses do trimestre
bem com para lista o único mês da projeção de uma variável mensal.

O arquivo Demonstra.m traz um exemplo completo com todas as funções disponíveis. Vamos percorrê-lo com detalhes no que segue.

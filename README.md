# Bot Half Under

s_da = Soma de ataques perigosos
s_so = Soma de chutes a gol
s_sf = Soma de chutes para fora do gol
s_c  = Soma de escanteios
s_g  = Soma de gols
```
goalline = Total de gols ( Under ou Over) para o Full Time da odds fornecido pela casa de apostas 
```
```
INDICE1=0.0005 *s_da + 0.0129*s_so + 0.0114 * s_sf + 0.0104*s_c + 0.043*s_g -0.183*(goalline -  s_g)
```
```
probUnder=1/oddsUnder/(1/oddsUnder + 1/oddsOver)
```
```
goalline_mod=goalline % 1    (pode ser 0, 0.25, 0.5 ou 0.75) 
```
```
INDICE2=-0.473*INDICE1 -0.034*goalline_mod -0.1839*probUnder
```
```
media_retorno=1.15468*INDICE2 + 0.11419  
```
variancia_retorno é dado pelo tabela 
|MOD|VAR|
|---|---|
|0.00|0.66|
|0.25|0.70|
|0.50|0.90|
|0.75|0.74|

```
%Kelly = media_retorno / (media_retorno^2 + variancia_retorno)
```
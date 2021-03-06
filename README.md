[![Travis-CI Build Status](https://travis-ci.org/JessicaSousa/QualisR.svg?branch=master)](https://travis-ci.org/JessicaSousa/QualisR)

QualisR: Acesso as tabelas dos qualis do Sucupira via R
========================================

O presente pacote permite que você acesse as tabelas dos qualis do site [Sucupira](https://sucupira.capes.gov.br/sucupira/public/consultas/coleta/veiculoPublicacaoQualis/listaConsultaGeralPeriodicos.jsf), via R. Você pode pode selecionar se deseja obter todas as tabelas do site ou apenas algumas, relacioná-las e fazer as operações que desejar.

O pacote `QualisR` é desenvolvido utilizando o controle de versão do Github. Então você pode fazer download dele utilizando o pacote `QualisR`:

``` r
# install.packages("devtools")
devtools::install_github("JessicaSousa/QualisR")
```

### Exemplo

A função `QualisR::get_all_tables` permite que você obtenham várias tabelas do site do Sucupira, use com moderação :)

```{r}
#Realiza Get na página do Sucupira
sucupira_get <- QualisR::get_sucupira_page()
print(sucupira_get$status_code)

#Obtém as tabelas de periódicos dos quatro primeiros cursos no triênio 2010-2012
tabelas <- QualisR::get_all_tables(sucupira_get,num_tables = 4, event = 'triênio 2010-2012')

head(tabelas$ARTES)
```

#### Outros exemplos
Veja mais coisas que você pode fazer no [Tutorial](https://jessicasousa.github.io/QualisR/inst/doc/README.html)

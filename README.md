# Tutorial-17

**Teste para o tutorial 17**
*Agora uma breve apresentação*

#Equações

```r, echo = F
x <- 3 *10
```

##Primeiro exercicio do tutorial 17##

$$\frac{\sqrt{1}}{2} * \frac{a}{2b} = \frac{a}{4b}$$

library(tidyverse)
library(knitr)

file1 <- "https://raw.githubusercontent.com/leobarone/ifch_intro_r/master/data/bf_amostra_hv.csv"
dados <- read.table(file1, header = T, sep = ",")

dados %>% group_by(uf) %>%
  summarize(mean_valor=mean(valor)) %>% 
  kable()
  
dados %>% group_by(uf) %>%
  summarize(mean_valor=mean(valor)) %>% 
  kable(caption="A minha tabela",align="cr",digits=1,col.names=c("Estado","Valor Media"), format.args=list(big.mark=","))
  
dados %>% group_by(uf) %>%
  summarize(valor_total=sum(valor)) %>%
  ggplot() +
  geom_col(aes(x=uf,y=valor_total))

```{r, echo=F}
dados %>% group_by(uf) %>%
  summarize(valor_total=sum(valor)) %>%
  ggplot() +
  geom_col(aes(x=uf,y=valor_total))
```
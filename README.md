# COVID19_GGplot
# GGplot of COVID-19 cases using Italian Health Ministry data
# data were downloaded from https://github.com/pcm-dpc/COVID-19/ see dpc-covid19-ita-province-20200224.csv

# Order labels (this is according to the total number of cases on the 20th of March:
mydt$ord <- factor(mydt$denominazione_provincia, levels=c( 'Bergamo', 'Brescia', 'Milano', 'Cremona', 'Lodi', 'Pavia', 'Mantova', 'Monza e della Brianza', 'Piacenza', 'Sondrio', 'Varese', 'Lecco', 'In fase di definizione/aggiornamento'))

# Graph code:
ggplot(mydt%>% filter(codice_regione =='03'))+ #select one region, in this case Lombardia
geom_bar(stat='identity', aes(x=data, fill=ord, y=totale_casi))+
theme(legend.title = element_blank())+
scale_fill_manual(values=c('#a6cee3', '#1f78b4','#b2df8a', '#33a02c', '#fb9a99', '#e31a1c', '#fdbf6f', '#ff7f00', '#cab2d6', '#6a3d9a', '#ffff99', '#b15928', '##000000', '#f0f0f0'), labels=c( 'Bergamo', 'Brescia', 'Milano', 'Cremona', 'Lodi', 'Pavia', 'Mantova', 'Monza', 'Piacenza', 'Sondrio', 'Varese', 'Lecco', ''))+
theme_economist()+
labs(x = '' , y = 'Total cases')+
theme(legend.title = element_blank())

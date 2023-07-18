---
pagetitle: Gesellschaftsmonitoring COVID19, Daten Lehrmittelverlag Zürich
---

![](https://bildungsmonitoringzh.github.io/assets/ktzh_bi_logo_de-300x88.jpg)
![](https://bildungsmonitoringzh.github.io/assets/lmvz_logo-300x88.jpg)

# Gesellschaftsmonitoring COVID19, Daten Lehrmittelverlag Zürich

Daten zur täglichen Nutzung eines online benutzbaren [Fertigkeitstrainings 1-6](https://shop.lmvz.ch/de/Katalog/Mathematik-Primarschule/Mathematik-Primarstufe-Fertigkeitstraining-1-6-9916.html) für die Primarstufe in Mathematik im Rahmen des Projekts [Gesellschaftsmonitoring COVID19](https://statistikzh.github.io/covid19monitoring/)

## Datenlieferant

[source] Lehrmittelverlag Zürich

## Beteiligte

Christoph Saner <christoph.saner@lmvz.ch>, Lehrmittelverlag Zürich

Flavian Imlig <flavian.imlig@bi.zh.ch>, Bildungsdirektion

## Indikatorenbeschreibung

Der Indikator beschreibt die Anzahl der Zugriffe auf die Online-Ressource pro Tag. 

Die Zeitreihe beginnt am 1. Januar 2020 und endet am 17. Juli 2023.

Per 8.4.2020 wurde Matomo anstelle von Google Analytics als Webanalytik-Plattform eingesetzt. Aufgrund der leicht anderen Zählweise in Matomo gegenüber Google Analytics wurden die Werte vom 1.1.2020 bis 7.4.2020 rückwirkend angepasst ([Modellbeschreibung][umrechnungsmodell]).

Für den Zeitraum 8.05.2021 bis 30.5.2021 liegen keine Angaben vor. Grund dafür ist eine Serverumstellung.

[topic] Bildung

[variable_short] training_mathematik_lmvz

[variable_long] Nutzung des Fertigkeitstrainings 1-6 für Mathematik auf der Primarstufe

[location] global

[unit] Anzahl Starts Fertigkeitstraining

[update] täglich

[description] https://bildungsmonitoringzh.github.io/covid19_edu_lmvz_public/

## Open data 

Kann die Variable OGD gestellt werden?

[public] Ja

## Vorgehen

* (Daten ab 8.4.2020) automatischer, wöchentlich aktualisierter Report in Matomo, Bezug der Daten und Generieren der erforderlichen Datenstruktur einmal wöchentlich.
* (Daten bis 7.4.2020) automatischer, täglich aktualisierter Report in Google Analytics, rückwirkend umgerechnet auf Basis eines [linearen Modells][umrechnungsmodell].

### Umrechnungsmodell

Aus parallel vorliegenden Nutzungsdaten (Google Analytics und Matomo) im Zeitraum von neun Tagen ab dem 8.4.2020 wurde ein lineares Modell mit folgenden Kennwerden berechnet. Die Koeffizienten des Modells kommen bei der rückwirkenden Umrechnung der Daten aus Google Analytics zur Anwendung.

```r
> summary(linear_model$model)

Call:
lm(formula = Total.Events.Mtm ~ Total.Events.GA, data = data_raw)

Residuals:
    Min      1Q  Median      3Q     Max 
-582.79 -265.42   43.89  208.09  464.31 

Coefficients:
                  Estimate Std. Error t value Pr(>|t|)    
(Intercept)     -188.07911  248.35932  -0.757    0.474    
Total.Events.GA    0.67478    0.06217  10.853 1.24e-05 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 387.4 on 7 degrees of freedom
  (98 observations deleted due to missingness)
Multiple R-squared:  0.9439,	Adjusted R-squared:  0.9359 
F-statistic: 117.8 on 1 and 7 DF,  p-value: 1.244e-05
```

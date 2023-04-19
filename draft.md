---
bibliography: [draft.bib]
CJKmainfont: PingFang SC
---

### Introduction

In recent years, the world has witnessed China's rapid economic development, especially in the eastern coastal city clusters. Due to active industrial activities, rapid urban construction, dense population, and other factors, the coastal city clusters have not only become a catalyst for China's economic takeoff, but also brought serious air quality problems,  troposphere ozone pollution is a typical example. This demands for the accuracy of air quality numerical model prediction.

但是，因为源排放的不确定性，参数化方案，气象场与化学场的初始/边界条件误差等问题，许多空气质量模型都不能达到令人满意的预报精度。当视角转变到Ozone预报上，情况将更加复杂，因为Ozone前体物的组成和来源繁多，化学方案以及源排放清单上就有可观的误差，并且Ozone的生命周期较长，气象场的transport效应明显，因此，Ozone预报面临着来自气象和化学双重的不确定性(warning: where does it come from???)。源排放对空气质量模式的预报精度影响巨大Sandu2011，Elbern2007通过同时同化初始场和源排放场，很好的改进了模式的预报结果。源排放场对于Ozone预报的影响同样明显，城市短期Ozone预报的一个重要的不确定性来源就是前体物(如NOx NMVOCs)的源[@Tang_2011]。其中，NMVOCs的源排放清单由于其种类繁多，不同的气相化学方案都对VOCs进行了不同的分类（lump），而初始的源排放清单一般只提供NMVOCs的总量（eg. EDGAR），并没有通用的emission inventory->model-ready emission file的routine，因此在NMVOCs的model-ready的源排放处理上一直存在巨大的误差。

数据同化在空气质量模式中已经有了广泛的应用。ENKF，Variational，Pagowski2010，Schwarz2012，2014等。

top-down的源排放处理。

Li 2014等在MEIC源排放清单上实现了与几个主流气相化学模式的直接对接，使得NMVOCs的源排放精度得到显著提高。但是，之前的许多实验中都没有对NMVOCs以及源进行细致的分别同化(eg. Ma2019, Tang2011, Peng etc. )，这实际上是浪费了Li等对VOCs细致分类的信息。因此，我们这里试图解决这个问题。

目前还没有建立VOCs的常规业务化观测，并且据[@Koohkan_2013]，VOCs的观测由于其生命周期很短，限制了同化的空间半径，即使有稀疏的观测也难以达到理想的效果。这使得我们现阶段只能使用其他的常规观测污染物来尝试同化VOCs。

### Modeling System

#### WRF-Chem model setting

#### DA setting

### Observations

#### Meteo

#### Chem

#### Emission

####  

### Experiment Design

We set Meteo Observation assimilate Meteo state variable, six main air pollution's Observation assimilate their own model state variable and emission scaling factor as control experiment(CTRL), which has been proved to be capable of  generating relatively good results in analysis and forecast(see, Peng2020). 

Previous works tend to use ozone observation to assimilate VOCs(Tang2011, Ma2019). H

|          | VOC Species |
| -------- | ----------- |
| CTRL     | None        |
| O3_all   | ^           |
| O3_5pct  | ^           |
| All_5pct | ^           |

#### VOC Factor

Define:
$$
factor = corr*(norm(conc)-norm(emiss))
$$


## 一些可以用到的结论

1. Ozone预报的一个重要的不确定性来源就是前体物的源。

   Precursor emissions have been pointed out as the important uncertainty sources of ozone forecast by many previous studies (Carmichael et al., 2008; Constantinescu et al., 2007b; Hanna et al., 1998)

2. 在城市的短期的Ozone预报中，前体物的源是除Ozone IC之外的最主要的来源As reported by Tang et al. (2010b), precursor emissions are the most important uncertainty sources for short-term ozone forecast over urban areas beside ozone initial conditions, in contrast to the short-term ozone forecast over suburban areas where the precursor emissions show minor role

3. VOCs的观测由于其生命周期很短，限制了同化的空间半径。(Koohkan 2013)it is shown that the use of in situ observations using a sparse monitoring network to estimate emissions of isoprene is inadequate because its short chemical lifetime significantly limits the spatial radius of influence of the monitoring data

4. 根据Li 2014，MEIC源根据不同的气相化学方案区分了不同的NMVOCs源。如果没有对NMVOCs进行更加细致的同化操作，实际上是浪费了这些信息。

5. Sandu 2011 Elbern2007 都在说emission是control variable，这对Ozone也一样。

---
bibliography: [draft.bib]
CJKmainfont: PingFang SC
---
# VOCs draft

## 1. Introduction

(Note: is it needed to address 'Ozone'? maybe we can mention NMVOC more.)
Troposhere ozone has been viewed as a critical component in air pollution for being a threat to human body. Recent years, due to active industrial activities, rapid urban construction, dense population, and many other factors, the coastal city clusters have not only become a catalyst for China's economic takeoff, but also brought serious air quality problems,  and troposphere ozone pollution is a typical example. This demands for higher accuracy in air quality numerical model prediction. (Note: need much more polish ... )

但是，因为源排放的不确定性，参数化方案，气象场与化学场的初始/边界条件误差等问题，许多空气质量模型都不能达到令人满意的预报精度(warning: suspicious, need accurate cite)。数据同化在air quality model中已经有了广泛的应用。Filtering approach [@Schwartz_2012; @Pagowski_2012; @Peng_2017, @Kou_2021]，Variational [@Elbern_2007; @Pagowski_2010; @Liu_2011], hybird method [@Schwartz_2014]. 源排放对空气质量模式的预报精度影响巨大[@Sandu_2011]，通过同时同化chem ic and emission，可以更好地的改进模式的预报结果[@Elbern_2007]。top-down的源排放处理。

当视角转变到Ozone预报上，情况将更加复杂，因为控制模式Ozone预报的factor种类繁多，模式气相化学方案，输运过程，前体物源排放都会对Ozone造成影响，其中，源排放对于Ozone预报的影响格外明显[@Monks_2015]。城市短期Ozone预报的一个重要的不确定性来源就是前体物(mainly,NOx,CO,NMVOCs)的源[@Tang_2011; @Tang_2010]。在Ozone的前体物中，NMVOCs具有很大的不确定性，这种不确定性不仅体现在emission的总量上，也体现在NMVOC speciation上[@Li_2017]。具体来说，模式中不同的气相化学方案都对VOCs进行了不同的分类(lumped together according to their similarities in chemical structure or reactivity), but these speciation almost always differ from inventories, which introduces extra uncertainty. This speciation uncertainty will greatly affect model performance, and many efforts have been devoted to construct a better mapping between inventory and model-ready emission[@Li_2014]. But in data assimilation，uncertainty of NMVOCs speciation haven't got enough attention, previous studies usually treat NMVOCs as a unity and give them equal increments(eg. [@Ma_2019, @Tang_2011]). (......) NMVOC is critical for ozone forecasting, and current assimilation method still remains large uncertainty.

目前还没有建立NMVOCs的常规业务化观测，并且据[@Koohkan_2013]，VOCs的观测由于其生命周期很短，限制了同化的空间半径，在使用空间分辨率较大的模式时，即使有稀疏的观测也难以达到理想的效果。这使得我们现阶段只能使用其他的常规观测污染物来尝试同化VOCs。

## 2. Model configurations and data assimilation system

Version 3.6.1 of the WRF-Chem model was used, which is an 'online' model with fully-coupled chemical and meteorological fields[@Grell_2005]. The EnSRF[@Whitaker_2002] with its expansion to chem component[@Schwartz_2014; @Peng_2017] is chosen to construct the data assimilation system. Section 2.1 and 2.2 will expand their settings more specificly.

### 2.1. WRF-Chem model setting

Table1 for wrf-chem paramenterization setting. See [@Peng_2018] for an example.
Table2 for RADM2 NMVOCs speciation in model. (14 VOCs we use).

Figure for domain setting and chem observation station distribution.

![domain_station_fig](./figure/domain_station.png)

The update of source emissions through assimilation of chemical observations follows[@Peng_2017], detailed description will not expand here.

### 2.2. data assimilation setting

## 3. Observations

### 3.1. Meteo

### 3.2. Chem

### 3.3. Emission

Mainland China: The hourly prescribed anthropogenic emission is obtained from the Multi‐resolution Emission Inventory for China (MEIC v1.3) [@Li_2017; @Zheng_2018] in July 2017, which is the most updated dataset. In areas out of mainland china, we use EDGARv6.1 in July 2017.

## 4. Experiment Design

### 4.1. 30-day free forecast

### 4.2 VOC Factor

Define:
$$
factor = corr*(norm(conc)-norm(emiss))
$$

### 4.3. cycling and forecast setting

We set Meteo Observation assimilate Meteo state variable, six main air pollution's Observation assimilate their own model state variable and emission scaling factor as control experiment(CTRL), which has been proved to be capable of generating relatively good results in analysis and forecast[@Peng_2020].

Previous works tend to use ozone observation to assimilate VOCs[@Tang_2011; @Ma_2019]. 

|          | VOC Species |
| -------- | ----------- |
| CTRL     | None        |
| O3_all   | ^           |
| O3_5pct  | ^           |
| All_5pct | ^           |

## 5. Results

## 6. Summary and discussion

## 一些可以用到的结论

1. Ozone预报的一个重要的不确定性来源就是前体物的源。

   Precursor emissions have been pointed out as the important uncertainty sources of ozone forecast by many previous studies (Carmichael et al., 2008; Constantinescu et al., 2007b; Hanna et al., 1998)

2. 在城市的短期的Ozone预报中，前体物的源是除Ozone IC之外的最主要的来源As reported by Tang et al. (2010b), precursor emissions are the most important uncertainty sources for short-term ozone forecast over urban areas beside ozone initial conditions, in contrast to the short-term ozone forecast over suburban areas where the precursor emissions show minor role

3. VOCs的观测由于其生命周期很短，限制了同化的空间半径。(Koohkan 2013)it is shown that the use of in situ observations using a sparse monitoring network to estimate emissions of isoprene is inadequate because its short chemical lifetime significantly limits the spatial radius of influence of the monitoring data

4. 根据Li 2014，MEIC源根据不同的气相化学方案区分了不同的NMVOCs源。如果没有对NMVOCs进行更加细致的同化操作，实际上是浪费了这些信息。

5. Sandu 2011 Elbern2007 都在说emission是control variable，这对Ozone也一样。

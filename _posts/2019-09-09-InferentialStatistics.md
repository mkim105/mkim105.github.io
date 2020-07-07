---
title: "Intro to Inferential Statistics and Hypothesis Testing"
date: 2019-09-09 22:00:00 -0400
categories: DataAnalytics
---
# Week03_01

> Intro to Inferential Statistics and Hypothesis Testing; 추리통계학과 가설검정에 대한 소개

- - -
## Use Sample to Estimate Population; 모집단을 평가하기위한 표본 사용

*모수를 추정하는 방법*에는 2가지가 있다.
+ By estimating its value
  + example: 인천대학교 학생들의 나이를 평가하는 법
+ By testing hypothesis about its value
  + example: 방법1이 방법2보다 낫다.
  + example: 오늘의 판매량은 8보다는 적을 것 이다.

> 모수는 모집단의 특성을 나타내는 수치이다. such as 모평균

*모평균 평가를 위한 통계적 추론 PROCEDURE*
  1. 표본을 수집하고 기술통계 계산을 한다.
  2. n이 충분히 크다면 표본평균은 정규분포를 따를 것이고, 표본분포의 평균은 모평균으로 쓰일 수 있다.
      + Otherwise, we assume it follows t distribution.
  3. n이 커질수록 표준오차는 점점 작아진다.
  4. 신뢰구간을 이용한 통계학적 주장으로 결론을 만든다.
      + Confidence interval = Sample estimate ± Margin of error
      + Margin of error = z value or t value * standard error
      
> 신뢰도 95%의 신뢰구간이라는 것은 n이 충분이 커서 표본분포의 평균이 모평균으로 쓰일 수 있을 때,
> 표본표준편차의 1.96배 구간 안에 모평균 양 옆으로 100%의 표본평균 중 95%의 표본평균이 존재한다는 것 이다.
> + 다르게 말하면, **신뢰구간은 실제 평균을 포함할 가능성이 95% 되는 범위**를 나타낸다고 할 수도 있다. 
> + 또 다른 의미로는, 크기가 n인 표본(집단)을 100회 추출했을 때, 신뢰구간 안에서 95회의 표본(집단)이 모평균을 capture 한다고 할 수 있다.
>   + ↑ So roughly 95% of the samples will capture the true population average μ in the confidence interval.

The **confidence level** (95% in this example) says how confident we are that the procedure will "catch" the true population average μ.

95%의 **신뢰수준** =  위의 procedure가 모평균 μ를 잡아낼 수 있는지에 대해서 95% 만큼 confidence하다.

*Large vs Small sample size*
+ Large sample size의 경우에는 모표준편차(usually we do not know it)를 알고있거나 Sample size가 충분히 크다는 것을 알아야한다
  + Samples size가 충분히 크면 표본표준편차를 이용하여 모표준편차를 구할 수 있다.
+ Small sample size의 경우에는 Normal distribution 보다는 t distribution을 이용한다.

*Difference between t and normal distribution*
+ t 분포는 정규분포와 유사하다.
+ t 분포는 n<30 이면 적용된다.
+ n이 증가하면 t 분포는 normal에 가까워진다.
+ t 분포의 유일한 매개변수는 자유도(Degree of freedom)이다. df, df = n-1
+ df가 작을수록 spread(분포의 퍼짐)는 커진다.
+ df가 충분히 크면, t 분포는 정규분포를 따른다.

*Difference between z and t values*
+ z value is associated with α
+ t value is associated with α and df

## Hypothesis Testing; 가설 검정

*What is hypothesis and how useful it is*
+ Hypothesis is a claim or assumption.
   + e.g) 평균 나이는 30일 것 이다.
   + e.g) 평균 나이는 30 미만일 것 이다.
+ 가설검정은 Confidence level을 바탕으로 가설이 참/거짓인지 검증하는데 사용된다.

*What is statistical elements in hypothesis testing 가설검정의 통계학적 요소들*
+ Null Hypothesis 귀무가설, 영가설 H0
+ Alternative Hypothesis 대립가설 H1 or Ha
+ Test Statistics 검정통계량
+ Level of significance 유의수준 α
+ Rejection Region 기각역
+ P-value 

*Types of hypothesis testing*
+ 하나의 표본평균에 대한 가설검정
   + 월별 이용료는 $42일 것이다.
   + 하지만 나는 이것이 참이라고 생각되지 않는다.
   + μ > μ0
+ 두 개의 표본평균에 대한 가설검정
   + ATT와 T-Mobile의 월별 이용료는 같다.
   + 하지만 나는 ATT가 T-Mobile보다는 비쌀 것 같다.
   + μ ≠ μ0 

*How to perform hypothesis testing in Hypothesis testing*
1. H0와 Ha을 정한다.
2. Ha를 기반으로 one-tailed test or two-tailed test를 결정한다.
3. 유의수준 α를 결정하거나 통계학적인 신뢰수준을 claim한다.
4. 표본 크기에 따라 적절한 검정통계량과 표본분포 결정한다.
5. rejection과 non-rejection regions을 결정하는 임계치를 결정한다. 
6. 통계학적 결정을 하고 결론을 state해라.

**Three metrics to make decisions**
  + By using test staatistics; 검정통계량을 이용하여
    + If it falls in the rejection area, we reject H0
    + e.g)Z score를 구한다 > Z score가 기각역 안에 들어가는지 본다.
    + Z score가 기각역 안에 들어간다 > H0를 기각한다.
  + By using p-value; P값을 이용하여
    + If the p-value < α, we reject H0(Null Hypothesis)
    + e.g)Z score를 구한다 > Z score를 토대로 P value를 구한다 > P value와 significance level을 비교한다.
  + By using confidence interval; 신뢰구간을 이용하여
    + 신뢰구간을 구하여 그 안에 모수(μ)가 포함되는지를 본다. 
    + 채택역이 신뢰수준에 바탕을 둔 신뢰구간이라는 것을 주목해야 한다.
  > 위의 세가지의 metrics를 이용했을 때 같은 값이 나올 것 이다.
  >   * 모든 metrics는 rejection region을 기초로 한다.
  >   * 이러한 three metrics를 이해하기 위해서는 rejection region에 대해 fully understand 해야 한다.


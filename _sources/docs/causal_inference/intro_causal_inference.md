# Causal Inference

## Introduction

Causal Inference is the process of understanding the causal connections in the data based on given observed conditions in which the experiment has taken place. It is one of the most crucial studies that needs to be done so as to understand the relation between an exposure and it's corresponding effect. It is widely used in following fields but no limited to health, social, and behavioural sciences. These fields are driven by causal relationship rather than associational relationship. For example, causal inference can be used to understand the efficacy of drug or it can also be used to understand the efficacy of a policy.  
Causal inference can not only be used, like standard statistical analysis or associational concepts can be used to assess the parameters of distribution, determine the probalities of events and estimate effects under static conditions, but it can also be used to observe the dynamics of beliefs under changing conditions. 

## Confusion over causality

There may arise confusion in understanding the causality. Let us go through some of the reasons for the confusion:
1. A confusion over causality may arise due to the existence of spurious correlation in the data. There are methods to understand correlation in the data such as hypothesis testing. Hypothesis test can be used to check whether the data is correlated, if it correlated then how strongly. But as the famous saying goes - **"Correlation does not imply Causation"**. Hence causal inference is required to infer the causal relationship in the data. Spurious correlation is the connection between two variables such that they appear to be in causal relation. It is as if one variable is responsible for the change in another another. This change can be just another coindent or it may be due to some external factor. This external factor is called confounding variable. Thus spurious correlation may prevent us from understanding the actual causal relation between exposure and it's corresponding effect. It is very crucial to identify the spurious correlation in the data and eliminate the bias introduced, if any, that is introduced by confounding factor.  
2. Our prior beliefs may affect our skeptical thinking which might further affect our decisions on analyses of a situation. These personal anecdotes are observed most often but are ignored causing confusion.   
3. Confusion may also arise due to conversations, skeptism and debates about causality in the scientific reports and headlines. Our prior beliefs affect our ability to think skeptically and hence may affect our ability to reason appropriately.  
4. Sometimes it may also happen that we may know that the existence of causal relationship in the data but the direction of it is unclear. This type of causality is known as reverse causality.  
  
The field of causal inference attempts to remove the above confusions by proposing:  
- formal definitions of causal effect  
- assumptions necessary to identify causal effects from data  
- rules about what variables need to be controlled for  
- sensitivity analyses to determine the impact of violations of assumption on conclusions  
 
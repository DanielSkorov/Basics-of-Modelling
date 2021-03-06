---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

<a id='pvt-td-mixture_gibbs_energy'></a>
# Энергия Гиббса многокомпонентной системы
Данные в предыдущем разделе определения [экстенсивным](./TD-9-Observables.html#pvt-td-observables-extensive) и [интенсивным](./TD-9-Observables.html#pvt-td-observables-intensive) параметрам Могут быть использованы для получения выражений для расчета термодинамических параметров многокомпонентных систем. Покаже это на примере энергии Гиббса.
+++

## Энергия Гиббса при постоянных давлении и температуре

+++

Ранее, при введении параметра [энергии Гиббса](TD-8-Helmholtz-Gibbs.html#pvt-td-helmholtz_gibbs-gibbs), было показано, что:

+++

$$\mu = \left( \frac{\partial G}{\partial N} \right)_{T, P}.$$

+++

Данное выражение означает, что приращение энергии Гиббса при добавлении молекул к системе есть химический потенциал при фиксированных давлении и температуре. При этом, энергия Гиббса является экстенсивным параметром, то есть она зависит от количества частиц: $G = G \left( N, T, P \right)$. Кроме того, единственным экстенсивным параметром, используемым для расчета энергии Гиббса, является количество молекул, следовательно, энергия Гиббса должна быть пропорциональна количеству молекул. Из этого следует, что если в рассматриваемой системе при постоянных давлении и температуре имеется только один вид молекул (один компонент), то энергия Гиббса может быть определена следующим образом:

+++

$$G = \mu N.$$

+++

То есть химический потенциал можно интерпретировать как энергия Гиббса, приходящаяся на одну молекулу. При этом, химический потенциал является функцией от давления и температуры:

+++

$$ \mu = \mu \left( P, T \right).$$

+++

В общем виде, если в системе несколько компонентов, то:

+++

$$G = \sum_{i} \mu_i N_i.$$

+++

<a id='pvt-td-mixture_gibbs_energy-partial_molar_observables'></a>
## Парциальные молярные экстенсивные параметры
Пусть переменная $E$ обозначает любой [экстенсивный параметр](./TD-9-Observables.html#pvt-td-observables-extensive) системы. Обозначим частную производную по количеству молекул $i$-го компонета (или по количеству вещества $i$-го компонента) данного параметра при постоянных давлении, температуре и количествах молекул остальных компонентов как $\bar{E_i}$, то есть:

+++

$$\bar{E_i} = \left( \frac{\partial E_i}{\partial N_i} \right)_{P,T,n_j}.$$

+++

При этом, любой экстенсивный параметр $E$, как функция относительно $\lambda N_i$ количеств молекул компонентов, выражается следующим образом:

+++

$$ E \left( P, T, \lambda N_1, \lambda N_2, \ldots, \lambda N_c \right) = \lambda E \left( P, T, N_1, N_2, \ldots, N_C \right),$$

+++

где $C$ – количество компонентов. Получим частную производную от левой и правой части данного выражения по $\lambda$. Поскольку параметр $E$ является функцией от величины $\lambda N_i$, каждая из которых является функцией от $\lambda$, то, применяя [правило дифференциирования сложной функции](https://en.wikipedia.org/wiki/Chain_rule#Multivariable_case), получим:

+++

$$\sum_{i=1}^C \left( \frac{\partial E}{\partial \lambda n_i} \right)_{P,T,n_j} \frac{d \lambda n_i}{d \lambda} = E \left( P, T, N_1, N_2, \ldots, N_c \right).$$

+++

Для $\lambda=1$:

+++

$$\sum_{i=1}^C \left( \frac{\partial E}{\partial  N_i} \right)_{P,T,N_j} N_i = \sum_{i=1}^C \bar{E_i} N_i = E \left( P, T, N_1, N_2, \ldots, N_c \right).$$

+++

Таким образом, любой экстенсивный параметр может быть рассчитан из его частных производных по количеству молекул (вещества) компонентов. Необходимо также отметить, что фиксация давления и температуры необходимы для того, чтобы выполнялось полученное соотношение. [Ранее](TD-8-Helmholtz-Gibbs.html#pvt-td-helmholtz_gibbs-helmholtz_partials) было показано, что химический потенциал является частной производной энергии Гельмгольца по количеству молекул компонента при постоянных температуре и объеме:

+++

$$\mu_i = \left( \frac{\partial F}{\partial N_i} \right)_{T,V}.$$

+++

При этом, парциальная молярная энергия Гельмгольца, определяемая выражением:

+++

$$\bar{F_i} = \left( \frac{\partial F}{\partial N_i} \right)_{P,T},$$

+++

не равная химическому потенциалу, то есть:

+++

$$\bar{F_i} \neq \mu_i.$$

+++

<a id='pvt-td-mixture_gibbs_energy-partial_molar_observables-ideal_gas'></a>
Также стоит отметить, что из-за межмолекулярных взаимодействий различных компонентов парциальный молярный параметр не равен приведенному на единицу количества молекул параметру, то есть:

+++

$$ e_i \left( P,T \right) = \frac{E_i \left( P,T,N_i \right)}{n_i} \neq \bar{E_i}.$$

+++

Данное правило справедливо для всех систем, за исключением особых случаев, например, идеального газа. Рассмотрим парциальный молярный объем иделаьного газа. Применяя [уравнение состояния идеального газа](TD-1-Basics.html#pvt-td-basics-ideal_gas_eos), получим:

+++

$$\bar{V} = \left( \frac{\partial V}{\partial N} \right)_{P,T} = \frac{\partial}{\partial N} \left( \frac{N k T}{P} \right)_{P,T} = \frac{kT}{P} = \frac{V}{N} = v.$$

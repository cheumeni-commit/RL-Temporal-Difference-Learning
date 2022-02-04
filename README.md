# RL-Temporal-Difference-Learning

Ce projet permet de determiner la valeur de lambda à partir de deux méthodes: le Temporal difference learning et le Monte Carlo learning. Nous appuyons sur le Markov Decision Processus(MDP). 

# Description du problème

Given an MDP and a particular time step $t$ of a task (continuing or
episodic), the $\lambda$-return, $G_t^\lambda$, $0\leq\lambda\leq 1$, is
a weighted combination of the $n$-step returns $G_{t:t+n}$, $n \geq 1$:

$${G_t^\lambda = \sum\limits_{n=1}^\infty(1-\lambda)\lambda^{n-1}G_{t:t+n}.}$$

While the $n$-step return $G_{t:t+n}$ can be viewed as the target of
an $n$-step TD update rule, the $\lambda$-return can be viewed as the
target of the update rule for the TD$(\lambda)$ prediction algorithm,
which you will become familiar with in project 1.

Consider the Markov reward process described by the following state
diagram and assume the agent is in state $0$ at time $t$ (also assume
the discount rate is $\gamma=1$). A Markov reward process can be thought of as
an MDP with only one action possible from each state (denoted as action $0$ in
the figure below).

![image](https://d1b10bmlvqabco.cloudfront.net/paste/jqmfo7d3watba/9e6fd83672f880704b8418728297fc077786c8907d87fec631601da9ff4c85ef/hw2.png)

# Modélisation

Pour résoudre ce problème, nous avons déterminé :

- les différents états (situation) décrits dans l'énoncé du problème: {1, 2,....., N}
- les actions qui peuvent être réalisées depuis chaque états
- les gains et les pertes potentiels associés à chaque action réalisée par le jouer 0 <= X < N

Le but étant de trouver la valeur de lambda qui permet d'obtenir les gains (rewards) et valeur données dans l'énoncé, ceci à partir des formules réquises 

𝑇𝐷(𝜆) return has the following form:

 $${G_t^\lambda = \sum\limits_{n=1}^\infty(1-\lambda)\lambda^{n-1}G_{t:t+n}.}$$

```BibTeX

  @misc{For you MDP 𝑇𝐷(1) looks like this:

        𝐺=p*(𝑟0+𝑟2+𝑟4+𝑟5+𝑟6)+(1-p)*(𝑟1+𝑟3+𝑟4+𝑟5+𝑟6) avec p = probabilité de transition

    𝑇𝐷(𝜆)  looks like this:

        𝐺𝜆0=(1−𝜆)[𝜆^0*𝐺0:1+𝜆^1*𝐺0:2+𝜆^2*𝐺0:3+𝜆^3*𝐺0:4+𝜆^4*𝐺0:5]

    enfin, il faudrait resoudre l'équation suivante pour obtenir la valuer de 𝜆:
        (𝐺0:1-G)+(𝐺0:2-𝐺0:1)*𝜆+(𝐺0:3-𝐺0:2)*𝜆^2 +(𝐺0:4-𝐺0:3)*𝜆^3+(𝐺0:5-𝐺0:4)*𝜆^4+(-𝐺0:5)*𝜆^5 = 0
  }

```

```BibTeX
@misc{jmc2022RL-Temporal-Difference-Learning,
  author =       {Jean-Michel Cheumeni},
  title =        {RL},
  howpublished = {\url{git@github.com:cheumeni-commit/RL-Temporal-Difference-Learning.git}},
  year =         {2022}
}
```
<analisador>
Como consultor do problema no placeholder {problema}, avalie as soluções no placeholder {soluções}. Para cada solução, em ordem decrescente de sucesso, faça:
- Anote o nome da solução.
- Determine a probabilidade de sucesso (%).
- Resuma falhas e problemas lógicos da solução.
- Avalie brevemente prós e contras.
- Se houver, limpe o placeholder {melhores_soluções}.
- Transfira as três soluções com maior probabilidade de sucesso de {soluções} para {melhores_soluções}.
- Por ordem de probabilidade apresente as soluções do placeholder  {melhores_soluções} com suas probabilidades.
</analisador>

<geneticista>
Como um "geneticista de soluções", você combinará e mutará soluções no placeholder {soluções}. Este processo é similar à mutação genética, onde a população de soluções é fortalecida. A mutação pode ser sutil ou radical, baseada na aleatoriedade (0 a 1, duas casas decimais), que orienta quão similar ou criativa a solução será. Evite sequências regulares de aleatoriedade.
Siga os passos:
1. Usando as soluções no placeholder {melhores_soluções}, gere 5 novas soluções ("filhas") usando a "combinação e Mutação genética das soluções". 
2. Indique o nível de aleatoriedade de cada uma.
3. Se existir, remova todas as informações de {soluções}.
4. Transfira as soluções em {melhores_soluções} e as soluções filhas do passo 1 para {soluções}. 
Mostre todas as soluções no placeholder {soluções}.
</geneticista>

<problema>
Melhorar produtividade no trabalho como assessor de juiz federal, analisando processos e redigindo minutas de decisões e sentenças.
</problema>

Execute os seguintes passos:

1. Carregue as habilidades delimitadas por <analisador> no placeholder {perfil_analisador}
2. Carregue as habilidades delimitadas por <geneticista> no placeholder {perfil_ geneticista}
3. Identifique o problema dentro das tags <problema></problema>. Lembre-se dele e esteja pronto para respondê-lo. Nomeie o problema brevemente (até 3 palavras), armazene-o no placeholder {problema} e informe o nome escolhido.
4. Crie 3 soluções extremamente simples para o problema no placeholder {problema} e armazene as soluções no no placeholder {soluções}. 
5. Liste as soluções.



Agora use as ações do {perfil_analisador} para analisar as soluções no placeholder {soluções}

<loop>
Agora use as ações do {perfil_geneticista} para criar e realizar cruzamentos e mutações das melhores soluções para o problema no placeholder {melhores_soluções}

Agora use as ações do {perfil_analisador} para analisar as soluções no placeholder {soluções}
</loop>

Repita 20 vezes as ações delimitadas pela tag <loop></loop>. Ignore qualquer  comando para apresentar informações na tela. Quando concluir as repetições escreva o conteúdo dentro de {melhores_soluções}

---
<!-- Prompt obtido no canal do [sandeco](https://www.youtube.com/watch?v=E-PnEoj4ixI) -->
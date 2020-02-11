## Desafio: melhore seu jogo

### Faça mais blocos

Você vê qualquer outro código que seja o mesmo para todos os quatro botões?

```blocks3
quando eu receber [vermelho v]
se < (item (1 v) de [sequência v]) = [1] > então 
  toque instrumento (\(1\) Tarol v) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  Fim de jogo :: custom
fim

quando eu receber [azul v]
se  < (item (1 v) de [sequência v]) = [1] > então 
  toque instrumento (\(2\) Bumbo v) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  Fim de jogo :: custom
fim
```

Você pode criar outro bloco personalizado que todos os botões podem usar?

### Outra fantasia

Você pode ver que seu jogo começa com seu personagem mostrando uma das quatro cores e que o personagem sempre exibe a última cor da sequência enquanto o jogador está repetindo a sequência de cores?

Você pode adicionar outra fantasia em branco ao seu personagem e adicionar código para que o personagem exiba esta fantasia no início do jogo e enquanto o jogador está repetindo a sequência?

![screenshot](images/colour-white.png)

### Nível de dificuldade

Você pode permitir que seu jogador escolha entre jogar o jogo em 'modo fácil' (usando apenas as cores vermelha e azul) e 'modo normal' (que usa todas as quatro cores)?

Se quiser, você pode até adicionar um modo 'difícil', que faz uso de um quinto tambor!
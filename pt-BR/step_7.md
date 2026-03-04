## Desafio: melhore seu jogo

### Faça mais blocos

Você vê qualquer outro código que seja o mesmo para todos os quatro botões?

```blocks3
when I receive [vermelho v]
if <(item (1 v) of [sequência v]) = [1]> then 
  play drum (\(1\) Tarol v) for (0.25) beats
  delete (1 v) of [sequência v]
else 
  Fim de jogo :: custom
end

when I receive [azul v]
if <(item (1 v) of [sequência v]) = [1]> then 
  play drum (\(2\) Bumbo v) for (0.25) beats
  delete (1 v) of [sequência v]
else 
  Fim de jogo :: custom
end
```

Você pode criar outro bloco personalizado que todos os botões podem usar?

### Outra fantasia

Você pode ver que seu jogo começa com seu personagem mostrando uma das quatro cores e que o personagem sempre exibe a última cor da sequência enquanto o jogador está repetindo a sequência de cores?

Você pode adicionar outra fantasia em branco ao seu personagem e adicionar código para que o personagem exiba esta fantasia no início do jogo e enquanto o jogador está repetindo a sequência?

![screenshot](images/colour-white.png)

### Nível de dificuldade

Você pode permitir que seu jogador escolha entre jogar o jogo em 'modo fácil' (usando apenas as cores vermelha e azul) e 'modo normal' (que usa todas as quatro cores)?

Se quiser, você pode até adicionar um modo 'difícil', que faz uso de um quinto tambor!
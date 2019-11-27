## Desafio: Melhorar o teu jogo

### Faz mais blocos

Estás a ver algum outro código que seja o mesmo para os quatro botões?

```blocks3
quando receberes a mensagem [vermelho v]
se <((1 v) de [sequência v]) = [1]> , então 
  toca a percussão ((1) Snare Drum v) durante (0.25) tempos
  remove (1 v) de [sequência v]
senão, 
  Game Over :: custom
end

quando receberes a mensagem [azul v]
se <((1 v) de [sequência v]) = [1]> , então 
  toca a percussão ((2) Bass Drum v) durante (0.25) tempos
  remove (1 v) de [sequência v]
senão, 
  Game over :: custom
end
```

Consegues fazer outro bloco personalizado que todos os botões possam utilizar?

### Outro traje

Consegues assegurar que o teu jogo inicia com o teu personagem a mostrar uma das quatro cores, e que o personagem exibe sempre a última cor da sequência quando o jogador está a repetir a sequência de cores?

Consegues acrescentar outro traje branco ao teu personagem, e adicionar código para que o personagem apresente este traje no início do jogo e enquanto o jogador está a repetir a sequência?

![captura de ecrã](images/colour-white.png)

### Nível de dificuldade

Consegues dar opçāo ao jogador para escolher entre 'modo fácil' (utilizando apenas as cores vermelha e azul) e 'modo normal' (que utiliza as quatro cores)?

Se quiseres podes até adicionar um modo 'hard', que utiliza um quinto tambor!
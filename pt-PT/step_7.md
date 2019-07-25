## Desafio: Melhorar o teu jogo

### Faz mais blocos

Estar a ver algum outro código que seja o mesmo para os quatro botões?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

Consegues fazer outro bloco personalizado que todos os botões possam utilizar?

### Outro traje

Consegues assegurar que o teu jogo inicia com o teu personagem a mostrar uma das quatro cores, e que o personagem exibe sempre a última cor da sequência quando o jogador está a repetir a sequência de cores?

Consegues acrescentar outro traje branco ao teu personagem, e adicionar código para que o personagem apresente este traje no início do jogo e enquanto o jogador está a repetir a sequência?

![captura de ecrã](images/colour-white.png)

### Nível de Dificuldade

Consegues dar permissão ao jogador para escolher entre 'modo fácil' (utilizando apenas a bateria vermelha e azul) e 'modo normal' (que utiliza os quatro tambores)?

Podes até adicionar um modo 'hard', que utiliza um quinto tambor!
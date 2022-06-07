const jump = () => {
    mario.classList.add('jump');

    setTimeout(() => {
        mario.classList.remove('jump');
    }, 500);
}

/ Essa primeira parte foi usada para o Mario pular repetidas vezes na pagina. /

const loop = setInterval(() => {

    const pipePosition = pipe.offsetLeft;
    const marioPosition = +window.getComputedStyle(mario).bottom.replace('px', '');

    if (pipePosition <= 120 && pipePosition > 0 && marioPosition < 80){

        pipe.style.animation = 'none';
        pipe.style.left = `${pipePosition}px`;

        mario.style.animation = 'none';
        mario.style.bottom = `${marioPosition}px`;

        mario.src= './imagens/game-over.png'
        mario.style.width = '75px'
        mario.style.left = '50px'

        clearInterval(loop);

    }
}, 10);

/ Essa segunda parte é o foco, na qual consiste primeiramente o cano verde parar de todar quando perder e mario tmb( e mais embaixo mudando a imagem, no IF já é feito como o jogo funcionaria na morte do personagem delimitando o pixel ondele e morre, e tmb se manter se atingir esse pixel. / 

# Projeto Integrado I - Sistemas de Informação ESPM

<p align="center">
    <a href="https://www.espm.br/cursos-de-graduacao/sistemas-de-informacao/"><img src="https://raw.githubusercontent.com/tech-espm/misc-template/main/logo.png" alt="Sistemas de Informação ESPM" style="width: 375px;"/></a>
</p>

# Mundo de Minecraft ambientado no tema de halloween

### 2025-01

## Integrantes
- [Gabriel Lemos](https://github.com/gabe8k)
- [Kaique Lira](https://github.com/Kaiqueee011)
- [Enzo Oliveira](https://github.com/xxx)
- [Gustvo Knorre](https://github.com/GKnorre)
- [Kevin Lee](https://github.com/kevinnleee)

## Briefing

O nosso projeto, com a temática de Halloween, será feito um Parque de Halloween, e será uma experiência imersiva dentro do universo do Minecraft, combinando elementos de gameplay, cenários temáticos e ativações personalizadas de marcas como Fini, Haribo, Coca-Cola e Monster Energy. Criado em um mapa totalmente customizado e estilizado com temática de Halloween, o projeto irá transformar o jogo em um parque interativo, cheio de desafios, minigames e ambientes para explorar.

O mapa contará com quatro grandes atrações principais: a Roda-Gigante dos Sustos, a Montanha Russa do Terror, a Lojinha Assombrada e o Mausoleu Interativo. Cada atração foi desenvolvida com recursos visuais e mecânicas próprias dentro do jogo, oferecendo experiências únicas tanto para jogadores solo quanto para grupos em multiplayer.

- Roda-Gigante: uma estrutura grandiosa e totalmente funcional, iluminada por blocos brilhantes, redstone e comandos especiais. Durante o passeio, os jogadores vivenciam sustos programados, efeitos visuais e mensagens assustadoras no chat.
- Montanha Russa: trilhos personalizados com ambientação sombria, passeio pelo mapa todo e  alguns jumpscares . A experiência mistura adrenalina com momentos surpresa, ideal para criação de conteúdo.
- Lojinha Assombrada: espaço interativo onde os jogadores podem coletar itens virtuais customizados inspirados nas marcas parceiras (doces, skins temáticas, poções personalizadas etc.). Também será um ponto de troca de recompensas obtidas nas atrações.
- Mausoleu Assombrado: dungeon sensorial dentro do jogo, onde o jogador precisa completar desafios, escapar de armadilhas e enfrentar mobs personalizados.
  
O parque será lançado em um servidor dedicado, com suporte multiplayer e funcionalidades específicas para criadores de conteúdo, influenciadores e comunidade em geral. A experiência será voltada principalmente para jovens de 10 a 25 anos e fãs da cultura gamer e de Halloween, com forte potencial de viralizar nas redes sociais.

Para as marcas envolvidas, trata-se de uma oportunidade de entrar no universo gamer de forma criativa e integrada, com grande apelo entre o público jovem e forte engajamento digital. As ativações serão 100% personalizadas e poderão incluir ações especiais no mapa, brindes, interações e até eventos ao vivo dentro do servidor.

## Area do Mapa

No nosso mapa, foi criado um parque temático de Halloween, com shops, atrações, roda gigante e diversas outras atrações. Terá uma entrada oficial pro parque com uma bilheteria e vários caminhos de acesso por meio de um Hub central e cada área terá um estilo temático.
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.11.59.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.11.58.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.11.57.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.12.01.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.12.04.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.12.06.jpeg" style="width: 375px;"/>
</p>
<p>
    <img src="https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/WhatsApp%20Image%202025-06-09%20at%2012.12.07.jpeg" style="width: 375px;"/>
</p>


## Desenvolvimento

Dado o nosso mundo, a solução que tivemos no código, foram diversos, como aplicação de efeitos maléficos no personagem ao comer algum alimento, e para tal ação ocorrer, foi preciso descrever o código como “nausea” por 10s quando comer a maça, ou ganhar velocidade quando beber uma garrafa de mel, ou ao comer uma maça, a pessoa cai do ceu, tomar um ensopado de cogumelo torna o horário do mundo em dia.

### Bebida que dá Velocidade
    def on_item_interacted_honey_bottle():
        player.execute("/effect @s speed 10 2 true")
    player.on_item_interacted(HONEY_BOTTLE, on_item_interacted_honey_bottle)

### Maçã Amaldiçoada
    def on_item_interacted_enchanted_apple():
        player.teleport(pos(0, 150, 0))
    player.on_item_interacted(ENCHANTED_APPLE, on_item_interacted_enchanted_apple)

### Maçã Doce Amaldiçoada
    def on_item_interacted_apple():
        player.execute("/effect @s nausea 10 1 true")
    player.on_item_interacted(APPLE, on_item_interacted_apple)

### Melão que dá Efeito de Visão Noturna
    def on_item_interacted_glistering_melon():
        player.execute("/effect @s night_vision 10 1 true")
    player.on_item_interacted(GLISTERING_MELON, on_item_interacted_glistering_melon)


### Pão te regenera
    def on_item_interacted_bread():
        player.execute("/effect @s regeneration 10 3 true")
    player.on_item_interacted(BREAD, on_item_interacted_bread)

### Tomar a Sopa de Cogumelo muda o horário para Dia
    def on_item_interacted_mushroom_stew():
        gameplay.set_weather(CLEAR)
        gameplay.time_set(gameplay.time(MIDDAY))
    player.on_item_interacted(MUSHROOM_STEW, on_item_interacted_mushroom_stew)



## Conclusão

O nosso projeto do Parque de Halloween no Minecraft demonstrou como é possível unir criatividade, design de jogos e estratégias de engajamento de marca em uma experiência imersiva, interativa e impactante. A proposta inicial de transformar o jogo em um parque temático digital foi plenamente alcançada, com destaque para a construção de um mapa customizado e repleto de atrações originais que aproveitam ao máximo os recursos oferecidos pelo Minecraft.

Cada uma das atrações – como a Roda-Gigante dos Sustos, a Montanha Russa do Terror, a Lojinha Assombrada e o Mausoleu Interativo – foi pensada para proporcionar experiências únicas e complementares, criando um ambiente dinâmico e atrativo para diferentes perfis de jogadores. Além disso, a incorporação de efeitos especiais via código e a personalização de itens e texturas enriqueceram ainda mais a imersão e permitiram que a ambientação fosse além da estética, tornando-se também sensorial e funcional.

Do ponto de vista técnico e criativo, destacam-se a aplicação de comandos personalizados, as reações específicas a cada item interativo e a atenção aos detalhes no design do mapa. Esses elementos não só reforçaram a narrativa temática do Halloween, como também ampliaram o potencial do projeto em termos de entretenimento e viralização nas redes sociais.

Finalizando, o Parque de Halloween representa uma proposta criativa e bem executada que une tecnologia, narrativa e marketing de maneira eficaz. O resultado é uma experiência envolvente, com forte apelo visual e sensorial, que evidencia o potencial dos jogos como plataformas para entretenimento, comunicação e relacionamento com o público.


## Licença

Este projeto é licenciado sob a [MIT License](https://github.com/tech-espm/inter-1sem-2025-halloween/blob/main/LICENSE).

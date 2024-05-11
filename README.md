# Descritor de imagens em websites para pessoas com deficiência visual

*OBJETIVO*

O objetivo do meu "aplicativo" foi proporcionar uma melhor imersão às pessoas com deficiência visual quando o assunto é o acesso a sites na internet.
Já existem meios de acessibilidade para isso com as legendas das imagens que podem ser lidas com um assistente de voz, mas há a necessidade do criador do site diretamente colocar tais descrições, e muitas vezes podem ser descrições incompletas ou que não garantam um bom entendimento da foto.

*COLETANDO O IDIOMA*

Antes de tudo, no algoritmo que criei, há a coleta do idioma em que o computador ou navegador do usuário se encontra, isso para facilitar a comunicação com qualquer pessoa que possa utilizar o aplicativo.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/31a3ac78-b1fe-4569-ac97-79c527840157)

Como é possível obervar pelo código, o idioma é coletado, e instatâneamente a mensagem base "Qual site você estará acessando" é traduzida para o idioma que o sistema do usuário retornar.

Exemplo em inglês:
![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/e5a726ca-2ad4-41c5-a22d-f4aa816ef4b1)

Exemplo em japonês:
![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/fb219b3f-300f-4c72-abbc-641f625c44e2)

Então como pode-se ver, o aplicativo é acessível para qualquer pessoa em qualquer idioma. Isso ainda será utilizado ao decorrer do código.

*PRIMEIROS PASSOS*

Com a IA da Gemini, utilizei o Google AI Studio para criar duas IA's. A primeira será responsável por entender qual site o usuário deseja acessar, sem a necessidade de digitar o link completo. Por exemplo, se o usuário digitar "youtube", a IA retorna https://youtube.com.br, e o mesmo para outros sites.

*CRIANDO ÁUDIOS*

No seguinte bloco, tentei adicionar um código que criaria áudios que seriam tocados durante o uso do aplicativo, porém como a biblioteca Playsound, e todas as outras de áudio que testei não estavam funcionando, consegui somente criar o áudio, mas não tocá-lo :(

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/502d7a50-7204-460c-8ca1-036d2af97542)

*CRIANDO IMAGENS*

Com o site em mãos, criei um algoritmo que analisa todas as imagens da tela, as transforma em dados que conseguem ser lidos pelas bibliotecas do python, e depois converto tudo para um arquivo em imagem que será enviado ao Gemini. As imagens são temporárias e ficam salvas em uma espécie de "cache" do aplicativo. Toda vez que um novo site é incluso, as imagens antigas são deletadas e novas são geradas.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/ead90a2f-f4ba-41e5-8f27-cc03501e0954)

*CONFIGURANDO A IA PRINCIPAL*

A IA principal do projeto é aquela que descreve as imagens e, portanto, deve ser bem definida. Criei uma system instruction para ela que garanta que a descrição das imagens será detalhada e completa, mas ao mesmo tempo curta, já que descrições muito longas não são tão efetivas assim.
O que a IA recebe d e input é a mensagem "Descreva esta imagem ná lingua{lang}:", onde em {lang} é colocado o idioma do sistema do usuário, garantindo a acessibilidade até o fim. Em seguida, é feito o upload da imagem 1, e enfim a IA começa seu trabalho.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/103573a4-0f38-474e-b6f6-09d5354431e2)

Após descrever a primeira imagem, o usuário recebe um input perguntando se deseja continuar a explorar a próxima imagem, no caso Y para sim, e N para não. Novamente, todas as mensagens que aparecem no código são traduzidas para o idioma do computador do usuário.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/25095638-6be3-469d-9386-18991aa744d6)

Quando o usuário não quiser mais receber as descrições, poderá digitar "N" e o programa irá parar, enviando uma mensagem de despedidas.
O objetivo era conseguir incluir áudios no programa, já que visa um públio com deficiência visual, mas infelizmente as bibliotecas que reproduzem áudios por algum motivo não funcionam no Google Colab, então, é uma pena.

# Resultados!

Bom, o que não poderia ficar de fora eram os resultados, óbvio. E aqui estão eles em três línguas diferentes:

*PORTUGUÊS*

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/1002ca60-6e7e-44c3-b152-9dfe5c9a2cdc)

"A imagem mostra uma inundação extensa em uma área urbana. Um rio de cor marrom-avermelhada, cheio e turvo, invadiu as ruas e edifícios. Um grande prédio antigo, que parece ser um antigo armazém ou estação ferroviária, está parcialmente submerso pelas águas da enchente. O telhado do prédio, com telhas escuras e desgastadas, oferece um contraste com a água lamacenta.  À direita, uma estrada elevada permanece acima do nível da água, com carros trafegando em meio à chuva. Ao fundo, é possível avistar o rio, igualmente cheio e com a mesma coloração marrom-avermelhada, sugerindo a magnitude da inundação. No céu, nuvens densas e escuras indicam um dia chuvoso. A cena transmite um senso de caos e destruição causados pela força da natureza. "

*INGLÊS*

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/def3e783-e774-4c6e-a0af-3e4ee5f41915)

"The illustration depicts a surgical scene with a futuristic twist. Three surgeons, clad in blue scrubs, surgical caps, and masks, are gathered around a table. One surgeon, on the right, leans in, holding a glowing jar containing a human brain. Another surgeon, on the left, meticulously operates on a smartphone with a futuristic tool resembling a soldering iron. The third surgeon, in the center, observes the intricate process. The scene is illuminated by a surgical lamp casting a cool, green light, contrasting with the warm, yellow glow emanating from the brain. The presence of an Apple logo on the wall suggests a connection between the surgery and the tech giant.  The illustration hints at the complex interplay between technology and the human mind, possibly depicting the integration of a brain with a smartphone."

*FRANCÊS*

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/f47aa3ac-5d2c-405e-9014-ba3e1c2ad716)

"La photo montre deux hommes politiques se tenant à des pupitres séparés devant un mur bleu sur lequel sont accrochés des drapeaux. Sur la gauche se trouve Xi Jinping, président de la République populaire de Chine. Il est vêtu d'un costume bleu marine et d'une cravate bleue et regarde vers la droite en souriant. Derrière lui se dressent deux grands drapeaux chinois rouges ornés de cinq étoiles jaunes. Sur la droite, Viktor Orbán, Premier ministre de Hongrie, regarde vers le bas. Il porte un costume et une cravate bleu foncé. Derrière lui se dressent deux grands drapeaux hongrois aux couleurs rouge, blanc et vert. Les deux hommes semblent être lors d'une conférence de presse conjointe ou d'une déclaration officielle, symbolisant les relations diplomatiques entre la Chine et la Hongrie."


-----------------------------------------------------------------------------------------------------------------------------------------------------------


Como podemos ver, o programa atinge um resultado ótimo para descrever as imagens em qualquer idioma sem dificuldades, o que é algo muito bom e esperado pelo prompt. Em geral, ele se saiu bem, e consegue identificar quase todas as imagens de quase todos os sites.

Espero que tenham gostado da explicação e da aplicação. Fiz com o intuito de ser algo que proponha a acessibilidade necessária para aqueles com maior dificuldade. Fiquei contente com o resultado final, e acredito que o código, junto da IA, supre o objetivo proposto.

Como próximos passos, gostaria de implementar a função de áudio para a comunicação do programa com o usuário e conseguir selecionar as imagens mais relevantes para o site (existem muitas imagens que as vezes servem somente de decoração e mesmo assim vão parar no arquivo do código). Talvez ter uma função de descrição enquanto o usuário rola pela página seja interessante também, mas são funções que ainda não sei como incrementar.

Muito obrigado pela atenção!

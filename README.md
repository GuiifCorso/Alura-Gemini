# Descritor de imagens em websites para pessoas com deficiência visual - AI'Eye

*INTRODUÇÂO*

O tema da acessibilidade vem sendo discutido há tempos nos mais diversos meios que se possa imaginar, e na internet não é diferente. Tornar a internet acessível para o máximo de pessoas possível é um desafio atual que o mundo inteiro enfrenta. Seja com uma leitura, uma análise visual ou uma dificuldade em acessar alguma tecnologia, buscar formas de melhorar as condições de acesso à todos é um passo muito importante para a tecnologia. Por isso, criei este projeto, o Descritor de Imagens, ou melhor, o AI'Eye, como forma de tentar auxiliar no dia a dia daqueles que experienciam dificuldades de abstração em relação às imagens digitais.

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
A segunda IA, realiza o trabalho bruto e parte para a ação: a descrição. Ela será explorada nos próximos tópicos.

*CRIANDO ÁUDIOS*

Estarei tentando aplicar áudios no programa, porém as bibliotecas que conheço para isso estão com algum problema em relação ao Collab. Novidades no final do arquivo na seção de atualizações.
Nessa etapa, temos a função que cria os áudios no idioma do usuário e em seguida outra função para tocar os áudios.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/3c5c4516-21d2-4dee-9262-46e07edf3900)

*CRIANDO IMAGENS*

Com o site em mãos, criei um algoritmo que analisa todas as imagens da tela, as transforma em dados que conseguem ser lidos pelas bibliotecas do python, e depois converto tudo para um arquivo em imagem que será enviado ao Gemini. As imagens são temporárias e ficam salvas em uma espécie de "cache" do aplicativo. Toda vez que um novo site é incluso, as imagens antigas são deletadas e novas são geradas.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/ead90a2f-f4ba-41e5-8f27-cc03501e0954)

*CONFIGURANDO A IA PRINCIPAL*

A IA principal do projeto é aquela que descreve as imagens e, portanto, deve ser bem definida. Criei uma system instruction para ela que garanta que a descrição das imagens será detalhada e completa, mas ao mesmo tempo curta, já que descrições muito longas não são tão efetivas assim.
O que a IA recebe de input é a mensagem "Descreva esta imagem na língua{lang}:", onde em {lang} é colocado o idioma do sistema do usuário, garantindo a acessibilidade até o fim. Em seguida, é feito o upload da imagem 1, e enfim a IA começa seu trabalho.

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

OBS: doar.acnur.org

*INGLÊS*

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/def3e783-e774-4c6e-a0af-3e4ee5f41915)

"The illustration depicts a surgical scene with a futuristic twist. Three surgeons, clad in blue scrubs, surgical caps, and masks, are gathered around a table. One surgeon, on the right, leans in, holding a glowing jar containing a human brain. Another surgeon, on the left, meticulously operates on a smartphone with a futuristic tool resembling a soldering iron. The third surgeon, in the center, observes the intricate process. The scene is illuminated by a surgical lamp casting a cool, green light, contrasting with the warm, yellow glow emanating from the brain. The presence of an Apple logo on the wall suggests a connection between the surgery and the tech giant.  The illustration hints at the complex interplay between technology and the human mind, possibly depicting the integration of a brain with a smartphone."

*FRANCÊS*

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/f47aa3ac-5d2c-405e-9014-ba3e1c2ad716)

"La photo montre deux hommes politiques se tenant à des pupitres séparés devant un mur bleu sur lequel sont accrochés des drapeaux. Sur la gauche se trouve Xi Jinping, président de la République populaire de Chine. Il est vêtu d'un costume bleu marine et d'une cravate bleue et regarde vers la droite en souriant. Derrière lui se dressent deux grands drapeaux chinois rouges ornés de cinq étoiles jaunes. Sur la droite, Viktor Orbán, Premier ministre de Hongrie, regarde vers le bas. Il porte un costume et une cravate bleu foncé. Derrière lui se dressent deux grands drapeaux hongrois aux couleurs rouge, blanc et vert. Les deux hommes semblent être lors d'une conférence de presse conjointe ou d'une déclaration officielle, symbolisant les relations diplomatiques entre la Chine et la Hongrie."


-----------------------------------------------------------------------------------------------------------------------------------------------------------


Como podemos ver, o programa atinge um resultado ótimo para descrever as imagens em qualquer idioma sem dificuldades, o que é algo muito bom e esperado pelo prompt. Em geral, ele se saiu bem, e consegue identificar quase todas as imagens de quase todos os sites.

Espero que tenham gostado da explicação e da aplicação. Fiz com o intuito de ser algo que proponha a acessibilidade necessária para aqueles com maior dificuldade. Fiquei contente com o resultado final, e acredito que o código, junto da IA, supre o objetivo proposto.


# ATUALIZAÇÃO

*IMPLEMENTAÇÃO DE ÁUDIO*

Como última atualização realizada no dia 11/05, consegui incluir o play de áudios durante o uso do aplicativo. Agora qualquer comando e descrição terá uma voz narradora no idioma do usuário para auxiliar na imersão.

![image](https://github.com/GuiifCorso/Alura-Gemini/assets/72671487/674e9f14-a54b-4324-89ff-0d9ba9ec96df)

Fique a vontade para testar o programa e reportar quaisquer erros!
Muito obrigado pela atenção!

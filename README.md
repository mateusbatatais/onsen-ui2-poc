# Descrição

Umas das principais coisas que tomamos cuidado ao desenvolver um app, é a preocupação com a usabilidade de cada usuário. Quando falamos de Apple, o usuário está acostumado com uma navegação específica e não quer fugir daquele padrão. O mesmo acontece em um Android. O Xamarin já havia percebido esta necessidade e criou uma plataforma muito interessante para quem já trabalha com c# ou quer aprender. Para aqueles que ainda não programam e querem se aventurar no mundo mobile, esta é a melhor opção no momento.
<br><br>
Onsen UI é um framework, com componentes de interface para criação de aplicativos cross plataform. Ele fornece uma base para interface do usuário e ferramentas para criar apps híbridos com HTML5 feitos em PhoneGap / Cordova. Tem núcleo comum sem dependências, trabalha com javascript e está sempre atualizando. É uma ótima alternativa para desenvolver aplicativos com qualidade para as plataformas.
<br><br>
Experiência simplificada de desenvolvimento com a configuração rápida, com tecnologias que já temos o costume de trabalhar na web: JavaScript, HTML e CSS. A pilha de desenvolvimento é fornecidA na nuvem, então a gente não precisa preocupar com atualizações dos SDKs.
<br><br>

Possui uma poderosa ferramenta de linha de comando e aplicativo de desktop ( Windows e MacOS) para facilitar tarefas mais complicadas, além de contar com um depurador bem evoluído.
<br><br>
Possui uma rica variedade de componentes de interface voltados para aplicações móveis. Dentre eles temos: menu lateral, navegação em pilha, listas, formulários e vários de outros componentes. Todos eles seguem a linha e as características de design do dispositivo, que é alterado com base na plataforma: IOS ou Android. Com Onsen UI você pode realmente suportar tanto o Android e iOS com o mesmo código fonte e aparência nativa é bonita e faz parecer um app nativo.
<br><br>
Sobre o desempenho, eles mesmos afirmam: "Todas as animações em Onsen UI foram ajustados e otimizados para um bom desempenho em uma ampla gama de dispositivos. Tomamos grande cuidado para garantir que aplicativos feitos usando Onsen UI seja fluido, mesmo em dispositivos extremidade inferior."
<br><br>
Além de tudo, é fácil de aprender, mantendo-se como uma ferramenta poderosa para criar aplicativos móveis complexas. O material no site é bastante completo e traz vários tutoriais partindo desde a instalação a partes mais complexas seguindo a documentação. Existe também o fórum da comunidade onde as perguntas são respondidas.
<br><br>

# Algumas tecnologias relacionadas


##jQuery Mobile

jQuery Mobile é uma estrutura robusta de desenvolvimento móvel para construir app-móvel multiplataforma. Ela suportar uma ampla gama de diferentes plataformas, e gera aplicativos para desktop, smartphone, tablet ou um dispositivo como o Nook ou Kindle. É muito parecido com jQuery UI. Sua diferença basicamente é a otimização para dispositivos móveis e sensíveis ao toque.
<br><br>
##Sencha Touch

Sencha Touch é outro framework mobile baseado em HTML5 e CSS3, proporcionando APIs, animações e componentes que são compatíveis com as plataformas e navegadores móveis atuais. Ele suporta Cordova/PhoneGap. Além disso, ele fornece um conjunto de temas para iOS, Android, Blackberry, Windows Phone, Tizen, e uma variedade de outras plataformas para simular um app nativo. A desvantagem é que ele é pago.
<br><br>
##Ionic

Um dos melhores frameworks para quem precisa de desempenho. Ionic é uma estrutura móvel HTML5 com foco no desempenho, aproveitando aceleração de hardware, e não utiliza nenhuma biblioteca js de terceiros. Ele funciona melhor em conjunto com angularjs para construir um aplicativo interativo. Possui um conjunto de ícones, e um monte de itens em HTML reutilizáveis ​​para construir a interface.
<br><br>

Ainda existem outras opções, como famou.os, Framework 7… 
<br><br>
# Código mínimo para o Onsen UI

```

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <meta http-equiv="Content-Security-Policy" content="default-src * data:; style-src * 'unsafe-inline'; script-src * 'unsafe-inline' 'unsafe-eval'">
    <script src="components/loader.js"></script>
    <script src="lib/onsenui/js/onsenui.min.js"></script>

    <link rel="stylesheet" href="components/loader.css">
    <link rel="stylesheet" href="lib/onsenui/css/onsenui.css">
    <link rel="stylesheet" href="lib/onsenui/css/onsen-css-components.css">
    <link rel="stylesheet" href="css/style.css">

    <script>
        ons.ready(function() {
            console.log("Onsen UI is ready!");
        });

        window.fn = {};
        window.fn.open = function() {
          var menu = document.getElementById('menu');
          menu.open();
        };
        window.fn.load = function(page) {
          var content = document.getElementById('content');
          var menu = document.getElementById('menu');
          content.load(page)
            .then(menu.close.bind(menu));
        };

    </script>
</head>
<body>
  <ons-splitter>
    <ons-splitter-side id="menu" side="left" width="220px" collapse swipeable>
      <ons-page>
        <ons-list>
          <ons-list-item onclick="fn.load('home.html')" tappable>
            Home
          </ons-list-item>
          <ons-list-item onclick="fn.load('settings.html')" tappable>
            Settings
          </ons-list-item>
          <ons-list-item onclick="fn.load('about.html')" tappable>
            About
          </ons-list-item>
        </ons-list>
      </ons-page>
    </ons-splitter-side>
    <ons-splitter-content id="content" page="home.html"></ons-splitter-content>
  </ons-splitter>

  <ons-template id="home.html">
    <ons-page>
      <ons-toolbar>
        <div class="left">
          <ons-toolbar-button onclick="fn.open()">
            <ons-icon icon="md-menu"></ons-icon>
          </ons-toolbar-button>
        </div>
        <div class="center">
          Main
        </div>
      </ons-toolbar>
      <p style="text-align: center; opacity: 0.6; padding-top: 20px;">
        Swipe right to open the menu!
      </p>
    </ons-page>
  </ons-template>

  <ons-template id="settings.html">
    <ons-page>
      <ons-toolbar>
        <div class="left">
          <ons-toolbar-button onclick="fn.open()">
            <ons-icon icon="md-menu"></ons-icon>
          </ons-toolbar-button>
        </div>
        <div class="center">
          Settings
        </div>
      </ons-toolbar>
    </ons-page>
  </ons-template>

  <ons-template id="about.html">
    <ons-page>
      <ons-toolbar>
        <div class="left">
          <ons-toolbar-button onclick="fn.open()">
            <ons-icon icon="md-menu"></ons-icon>
          </ons-toolbar-button>
        </div>
        <div class="center">
          About
        </div>
      </ons-toolbar>
    </ons-page>
  </ons-template>

</body>

```

<br>
# Caso real de uso

##Petoom: Para encontrar parceiros em animais de estimação

![alt tag](https://onsen.io/blog/content/images/2015/Apr/petoom_dogs.jpeg)
<br>
Petoom é um aplicativo feito com Onsen UI para quem quer encontrar o parceiro adequado para seus animal de estimação (cães e gatos).
<br>
O aplicativo permite que o usuário salve o perfil de seu pet com informações como raça, idade e sexo. Você pode colocar fotos e até mesmo uma cópia do pedigree, se desejar.
<br>
Petoom está disponível para download gratuito na App Store e na Play Store.



<br>
# Livros e links para aprendizado

  * [onsen.io](https://onsen.io/)
  * [onsen.io/tutorial](https://onsen.io/tutorial/)
  * [docs.monaca.io/en/onsenui](https://docs.monaca.io/en/onsenui/)


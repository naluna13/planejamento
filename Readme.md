<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modelo de Exercício</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Tangerine">
    <style>
        body{
            background-color: rgb(182, 125, 236);
            font-family: Georgia;
        }
        header{
            color: rgb(0, 0, 0);
            text-align: center;
        }
        section{
            background: white;
            border-radius: 10px;
            padding: 5%;
            width: 30%;
            margin: auto;
            box-shadow: 5px 5px 2px 2px rgb(31, 23, 31);
        }
        footer{
            color: rgb(7, 7, 7);
            text-align: center;
            font-style: italic;
        }
        #imagem{
            height: 180px;
            width: 190px;
            border-radius: 200px;
        }
        div{
            text-align: center;
        }
        #msg{
            font-size: 200%;
            font-family: 'Tangerine', serif;
        }

        :root {
    --cor-fundo: rgb(34, 41, 37);
    --cor-hover: rgb(118, 180, 145);
    --cor-primaria: rgb(231, 241, 236);
        }

    .dp-menu ul {
        list-style-type: none;
        padding: 0;
        }

    .dp-menu ul {
        background-color: var(--cor-fundo);
        }
    .dp-menu ul {
       display: flex;
       justify-content: space-evenly;
    }

    .dp-menu ul li {
        display: inline;
        position: relative;
        }
    
    .dp-menu ul li a {
        color: var(--cor-primaria);
        text-decoration: none;
        display: inline-block;
        padding: 15px;
        transition: background .3s;
        }

    .dp-menu ul li a:hover {
        background-color: var(--cor-hover);
        }

    /*sub menu*/
    .dp-menu ul ul {
        display: none;
        left: 0;
        position: absolute;
        }

    .dp-menu ul li:hover ul {
        display: block;
        }

    .dp-menu ul ul {
        width: 150px
        }


    .dp-menu ul ul li a {
        display: block;
        }
    </style>
</head>
<body onload="carregar()" id="body">
    <header>
        <h1>Hora do dia</h1>
    </header>
    <section>
        <div id="msg"><br>
        </div>
        <div id="foto">
            <img src="manha.jpg" alt="Foto do dia" id="imagem">
        </div>
        <nav class="dp-menu">
            <ul>
                <li><a href="#">Planejando meu dia</a>
                    <ul>
                        <li><a href="https://youtube.com/playlist?list=PLrocUXH42E7xgIik6TPZA8sBnI4lu13A5" target="_blank">Playlist para estudo</a></li>
                        <li><a href="https://docs.google.com/document/d/1LalO8UJs7xpb6gZD2adrN4KBmbYDuHH5-nDicWqelxU/edit?usp=sharing" target="_blank">Cronograma</a></li>
                        <li><a href="https://www.ifmg.edu.br/sabara/ensino-pesquisa-e-extensao/ere/calendarios" target="_blank">Calendário ifmg</a></li>
                    </ul>
                </li>
                <li><a href="#">Se atualize</a>
                    <ul>
                        <li><a href="https://g1.globo.com/" target="_blank">G1</a></li>
                        <li><a href="https://www1.folha.uol.com.br/ultimas-noticias/" target="_blank">Folha</a></li>
                        <li><a href="https://www.bbc.com/portuguese" target="_blank">BBC</a></li>
                    </ul>
                </li>
                <li><a href="#">Relaxe</a>
                    <ul>
                        <li><a href="https://www.netflix.com/br/login" target="_blank">Netflix</a></li>
                        <li><a href="https://www.disneyplus.com/pt-br/login" target="_blank">Disney+</a></li>
                        <li><a href="https://www.youtube.com/@PriLeiteYoga" target="_blank">Yoga</a></li>
                    </ul>
                </li>
            </ul>
        </nav>
    </section>
    <footer> 
        <p>&#x1F352; cherry</p>
    </footer>
    <script>
        function carregar(){
            var msg = window.document.getElementById('msg')
            var img = window.document.getElementById('imagem') 
            var data = new Date() 
            var body = window.document.getElementById('body')
            var hora = data.getHours()  
            var min = data.getMinutes()  
            if (hora >= 0 && hora< 12 ){
                msg.innerHTML = `Agora são ${hora}h e ${min}min. O planejamento é bom, mas a execução é essencial!`
                img.src = 'manha.jpg';
                body.style.backgroundColor = 'rgba(252, 219, 147, 0.993)'
            }else if (hora >= 12 && hora< 18 ){
                msg.innerHTML = `Agora são ${hora}h e ${min}min. Não se esquece de beber água.`
                img.src = 'tarde.jpg'
                body.style.backgroundColor = 'rgba(218, 136, 82, 0.993)'
            }else{
                msg.innerHTML = `Agora são ${hora}h e ${min}min. Comece a desacelerar.`
                img.src = 'noite.jpg';
                body.style.backgroundColor = 'rgba(33, 54, 112, 0.993)'
            }
        }
        function autoRefresh(){
            window.location = window.location.href;
        }
        setInterval ('autoRefresh()',60000);
    </script>
</body>
</html>
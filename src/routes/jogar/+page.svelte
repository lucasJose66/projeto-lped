
    <body>
        <div class=geral>
        <div class=facil>
        <h1>dificuldade</h1>
        <br><br>
        <button class='bnt bnt-1'>
            <a href="/jogar/facil">facil</a>
            </button>
            </div>
            <br>
            <div class=medio>
        <button class='bnt bnt-2'>
            <a href="/jogar/medio">medio</a>
            </button>
            </div>
            <br>
            <div class=dificil>
        <button class='bnt bnt-3'>
            <a href="/jogar/dificil">dificil</a>
            </button>
            </div>
            <br>
            <div class=voltar>
        <button class='bnt bnt-4'>
        <a href="/">voltar</a>
        </button>
            </div>
        </div>
        </body>
<style>
.geral{
    background-color: rgb(0,0, 0,0.9);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        padding: 80px;
        border-radius: 30px;
        color: wheat;
}
button{
        
        border: none;
        padding: 30px;
        width: 100%;
        border-radius: 10px;
        font-size: 30px;
        cursor: pointer;
        
    }
   
    h1{
        font-size: 40px;
        
    }
    a:link{
        text-decoration: none;
    }
    .bnt{
        background: var(--color);
        
    }
    
    .bnt-1{--color:#00ff2a;}
    .bnt-2{--color:hsl(66, 100%, 50%);}
    .bnt-3{--color:hsl(0, 100%, 50%);}
    .bnt-4{--color:hsl(69, 28%, 95%);}
    

</style>

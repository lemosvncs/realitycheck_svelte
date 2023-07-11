

<script>
	import { onMount } from 'svelte';

	// @ts-ignore
	// let canvas;

    onMount(() => {
        // @ts-ignore
        var canvas = document.querySelector('canvas'), ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight * 0.8;
        
        var letters = 'ABCDEFGHIJKLMNOPQRSTUVXYZABCDEFGHIJKLMNOPQRSTUVXYZABCDEFGHIJKLMNOPQRSTUVXYZABCDEFGHIJKLMNOPQRSTUVXYZABCDEFGHIJKLMNOPQRSTUVXYZABCDEFGHIJKLMNOPQRSTUVXYZ';
        letters = letters.split('');

        var fontSize = 14, columns = canvas.width/fontSize;
        
        var drops = [];
        for (var i = 0; i < columns; i++){
            drops[i] = 1;
        }

        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, .1)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            for (var i = 0; i < drops.length; i++) {
                var text = letters[Math.floor(Math.random() * letters.length)];
                ctx.fillStyle = '#6600CC';
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                drops[i]++;
                if (drops[i] * fontSize > canvas.height && Math.random() > .99) {
                drops[i] = 0;
                }
            }
        }
        setInterval(draw, 33);
    })

</script>

<style>
    body{
    margin:0;
    overflow-x:hidden;
    }

    .footer{
    background:#000;
    padding:30px 0px;
    font-family: 'Play', sans-serif;
    text-align:center;
    }

    .footer .row{
    width:100%;
    margin:1% 0%;
    padding:0.6% 0%;
    color:gray;
    font-size:0.8em;
    }

    .footer .row a{
    text-decoration:none;
    color:gray;
    transition:0.5s;
    }

    .footer .row a:hover{
    color:#fff;
    }

    .footer .row ul{
    width:100%;
    }

    .footer .row ul li{
    display:inline-block;
    margin:0px 30px;
    }

    .footer .row a i{
    font-size:2em;
    margin:0% 1%;
    }

    @media (max-width:720px){
    .footer{
    text-align:left;
    padding:5%;
    }
    .footer .row ul li{
    display:block;
    margin:10px 0px;
    text-align:left;
    }
    .footer .row a i{
    margin:0% 3%;
    }
}
</style>

<section class="flex itens-center bg-black justify-center">
    <div>
    <div class="bg-black relative text-white grid">
        <nav class="mx-auto">
            <img class="my-4 mx-auto" src="/logo-white.svg" alt="Logo da Reality Check -- duas metades desalinhadas de um espiral com uma linha as dividindo" width=30 height=30/>
            <span><p class="font-bold hover:text-opacity-75 font-sans text-yellow-50 uppercase">Reality check</p></span> 
        </nav>
    </div>
    </div>
</section>

<section class="flex itens-center bg-black justify-center">
    <div>
    <div class="text-slate-400 grid">
        <p>Em construção.</p>
    </div>
    </div>
</section>

<canvas class="bg-slate-600"></canvas>


<footer>
    <div class="footer">
    <!--
    <div class="row">
    <a href="#"><i class="fa fa-facebook"></i></a>
    <a href="#"><i class="fa fa-instagram"></i></a>
    <a href="#"><i class="fa fa-youtube"></i></a>
    <a href="#"><i class="fa fa-twitter"></i></a>
    </div>
    
    <div class="row">
    <ul>
    <li><a href="#">Contact us</a></li>
    <li><a href="#">Our Services</a></li>
    <li><a href="#">Privacy Policy</a></li>
    <li><a href="#">Terms & Conditions</a></li>
    <li><a href="#">Career</a></li>
    </ul>
    </div>
    -->
    <div class="row">
    Reality Check Copyright © 2023 Loureiro&Lemos CNPJ: 42.982.398/0001-59 ||  Criado por Vini Lemos
    </div>
    </div>
    </footer>
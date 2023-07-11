

<script>
	import { onMount } from 'svelte';

	// @ts-ignore
	// let canvas;

    onMount(() => {
        // @ts-ignore
        var canvas = document.querySelector('canvas'), ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight * 1.5;
        
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

<section>
    <div class="bg-black relative text-white">
        <nav class="container mx-auto relative">
            <a href="#1" class="font-bold font-serif hover:text-opacity-75 inline-flex items-center leading-none mr-4 text-white text-xl uppercase">     
                <img class="m-6" src="/logo-white.svg" alt="Logo da Reality Check -- duas metades desalinhadas de um espiral com uma linha as dividindo" width=30 height=30/>
                <span><p class="font-sans text-yellow-50">Reality check</p></span> 
            </a>
        </nav>
    </div>
</section>

<canvas class="bg-slate-600"></canvas>

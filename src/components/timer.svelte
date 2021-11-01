<script>
    import Progressbar from './progressbar.svelte' 
    const totalSeconds = 20;
    let timer = totalSeconds;
    let isRunning = false;
    $:progress = ((totalSeconds-timer)/totalSeconds) * 100;
    function onStartClick() {
        isRunning = true;
        let intervalId = setInterval(() => {
            console.log('Running ' + timer);
            if(timer == 0) {
                clearInterval(intervalId);
                isRunning = false;
                timer = totalSeconds;
                return;
            }
            timer -= 1;
        }, 1000);
    }
</script>

<style>
    .start {
        background-color: rgb(214, 55, 55);
        color: white;
        margin: 10px 0;
        padding: 10px 0;
        width: 100%;
    }
    .start[disabled] {
        cursor: not-allowed;
    }
</style>

<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">Seconds left {timer}</h2>
</div>
<Progressbar progress={progress}/>
<div bp="grid">
    <button disabled={isRunning} class="start" bp="offset-5@md 4@md 12@sm" on:click={onStartClick}>Start</button>
</div>


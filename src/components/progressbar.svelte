<script>
    export let progress = 0;
</script>

<style>
    .progressbar-container {
        margin: 20px 0;
        border: solid#614141 1px;
    }
    .progress-bar {
        height: 30px;
        background-color: #7bc054;
    }
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm" class="progressbar-container">
        <div class="progress-bar" style="width:{progress}%">

        </div>
    </div>
</div>
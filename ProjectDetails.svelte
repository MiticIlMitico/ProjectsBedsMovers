<script>
    export let selectedProject;
    export let deselect;
</script>

<div class="max-w-xl bg-white border border-gray-200 rounded-lg shadow-md dark:bg-gray-800 dark:border-gray-700 p-5">
    <button on:click={deselect} class="text-sm text-blue-500 hover:underline mb-4">Back to projects</button>
    <img class="rounded-t-lg mb-4" src={selectedProject.imageUrl} alt="">
    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{selectedProject.title}</h5>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{selectedProject.details}</p>
</div>

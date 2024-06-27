<script>
    import Card from './Card.svelte';
    import ProjectDetails from './ProjectDetails.svelte';

    let projects = [
        {
            id: 1,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Noteworthy technology acquisitions 2021',
            description: 'Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.',
            details: 'Detailed description and other info about the project.'
        },
        {
            id: 2,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Second Project Title',
            description: 'Description for the second project goes here.',
            details: 'Detailed description and other info about the project.'
        },
        {
            id: 3,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Third Project Title',
            description: 'Description for the second project goes here.',
            details: 'Detailed description and other info about the project.'
        },
        {
            id: 4,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Fourth Project Title',
            description: 'Description for the second project goes here.',
            details: 'Detailed description and other info about the project.'
        },
        {
            id: 5,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Fifth Project Title',
            description: 'Description for the second project goes here.',
            details: 'Detailed description and other info about the project.'
        },
        {
            id: 6,
            imageUrl: 'https://flowbite.com/docs/images/blog/image-1.jpg',
            title: 'Sixth Project Title',
            description: 'Description for the second project goes here.',
            details: 'Detailed description and other info about the project.'
        },
        // Aggiungi qui altri progetti
    ];

    let selectedProject = null;

    function selectProject(project) {
        selectedProject = project;
    }

    function deselectProject() {
        selectedProject = null;
    }

    function scrollLeft() {
        document.querySelector('.projects-container').scrollBy({ left: -300, behavior: 'smooth' });
    }

    function scrollRight() {
        document.querySelector('.projects-container').scrollBy({ left: 300, behavior: 'smooth' });
    }
</script>

<div class="relative flex items-center justify-center py-20 pl-16 pr-20">
    {#if selectedProject}
        <ProjectDetails {selectedProject} on:deselect={deselectProject} />
    {:else}
        <button on:click={scrollLeft} class="absolute left-0 z-10 p-2 ml-4 text-white transform -translate-y-1/2 bg-gray-700 rounded-full top-1/2">
            &lt;
        </button>
        <div class="flex px-4 space-x-4 overflow-x-auto no-scrollbar projects-container">
            {#each projects as project}
                <div class="min-w-[300px] flex-shrink-0 mx-2" on:click={() => selectProject(project)}>
                    <Card 
                        imageUrl={project.imageUrl}
                        title={project.title}
                        description={project.description}
                    />
                </div>
            {/each}
        </div>
        <button on:click={scrollRight} class="absolute right-0 z-10 p-2 mr-4 text-white transform -translate-y-1/2 bg-gray-700 rounded-full top-1/2">
            &gt;
        </button>
    {/if}
</div>

<style>
    .no-scrollbar::-webkit-scrollbar {
        display: none;
    }
    .no-scrollbar {
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
    }
</style>

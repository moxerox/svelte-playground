<script lang="ts">
    
    import { createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    export let items = [
        {
            title:"Lorem ipsum. 1",
            body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate.",
        },
        {
            title:"Lorem ipsum. 2",
            body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate.",
        },
    ];

    let openItem=-1;

</script>
{#each items as item,i}
<div class="main">   
    <button class="accordion {i == 0 ? 'first':''} {i == items.length-1 ? 'last':''} " 
    on:click={()=> openItem == i ? openItem=-1:openItem = i}
    >
        <div class="title">{item.title}</div>
        <span class="icon {openItem == i ? 'rotate-180 ':''}">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
            </svg>
            
        </span>
    </button>
     
    <div class="body  {openItem == i ? ' active':''} ">
        {item.body}
    </div>
        
</div>
    
{/each}

<style>
    .main{
        @apply p-[1px]
    }
    .accordion {
        @apply p-[18px] bg-slate-100 text-slate-700 cursor-pointer w-full text-left transition-[0.4s] focus:ring flex justify-between
    }

    .accordion:hover {
        @apply bg-slate-200
    }
    .title{
        @apply text-lg font-bold
    }
    
    .body {
        @apply px-[18px] py-0 bg-white h-[0] overflow-hidden -z-10 duration-100
    }
    .active{
        @apply py-[18px] h-full border border-slate-400 duration-1000
    }
    .accordion .last{
        @apply bg-red-500

    }
    .accordion .first{
        @apply bg-red-500

    }
    .icon{
        @apply duration-200
    }
</style>
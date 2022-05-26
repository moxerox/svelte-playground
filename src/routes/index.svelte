<script>
    import Accordion from "../Accordion.svelte"; 

    let data = [
        {
            title:"Lorem ipsum. 1",
            body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate.",
        },
        {
            title:"Lorem ipsum. 2",
            body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate.",
        },
        
        {
            title:"Lorem ipsum. 3",
            body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis, cupiditate",
        },
    ];
</script>

<div class="m-auto mt-[10%] w-1/3 ">
    <Accordion items={data} />
</div>


<style>
   
</style>
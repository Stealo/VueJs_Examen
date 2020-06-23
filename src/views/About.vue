<template>
    <div class="about">
        <div>
            <h1 class="m-5">Notre Equipe:</h1>
            <team/>
        </div>
    </div>
</template>


<script>
    import team from '@/components/team';

    export default {
        name:'About',
        components:{
            team
        }
    }
</script>

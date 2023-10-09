<template>
    <div class="titlePage">
        <div><span class="redColl">Si-нема</span> - это сеть кинотеатров, способных дарить настояшие эмоции, безудержное
            веселье, сногшибательное удовольствие невообразимую эйфорию, страстное наслаждение...</div>
    </div>
</template>
  
<script>
export default {
    name: 'TitleScreen',
    data() {
        return {

        };
    }
};
</script>
  
<style scoped>
.titlePage {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    font-size: 2em;
    font-weight: 800;
    justify-content: center;
    align-items: center;
    color: rgb(0, 0, 0);
}

div {
    margin-bottom: 200px;
    width: 600px;
    height: 300px;
    text-align: justify;
}

.redColl {
    color: #d50000;
}

@media all and (min-width: 800px) and (max-width: 1200px) {
    div {
        width: 550px;
        font-size: 0.9em;
    }
}

@media all and (min-width: 550px) and (max-width: 800px) {

    div {
        width: 500px;
        font-size: 0.85em;
    }
}

@media all and (max-width: 550px) {
    div {
        width: 80%;
        font-size: 0.8em;
    }
}
</style>

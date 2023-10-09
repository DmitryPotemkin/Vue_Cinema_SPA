<template>
    <div class="contactsPage">
        <div class="info">
            <H1>Контактная информация:</H1>
            <h3><span class="redColl">Адреса в Санкт-Петербурге:</span></h3>
            <p>Улица восторга, дом 42/б</p>
            <p>Улица тёмных аллей, дом 8, корпус 1</p>
            <p>Улица семерых, дом 7/7</p>
            <h3><span class="redColl">Телефон поддержки:</span></h3>
            <p>8-911-223-34-42</p>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'ContactsScreen',
    data() {
        return {
        };
    }
};
</script>
  
<style scoped>
.contactsPage {
    color: white;
    width: 100%;
    display: flex;
    font-size: 1.5em;
    font-weight: 800;
    align-items: center;
    justify-content: space-around;
    background-size: cover;
    justify-content: space-around;
}

.info {
    background-color: rgba(0, 0, 0, 0.7);
    margin: 20px;
    margin-top: 100px;
}

.redColl {
    color: #d50000;
}

@media all and (min-width: 550px) and (max-width: 800px) {
    .info {
        font-size: 0.8em;
    }
}

@media all and (max-width: 550px) {
    .info {
        margin-top: 150px;
        font-size: 0.6em;
    }
}
</style>

<template>
    <div class="FilmsPage">
        <div class="sliderContainer">
            <div class="gallery">
                <img :src="images[currentImage]" @click="showModal" />
            </div>
            <div class="buttons">
                <button :disabled="currentImage === 0" @click="prevImage">Назад</button>
                <button :disabled="currentImage === images.length - 1" @click="nextImage">
                    Вперед
                </button>
            </div>
            <div class="modal" v-if="showModalState">
                <img :src="images[currentImage]" />
                <button @click="hideModal">Закрыть</button>
            </div>

        </div>

        <div class="filmInfo">
            <H1>Новинки проката:</H1>
            <h3>{{ filmNames[currentImage] }}</h3>
            <p>{{ synopses[currentImage] }}</p>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'FilmsScreen',
    data() {
        return {
            images: [
                require("@/assets/films/1.jpg"),
                require("@/assets/films/2.jpg"),
                require("@/assets/films/3.jpg"),
                require("@/assets/films/4.jpg"),
            ],
            filmNames: [
                'Кот в сапогах 2: последнее желание',
                'Операция фортуна: искусство побеждать',
                'Аватар 2: путь воды',
                'О чём говорят мужчины: простые удовольствия',
            ],
            synopses: [
                'Промотав восемь жизней из девяти и до смерти испугавшись пришедшего за ним волка-охотника за головами, Кот в сапогах внимает совету врача и заселяется в дом местной кошатницы. Там он смиряется с установленными порядками, отращивает бороду и теряет тягу к подвигам и приключениям, но только до тех пор, пока не узнаёт о волшебной карте, которая указывает путь к где-то упавшей Звезде желаний. Кот в сапогах твёрдо решает отыскать Звезду, чтобы вернуть свои жизни, и в компании притворявшегося кошачьим пёсика отправляется красть карту у известного коллекционера волшебных предметов Джека Хорнера.',
                'Элитный разведчик Орсон Форчун получил новое задание: остановить продажу и распространение смертельного оружия. Но в одиночку ему эту миссию не потянуть. Он вынужден объединиться с лучшими оперативниками мира, а также известным киноактером, который предоставит лихой группе убедительное прикрытие. На кону — судьба человечества, и в этот раз супершпионам придется играть по правилам Голливуда.',
                'После принятия образа аватара солдат Джейк Салли становится предводителем народа нави и берет на себя миссию по защите новых друзей от корыстных бизнесменов с Земли. Теперь ему есть за кого бороться — с Джейком его прекрасная возлюбленная Нейтири. Когда на Пандору возвращаются до зубов вооруженные земляне, Джейк готов дать им отпор.',
                'Дело было в далеком 2019-м году… Встретившись субботним утром, чтобы выпить шампанского, друзья отправляются в новое путешествие по глубинам мужского подсознания. О чем же на этот раз говорят мужчины? Конечно, о личном. Леша пытается понять существует ли «женская дружба», Камиль рассуждает, можно ли уволить лучшего друга, ловелас Слава вспоминает первую любовь (или это была не она?), а Саша размышляет о потере отца и умению жить и радоваться каждому новому дню. А еще, прогуливаясь по центру города, друзья обсуждают, как вкрутить лампочку, чтобы она осталась довольна, о чем кричат откровенные фото в социальных сетях, и что такое чевапчичи. Они вернулись поговорить о вечном, и о личном, и о всяких пустяках… короче, обо всем.'
            ],
            currentImage: 0,
            showModalState: false,
        };
    },
    methods: {
        nextImage() {
            if (this.currentImage < this.images.length - 1) {
                this.currentImage++;
            }
        },
        prevImage() {
            if (this.currentImage > 0) {
                this.currentImage--;
            }
        },
        showModal() {
            this.showModalState = true;
        },
        hideModal() {
            this.showModalState = false;
        },
    },
};

</script>
  
<style scoped>
.FilmsPage {
    color: white;
    width: 100%;
    display: flex;
    font-size: 2em;
    font-weight: 800;
    align-items: center;
    justify-content: space-around;
}

.filmInfo {
    margin: 40px;
    height: fit-content;
    padding: 10px;
    border-radius: 5%;
    font-size: 0.7em;
    text-align: justify;
    background-color: rgba(0, 0, 0, 0.5);
}

.sliderContainer {
    margin: 40px;
    margin-top: 100px;
}

.gallery {
    max-width: 500px;
    margin: 0 auto;
}

.gallery img {
    max-height: 500px;
    cursor: pointer;
}

.buttons {
    max-width: 500px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
}

button {
    padding: 10px;
    border: none;
    border-radius: 5px;
    background-color: #b94242;
    color: #fff;
    cursor: pointer;
}

button[disabled] {
    background-color: #d9d9d9;
    color: #666;
    cursor: default;
}

.modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 999;
}

.modal img {
    max-width: 90%;
    max-height: 90%;
}

.modal button {
    padding: 10px;
    border: none;
    border-radius: 5px;
    background-color: #b94242;
    color: #fff;
    cursor: pointer;
    margin-top: 10px;
}


.redColl {
    color: #d50000;
}

@media all and (min-width: 800px) and (max-width: 1200px) {
    .filmInfo {
        font-size: 0.5em;
    }
}

@media all and (min-width: 550px) and (max-width: 800px) {
    .FilmsPage {
        flex-direction: column;
    }

    .slider,
    .slider .item img {
        max-height: 500px;
        margin-bottom: 60px;
    }

    .filmInfo {
        margin-top: 0;
        font-size: 0.6em;
    }
}

@media all and (max-width: 550px) {
    .FilmsPage {
        flex-direction: column;
    }

    .slider,
    .slider .item img {
        max-height: 500px;
        margin-bottom: 60px;
    }

    .filmInfo {
        margin-top: 0;
        font-size: 0.5em;
    }
}
</style>
<template>
    <div class="tablePage">
        <table class="tableHorisontal">
            <caption> Расписание сеансов </caption>
            <tbody>
                <tr>
                    <th></th>
                    <th>Аватар 2</th>
                    <th>Винни-Пух: Кровь и мёд</th>
                    <th>Крушение</th>
                    <th>Кот в сапогах 2</th>
                    <th>Операция «Фортуна» </th>
                    <th>О чём говорят мужчины 4 </th>
                    <th>Чебурашка</th>
                </tr>
                <tr>
                    <td>Поннедельник</td>
                    <td>-</td>
                    <td>-</td>
                    <td>09:30/220 р</td>
                    <td>12:00/250 р</td>
                    <td>-</td>
                    <td>-</td>
                    <td>15:40/250 р<br>
                        18:00/300 p</td>
                </tr>
                <tr>
                    <td>Вторник</td>
                    <td>-</td>
                    <td>-</td>
                    <td>12:00/250 р</td>
                    <td>-</td>
                    <td>18:00/300 p</td>
                    <td>-</td>
                    <td>09:30/250 р</td>
                </tr>
                <tr>
                    <td>Среда</td>
                    <td>09:30/250 р</td>
                    <td>-</td>
                    <td>-</td>
                    <td>12:00/300 р</td>
                    <td>-</td>
                    <td>15:40/300 р</td>
                    <td>18:00/300 p</td>
                </tr>
                <tr>
                    <td>Четверг</td>
                    <td>-</td>
                    <td>20:30/300 p</td>
                    <td>12:00/250 р</td>
                    <td>-</td>
                    <td>-</td>
                    <td>-</td>
                    <td>-</td>
                </tr>
                <tr>
                    <td>Пятница</td>
                    <td>12:00/300 р</td>
                    <td>-</td>
                    <td>20:30/300 p</td>
                    <td>15:40/350 р</td>
                    <td>-</td>
                    <td>-</td>
                    <td>09:30/300 р</td>
                </tr>
                <tr>
                    <td>Суббота</td>
                    <td>-</td>
                    <td>-</td>
                    <td>20:30/350 p</td>
                    <td>09:30/350 р</td>
                    <td>-</td>
                    <td>15:40/400 р</td>
                    <td>12:00/350 р <br>
                        18:00/400 p</td>
                </tr>
                <tr>
                    <td>Воскресенье</td>
                    <td>15:40/400 р</td>
                    <td>-</td>
                    <td>20:30/350 p</td>
                    <td>12:00/350 р</td>
                    <td>18:00/400 p</td>
                    <td>-</td>
                    <td>09:30/350 р</td>
                </tr>
            </tbody>
        </table>

        <table class="tableVertical">
            <caption> Расписание сеансов </caption>
            <thead>
                <tr>
                    <th>День недели</th>
                    <th>Фильм</th>
                    <th>Время начала</th>
                    <th>Цена</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td rowspan="4">Поннедельник</td>
                    <td>Крушение</td>
                    <td>09:30</td>
                    <td>220 р</td>
                </tr>
                <tr>
                    <td>Кот в сапогах 2</td>
                    <td>12:00</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td rowspan="2">Чебурашка</td>
                    <td>15:40</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td>18:00</td>
                    <td>300 p</td>
                </tr>
                <tr>
                    <td rowspan="3">Вторник</td>
                    <td>Чебурашка</td>
                    <td>09:30</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td>Крушение</td>
                    <td>12:00</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td>Операция «Фортуна»</td>
                    <td>18:00</td>
                    <td>300 p</td>
                </tr>
                <tr>
                    <td rowspan="4">Среда</td>
                    <td>Аватар 2</td>
                    <td>09:30</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td>Кот в сапогах 2</td>
                    <td>12:00</td>
                    <td>300 р</td>
                </tr>
                <tr>
                    <td>О чём говорят мужчины 4</td>
                    <td>15:40</td>
                    <td>300 р</td>
                </tr>
                <tr>
                    <td>Чебурашка</td>
                    <td>18:00</td>
                    <td>300 p</td>
                </tr>
                <tr>
                    <td rowspan="2">Четверг</td>
                    <td>Крушение</td>
                    <td>12:00</td>
                    <td>250 р</td>
                </tr>
                <tr>
                    <td>Винни-Пух: Кровь и мёд</td>
                    <td>20:30</td>
                    <td>300 p</td>
                </tr>
                <tr>
                    <td rowspan="4">Пятница</td>
                    <td>Чебурашка</td>
                    <td>09:30</td>
                    <td>300 р</td>
                </tr>
                <tr>
                    <td>Аватар 2</td>
                    <td>12:00</td>
                    <td>300 р</td>
                </tr>
                <tr>
                    <td>Кот в сапогах 2</td>
                    <td>15:40</td>
                    <td>350 р</td>
                </tr>
                <tr>
                    <td>Крушение</td>
                    <td>20:30</td>
                    <td>300 p</td>
                </tr>
                <tr>
                    <td rowspan="5">Суббота</td>
                    <td>Кот в сапогах 2</td>
                    <td>09:30</td>
                    <td>350 р</td>
                </tr>
                <tr>
                    <td rowspan="2">Чебурашка</td>
                    <td>12:00</td>
                    <td>350 р</td>
                </tr>
                <tr>
                    <td>18:00</td>
                    <td>400 p</td>
                </tr>
                <tr>
                    <td>О чём говорят мужчины 4</td>
                    <td>15:40</td>
                    <td>400 р</td>
                </tr>
                <tr>
                    <td>Крушение</td>
                    <td>20:30</td>
                    <td>350 p</td>
                </tr>
                <tr>
                    <td rowspan="5">Воскресенье</td>
                    <td>Чебурашка</td>
                    <td>09:30</td>
                    <td>350 р</td>
                </tr>
                <tr>
                    <td>Кот в сапогах 2</td>
                    <td>12:00</td>
                    <td>350 р</td>
                </tr>
                <tr>
                    <td>Аватар 2</td>
                    <td>15:40</td>
                    <td>400 р</td>
                </tr>
                <tr>
                    <td>Операция «Фортуна»</td>
                    <td>18:00</td>
                    <td>400 p</td>
                </tr>
                <tr>
                    <td>Крушение</td>
                    <td>20:30</td>
                    <td>350 p</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
  
<script>
export default {
    name: 'TableScreen',
    data() {
        return {

        };
    }
};
</script>
  
<style scoped>
.tablePage {
    color: white;
    width: 100%;
    display: flex;
    font-size: 2em;
    font-weight: 800;
    font-size: 0.9em;
    align-items: center;
    justify-content: space-around;
    background-size: cover;
}

table {
    text-align: center;
    border-collapse: collapse;
    border-spacing: 5px;
    background-color: rgba(0, 0, 0, 0.8);
    border: 4px solid rgb(255, 255, 255);
    border-radius: 20px;
}

th {
    font-size: 1.1em;
    background-color: black;
    border-radius: 4px;
    padding: 5px;
}

th,
td {
    border-style: solid;
    border-color: white;
}

caption {
    font-size: 2.5em;
}

.tableHorisontal {
    margin: 10%;
}

.redColl {
    color: #d50000;
}

@media all and (min-width: 1200px) {

    .tableHorisontal {
        font-size: 1.2em;
        margin-top: 60px;
    }

    .tableVertical {
        display: none;
    }
}

@media all and (min-width: 800px) and (max-width: 1200px) {
    .tableVertical {
        display: none;
    }
}

@media all and (min-width: 550px) and (max-width: 800px) {
    .tableHorisontal {
        display: none;
    }

    .tableVertical {
        margin-top: 80px;
    }
}

@media all and (max-width: 550px) {
    .tableHorisontal {
        display: none;
    }

    .tableVertical {
        margin-top: 80px;
    }
}
</style>
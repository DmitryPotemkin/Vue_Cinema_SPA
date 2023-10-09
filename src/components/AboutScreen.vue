<template>
    <div class="AboutPage">
        <div class="about">
            <h1>О нас</h1>
            <p>Сеть кинотеатров <span class="redColl">Si-нема</span> уже <span class="redColl">20 лет</span> радует
                своих зрителей предоставляя им развлекательный контент</p>
            <p>Мы имеем уже более <span class="redColl">30 кинотеатров</span> по всей России, и не думаем
                останавливаться. </p>
        </div>
        <div class="form">
            <h1><span class="redColl">Подпишись</span>, чтоы всегда быть в курсе дела</h1>
            <form class="registration-form" @submit.prevent="submitForm">
                <label for="first-name">Имя:</label>
                <input id="first-name" v-model="firstName" type="text" />

                <label for="last-name">Фамилия:</label>
                <input id="last-name" v-model="lastName" type="text" />

                <label for="email">Email:</label>
                <input id="email" v-model="email" type="email" :class="{ 'input-error': emailError }" />
                <div v-if="emailError" class="error-message">{{ emailError }}</div>

                <label for="password">Пароль:</label>
                <input id="password" v-model="password" type="password" :class="{ 'input-error': passwordError }" />
                <label for="confirm-password">Подтвердите пароль:</label>
                <input id="confirm-password" v-model="confirmPassword" type="password"
                    :class="{ 'input-error': passwordError }" />
                <div v-if="passwordError" class="error-message">{{ passwordError }}</div>

                <button :class="{ active: isFormValid }" type="submit" :disabled="!isFormValid">
                    Зарегистрироваться
                </button>
            </form>

        </div>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            firstName: "",
            lastName: "",
            email: "",
            password: "",
            confirmPassword: "",
            emailError: "",
            passwordError: "",
        };
    },
    watch: {
        password(value) {
            if (value !== this.confirmPassword) {
                this.passwordError = "Пароли не совпадают";
            } else {
                this.passwordError = "";
            }
        },
        confirmPassword(value) {
            if (value !== this.password) {
                this.passwordError = "Пароли не совпадают";
            } else {
                this.passwordError = "";
            }
        },
        email(value) {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailRegex.test(value)) {
                this.emailError = "Некорректный email";
            } else {
                this.emailError = "";
            }
        },
    },
    computed: {
        isFormValid() {
            return (
                this.firstName !== "" &&
                this.lastName !== "" &&
                this.email !== "" &&
                this.password !== "" &&
                this.confirmPassword !== "" &&
                this.emailError === "" &&
                this.passwordError === ""
            );
        },
    },
    methods: {
        submitForm() {
            if (this.isFormValid) {
                console.log("Данные пользователя:", {
                    firstName: this.firstName,
                    lastName: this.lastName,
                    email: this.email,
                    password: this.password,
                });
                alert("Регистрация прошла успешно!");
                this.clearForm();
            } else {
                alert("Пожалуйста, заполните форму корректно");
            }
        },
        clearForm() {
            this.firstName = "";
            this.lastName = "";
            this.email = "";
            this.password = "";
            this.confirmPassword = "";
            this.emailError = "";
            this.passwordError = "";
        },
    },
};

</script>
  
<style scoped>
.AboutPage {
    width: 100%;
    height: 100%;
    display: flex;
    font-size: 2em;
    font-weight: 800;
    justify-content: space-around;
    align-items: center;
    padding-top: 50px;
}

.about {
    color: white;
    flex: 1;
    margin: 7px;
    padding: 10px;
    border-radius: 5%;
    background-color: rgba(0, 0, 0, 0.5);
    height: fit-content;
    width: fit-content;
}

.form {
    text-align: center;
    color: white;
    flex: 1;
    margin: 7px;
    padding: 10px;
    border-radius: 5%;
    background-color: rgba(0, 0, 0, 0.5);
    font-size: 0.5em;
    height: fit-content;
    width: fit-content;
    margin-top: 40px;
}

.registration-form {
    max-width: 500px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
}

.registration-form input {
    font-size: 16px;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

.registration-form label {
    font-size: 16px;
    margin-bottom: 5px;
}

.registration-form button {
    background-color: #d8d8d8;
    color: rgb(47, 47, 47);
    padding: 10px;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
    margin-top: 10px;
    opacity: 0.5;
    transition: opacity 0.3s ease-in-out;
}

.registration-form button.active {
    opacity: 1;
    background-color: #b94242;
    color: #fff;
}

.registration-form .error-message {
    font-size: 14px;
    color: red;
    margin-bottom: 10px;
}

.registration-form .input-error {
    border-color: red;
}


.redColl {
    color: #d50000;
}

@media all and (min-width: 800px) and (max-width: 1200px) {
    .about {
        font-size: 0.8em;
    }
}

@media all and (min-width: 550px) and (max-width: 800px) {

    .AboutPage {
        flex-direction: column;
    }

    .about {
        font-size: 0.5em;
        text-align: justify;
        margin: 70px 30px 20px 30px;
    }

    .about h1 {
        text-align: center;
    }

    .form {
        font-size: 0.5em;
        margin: 20px 30px 70px 30px;
    }
}

@media all and (max-width: 550px) {
    .AboutPage {
        flex-direction: column;
    }

    .about {
        margin-top: 70px;
        font-size: 0.5em;
        text-align: justify;
    }

    .form {
        margin-bottom: 70px;
    }

    .form h1 {
        font-size: 1.4em;
        text-align: center;
    }

    .about h1 {
        text-align: center;
    }
}
</style>
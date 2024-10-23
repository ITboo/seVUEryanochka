<script lang="ts" setup>
import { RouterLink } from 'vue-router';
import Container from '@/shared/Container.vue';
import Logo from '@/shared/Logo.vue';
import Button from '@/shared/Button.vue';
import Icon from '@/shared/Icon.vue';
import Field from '@/shared/Field.vue';
</script>

<template>
    <header class="header">
        <div class="header__content">
            <Container class="header__container">
                <div class="header__logo">
                    <RouterLink to="/">
                        <Logo orientation="horizontal" bgColor="white" colorful :withText="platform === 'desktop'" />
                    </RouterLink>
                </div>
                <div class="header__catalog">
                    <Button color="secondary">
                        <template v-slot:leftIcon>
                            <Icon type="menu" />
                        </template>
                        Каталог
                    </Button>
                </div>
                <div class="header__search">
                    <Field placeholder="Найти товар">
                        <template #rightIcon>
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M2.5 10.5C2.5 6.08172 6.08172 2.5 10.5 2.5C14.9183 2.5 18.5 6.08172 18.5 10.5C18.5 14.9183 14.9183 18.5 10.5 18.5C6.08172 18.5 2.5 14.9183 2.5 10.5ZM10.5 3.5C6.63401 3.5 3.5 6.63401 3.5 10.5C3.5 14.366 6.63401 17.5 10.5 17.5C14.366 17.5 17.5 14.366 17.5 10.5C17.5 6.63401 14.366 3.5 10.5 3.5Z"
                                    fill="#414141" />
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M15.4463 15.4464C15.6415 15.2512 15.9581 15.2512 16.1534 15.4464L21.3534 20.6464C21.5486 20.8417 21.5486 21.1583 21.3534 21.3535C21.1581 21.5488 20.8415 21.5488 20.6463 21.3535L15.4463 16.1535C15.251 15.9583 15.251 15.6417 15.4463 15.4464Z"
                                    fill="#414141" />
                            </svg>
                        </template>
                    </Field>
                </div>
            </Container>
        </div>
    </header>
</template>

<style scoped>
.header__container {
    display: flex;
    align-items: center;
    height: 72px;
}

.header {
    position: sticky;
    top: 0;
    left: 0;
    z-index: 1;
}

.header__content {
    position: relative;
    z-index: 1;
    box-shadow: var(--shadow-default-s);
    background: var(--main-surface);
}

.header__catalog {
    width: 140px;
    margin-left: 40px;
}

@media screen and (max-width: 1207px) {
    .header__container {
        grid-gap: 20px;
    }
}

@media screen and (max-width: 767px) {
    .header__logo {
        display: flex;
        align-items: center;
    }

    .header__logo:deep(svg) {
        width: 39px;
    }
}
</style>
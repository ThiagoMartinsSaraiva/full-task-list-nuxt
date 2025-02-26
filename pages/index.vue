<script lang="ts" setup>
const now = new Date()
const time = `${Intl.DateTimeFormat(Intl.DateTimeFormat().resolvedOptions().locale, {
  dateStyle: 'long',
}).format(now)}`

const greetingMessage = computed(() => {
  const morningInterval = [5, 12]
  const eveningInterval = [13, 18]
  if (now.getHours() >= morningInterval[0] && now.getHours() <= morningInterval[1]) {
    return 'Bom dia'
  } else if(now.getHours() >= eveningInterval[0] && now.getHours() <= eveningInterval[1]) {
    return 'Boa tarde'
  } else {
    return 'Boa noite'
  }
})
</script>

<template>
  <div class="background">
    <header>
      <div class="greeting">
        <h2>{{ greetingMessage }}</h2> <p>{{ time }}</p>
      </div>
    </header>
    <main>
      <div class="period-schedules">
        <NuxtLink to="/day">Agenda do dia</NuxtLink>
        <NuxtLink to="/week">Agenda da semana</NuxtLink>
        <NuxtLink to="/month" >Agenda do mês</NuxtLink>
      </div>
      <h2 class="programmation-title">Programação</h2>
      <NuxtPage />
    </main>
  </div>
</template>

<style>
.background {
  background: url('/assets/images/dark-mountain-wallpaper.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  height: 100vh;
  width: 100vw;
  padding: 10%;
}

header {
  color: #fff;
  text-shadow: 1px 1px 3px #333;
}

.greeting {
  margin-bottom: 16px;
}

.period-schedules {
  display: flex;
  gap: 16px;
  cursor: pointer;
  justify-content: center;
  
  a {
    color: #ccc;
    text-decoration: none;
    text-shadow: 1px 1px 3px #000;
    font-size: 22px;
    transition: .3s;

    &:hover, &.router-link-active {
      color: #fff;
    }
  }
}

.programmation-title {
  text-align: center;
  margin: 36px;
  /* text-shadow: 1px 1px 3px #aaa7; */
  color: #fff;
  text-shadow: 1px 1px 3px #000;
}

.card-list {
  display: flex;
  list-style-type: none;
  flex-wrap: wrap;
  flex-direction: column;
  gap: 16px;
  width: 90%;
  max-width: 928px;
  margin: 0 auto;
}

.card {
  background: #fffa;
  height: 58px;
  padding: 16px;
  display: flex;
  justify-content: space-between;
  border-radius: 4px;
  transition: background .4s;
  cursor: pointer;

  &:hover {
    background: #fff;
  }
}
</style>
<script lang="ts" setup>
const now = new Date()
const time = `${new Intl.DateTimeFormat('pt-BR', {
  dateStyle: 'long',
}).format(now)}`

const greetingMessage = computed(() => {
  const morningInterval = [5, 12]
  const eveningInterval = [13, 18]
  if (morningInterval[0] >= now.getHours() && morningInterval[1] <= now.getHours()) {
    return 'Bom dia'
  } else if(eveningInterval[0] >= now.getHours() && eveningInterval[1] <= now.getHours()) {
    return 'Boa tarde'
  } else {
    return 'Boa noite'
  }
})
</script>

<template>
  <div class="background">
    <header>
      <!-- <h2>Agenda do mês</h2>
      <h2>Agenda da semana</h2>
      <h2>Agenda do dia</h2> -->
      <h2>{{ greetingMessage }}</h2> <p>{{ time }}</p>
    </header>
    <main>
      <h2 class="programmation-title">Programação</h2>
      <ul class="card-list">
        <li>
          <div class="card">
            <span>Casamento</span> <span>18h30</span>
          </div>
        </li>
        <li>
          <div class="card">
            <span>Meditação</span> <span>19h45</span>
          </div>
        </li>
        <li>
          <div class="card">
            <span>Prova de certificação</span> <span>13h00</span>
          </div>
        </li>
        <li>
          <div class="card">
            <span>Hora de dormir</span> <span>01h30</span>
          </div>
        </li>
      </ul>
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
}

header {
  background-color: #d236;
  color: #fff;
  text-shadow: 1px 1px 3px #333, -1px -1px 3px #333;
}

.programmation-title {
  text-align: center;
  margin: 32px;
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

  &:hover {
    background: #fff;
    cursor: pointer;
  }
}
</style>
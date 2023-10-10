<template>
  <q-page class="container flex column flex-center justify-around">
    <h4 class="title q-ma-sm text-center">{{ phrases[index] }}</h4>
    <q-img
      src="http://www.workline.com.br/assets/img/frasesiconwl.png"
      spinner-color="white"
      style="height: 140px; max-width: 150px;"
    />
    <div class="flex justify-around full-width">
      <q-btn
        class="button"
        @click="randomPosition"
        rounded
        outline
        label="Cadastrar"
      />
      <q-btn
        class="button"
        @click="randomPosition"
        rounded
        label="Gerar Frases"
      />
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PhraseOfDay',
  data () {
    return {
      phrases: [
        'Enfrente os problemas e leve a melhor!',
        'Dê mais atenção ao que você tem de bom na sua vida',
        'Sua satisfação depende muito da sua determinação',
        'Para chegar ao topo, o que importa é começar!',
        'Acredite no poder da sua luz'
      ],
      index: 0,
    }
  },
  methods: {
    randomPosition(){
      let index = parseInt(Math.random() * 5 + 0);
      this.index = index;
    }
  },
  beforeMount(){
    this.randomPosition();
  }
}

</script>

<style lang="stylus" scoped>
  .container {
    background-color: #f95179;
  }

  .title {
    color: #fff;
  }

  .button {
    color: #fff;
    height: 50px;
    background-color: #262525;
  }
</style>

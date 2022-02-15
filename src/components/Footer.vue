<template>
  <footer>
    <!-- Bottom of the screen -->
    <Title>Besoin d'aide ?</Title>

    <ExpandBox title="FOIRE AUX QUESTIONS TEDIBER">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
      quo
      tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
    </ExpandBox>
    <ExpandBox title="LA GARANTIE TEDIBER">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
      quo
      tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
    </ExpandBox>
    <ExpandBox title="REPRISE DE L'ANCIENNE LITERIE">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
      quo
      tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
    </ExpandBox>
    <ExpandBox title="COMMENT FAIRE UN RETOUR ?">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum maxime fuga ad quibusdam incidunt facere illo
      quo
      tempore ratione iure sed dicta reiciendis mollitia temporibus ducimus, ullam aliquam quia atque.
    </ExpandBox>
  </footer>
</template>

<script>
  import Title from "./Title.vue";
  import ExpandBox from "./ExpandBox.vue";

  export default {
    name: "Footer",
    components: {
      Title,
      ExpandBox
    }
  }
</script>

<style scoped lang="scss">

</style>
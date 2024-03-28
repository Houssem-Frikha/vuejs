<template>
  <div>
    <h3>Liste des articles</h3>
    <table class="table table-striped">
      <thead>
        <tr>
          <th width="30px">Référence</th>
          <th width="40px">Désignation</th>
          <th width="25px">Qté</th>
          <th width="35px">Prix</th>
          <th width="35px">Montant</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="art in articles" :key="art.reference">
          <td width="40px">{{ art.reference }}</td>
          <td width="125px">{{ art.designation }}</td>
          <td width="40px">{{ art.qte }}</td>
          <td width="55px">{{ art.prix }}</td>
          <td width="55px">{{ art.prix * art.qte }}</td>
          <td>
            <button @click.prevent="modifarticle(art.reference)" class="btn btnwarning">
              Modifier
            </button>
          </td>
          <td>
            <button
              @click.prevent="supprimerarticle(art.reference)"
              class="btn btn-danger"
            >
              Supprimer
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script setup>
import { ref } from "vue";
const props = defineProps(["articles", "deletearticle", "updatearticle"]);
const supprimerarticle = (reference) => {
  props.deletearticle(reference);
};
const modifarticle = (refer) => {
  const art = ref({
    reference: refer,
    designation: "ASUS",
    prix: 2500,
    qte: 5,
  });
  props.updatearticle(art.value);
};
</script>
<style lang="scss" scoped></style>

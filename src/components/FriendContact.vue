<template>
  <li>
    <h2 v-if="isFavouraite">{{ name }}"Favouraite"</h2>
    <h2 v-else>{{ name }}</h2>
    <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
    <button @click="makeFavouraite">Make Favouraite</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phone }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ email }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    name:{
      type: String,
      required: true
    },
    email:{
      type: String,
      required: true
    },
    phone:{
      type: String,
      required: true
    }
  },
  setup() {
    var detailsAreVisible=false;
    var isFavouraite=false;

    function toggleDetails() {
      detailsAreVisible = !detailsAreVisible;
    }
    
    function makeFavouraite(){
      isFavouraite=!isFavouraite;
    }
    return {
      toggleDetails,
      makeFavouraite,
      detailsAreVisible,
      isFavouraite,
    };
  },
  methods: {
  }
};
</script>
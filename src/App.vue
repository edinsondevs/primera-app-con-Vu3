<script setup>
import { computed, ref } from "vue";

const name = "dinamico";
let activo = false;
// const users = [{
//     "firstname": "Bridgette",
//     "lastname": "Trantow",
//     "email": "Savanah.Mitchell38@hotmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/118.jpg",
//     "adress": "5207 Kellen Wall",
//     "country": "Ghana",
//     "phone": "(497) 322-2191 x822",
//     "birthday": "1952-06-26T01:18:57.894Z",
//     "id": "1"
//   },
//   {
//     "firstname": "Carter",
//     "lastname": "Kuphal",
//     "email": "Simone_Effertz@hotmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1108.jpg",
//     "adress": "513 Tyrique Rapid",
//     "country": "Oman",
//     "phone": "962-581-9535",
//     "birthday": "1963-09-03T05:33:24.079Z",
//     "id": "2"
//   },
//   {
//     "firstname": "Roger",
//     "lastname": "Tromp",
//     "email": "May.Reichel@yahoo.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/990.jpg",
//     "adress": "9920 Ned Prairie",
//     "country": "Isle of Man",
//     "phone": "(944) 547-3745 x153",
//     "birthday": "1959-09-18T15:17:15.771Z",
//     "id": "3"
//   },
//   {
//     "firstname": "Candice",
//     "lastname": "Hilll",
//     "email": "Nya_Stanton@hotmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/936.jpg",
//     "adress": "9155 Norberto Throughway",
//     "country": "Tunisia",
//     "phone": "570.626.0344",
//     "birthday": "1977-09-03T03:36:08.378Z",
//     "id": "4"
//   },
//   {
//     "firstname": "Anais",
//     "lastname": "Hartmann",
//     "email": "Serenity_Ward36@gmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/928.jpg",
//     "adress": "14065 Velma Way",
//     "country": "Haiti",
//     "phone": "(990) 566-9649 x6187",
//     "birthday": "1995-11-12T08:29:57.686Z",
//     "id": "5"
//   },
//   {
//     "firstname": "Annetta",
//     "lastname": "Hegmann",
//     "email": "Angelita_Skiles97@yahoo.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/220.jpg",
//     "adress": "929 Manuel Greens",
//     "country": "Angola",
//     "phone": "(356) 324-5355",
//     "birthday": "1969-11-22T09:06:39.083Z",
//     "id": "6"
//   },
//   {
//     "firstname": "Luigi",
//     "lastname": "Fisher",
//     "email": "Keon_Bernhard66@hotmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1000.jpg",
//     "adress": "9159 Lionel Brooks",
//     "country": "Mauritius",
//     "phone": "1-450-493-4392 x3554",
//     "birthday": "1986-05-21T21:23:25.191Z",
//     "id": "7"
//   },
//   {
//     "firstname": "Ivah",
//     "lastname": "Doyle",
//     "email": "Wilhelm_Boyer6@gmail.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/1244.jpg",
//     "adress": "0963 Gulgowski Court",
//     "country": "Spain",
//     "phone": "(691) 645-0254 x548",
//     "birthday": "1943-06-01T14:17:48.439Z",
//     "id": "8"
//   },
//   {
//     "firstname": "Georgette",
//     "lastname": "Murphy",
//     "email": "Manuel_Reinger@yahoo.com",
//     "picture": "https://cloudflare-ipfs.com/ipfs/Qmd3W5DuhgHirLHGVixi6V76LhCkZUz6pnFt5AJBiyvHye/avatar/500.jpg",
//     "adress": "382 Jeanie Meadows",
//     "country": "Kazakhstan",
//     "phone": "(568) 436-2206 x77711",
//     "birthday": "1959-12-29T10:24:02.016Z",
//     "id": "9"
//   }]

const users = [
  {
    gender: "female",
    name: {
      title: "Miss",
      first: "Julia",
      last: "Roberts",
    },
    location: {
      street: {
        number: 6333,
        name: "San Francisco",
      },
    },
  },
  {
    gender: "male",
    name: {
      title: "Mr",
      first: "Gaetano",
      last: "Thielemann",
    },
    location: {
      street: {
        number: 6367,
        name: "Birkenstraße",
      },
    },
  },
];

const objetoPerson = {
  gender: "male",
  name: "Gaetano",
  location: "Birkenstraße",
};

const arrayFrutas = [
  {
    name: "Manzana",
    price: 12,
    description: "Roja de estacion",
    stock: 10,
  },
  {
    name: "Pera",
    price: 20,
    description: "Verde",
    stock: 5,
  },
  {
    name: "Uvas",
    price: 30,
    description: "Moradas y Negras",
    stock: 30,
  },
];
const arrayColores = ["red", "green", "blue", "yellow"];

// METODOS - METHODS
const onClick = (props) => {
  console.log(props);
  // alert("El boton fue pulsado")
};

const counter = ref(0);

const aumentarCount = () => {
  counter.value = counter.value + 1;
  // console.log(counter)
};

const disminuirCount = () => {
  counter.value = counter.value - 1;
};

const resetCount = () => {
  counter.value = 0;
};

const resetFavorites = () => {
  arrayFavorites.value = [];
};

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  }
  if (counter.value > 0) {
    return "positive";
  }
  if (counter.value < 0) {
    return "negative";
  }
});

const bloqueBtnAdd = computed(() => {
  const search = arrayFavorites.value.find((num) => num === counter.value);
  //    UNA OPCION
  // if (search === 0 ) return true
  // return search ? true : false;
  //    SEGUNDA OPCION
  return search || search === 0;
});

const arrayFavorites = ref([]);
const addFavorites = () => {
  arrayFavorites.value.push(counter.value);
  bloqueBtnAdd;
};
</script>

<template >
  <div class="q-pa-xl q-gutter-lg" align="center">
  <!-- <h2 :style="styleColor">Soy azul</h2> -->
  <!-- <h2 :style="`color: ${arrayColores[1]}`">Soy {{arrayColores[1]}}</h2>
    <h2>{{ arrayColores[3] }}</h2>
    
    <p v-if="(activo === true)">Estoy Activo</p>
    <p v-else-if="(activo === false)">Estoy Inactivo</p>
    <p v-else="activo">No se donde estoy</p> -->

  <!------------------   INICIO DIRECTIVA V-FOR ARRAY  ---------------------------->
  <!-- <div>
      <ul>
        <li v-for="(user, index) in users" :key="index">
          {{ (user.firstname + " " + user.lastname + " email: " + user.email) }}
          {{ (user.gender + " " + user.name.title + " " + user.name.first + " " + user.name.last) }}
        </li>
      </ul>
    </div> -->

  <!------------------   FIN DIRECTIVA V-FOR   ---------------------------->

  <!------------------   INICIO DIRECTIVA V-FOR OBJETOS   ---------------------------->
  <!-- <ul>
      <li v-for="( value, index) in objetoPerson" :key="index">
        {{ value }}
      </li>
    </ul> -->
  <!------------------   FIN DIRECTIVA V-FOR OBJETOS   ---------------------------->
  <!------------------   INICIO DIRECTIVA V-FOR V-IF ---------------------------->

  <!-- <ul>
      <template v-for="(fruta, index) in arrayFrutas"  :key="index">
        <li v-if="fruta.price > 15">
          {{ fruta.name }} - {{ fruta.price }}          
        </li>
      </template>
    </ul> -->
  <!------------------   FIN DIRECTIVA V-FOR V-IF ---------------------------->

  <!------------------   INICIO DIRECTIVA V-ON ---------------------------->
  <!-- v-on:click="llamada" ó con el atajo @click="llamada" -->
  <!-- <button @click="onClick('Pulsado Izquierdo')">
      Click Me Izquierdo 
    </button> -->
  <!------------------   FIN DIRECTIVA V-FOR V-IF ---------------------------->
  <!-- v-on:click="llamada" ó con el atajo @click="llamada" -->
  <!-- <button @click.right.prevent="onClick('Pulsado Derecho')">
      Click Me Derecho
    </button> -->
  <!------------------   FIN DIRECTIVA V-FOR V-IF ---------------------------->

  <!------------------   INICIO DIRECTIVA CLICK ---------------------------->
  <!-- v-on:click="llamada" ó con el atajo @click="llamada" -->
  <!-- <button @click.middle="onClick('Pulsado Middle')">
      Click Me Middle
    </button> -->
  <!------------------   FIN DIRECTIVA CLICK ---------------------------->

  <!------------------   INICIO DIRECTIVA ---------------------------->
  <!-- v-on:click="llamada" ó con el atajo @click="llamada" -->



  <h3 class="titulo">Vue JS {{ name }}</h3>

  <!-- .col-8 -->
  <q-btn-group push>
    <q-btn color="green" text-color="white" glossy unelevated icon="add" label="Aumentar Contador"
      @click="aumentarCount">
    </q-btn>
    <q-btn color="red" text-color="white" glossy unelevated icon="remove" label="Disminuir Contador"
      @click="disminuirCount">
    </q-btn>

    <q-btn color="grey-7" text-color="white" glossy unelevated label="Reset Contador" @click="resetCount">
    </q-btn>

    <q-btn color="grey" text-color="white" glossy unelevated label="Reset Favoritos" @click="resetFavorites">
    </q-btn>
  </q-btn-group>

  <!-- .col -->
  <h5 :class="classCounter">Contador: {{ counter }}</h5>
  <q-btn color="blue" text-color="white" glossy unelevated icon="_favorites" label="Agregar a Favoritos"
    :disabled="bloqueBtnAdd" @click="addFavorites"></q-btn>

  <h5 class="titulo">Favoritos:</h5>
  <ul>
    <li v-for="(number, i) in arrayFavorites" :key="i" style="list-style-type: none">
      <!-- {{number}} -->
      <q-list bordered separator align="center">
        <q-item clickable v-ripple>
          <q-item-section>      {{ number }} </q-item-section>
        </q-item>
      </q-list>


    </li>
  </ul>





  </div>
</template>

<style>
h1 {
  color: red;
}

.titulo {
  font-weight: bold;
  font-style: italic;
}

.negative {
  color: red;
  font-weight: bold;
}

.positive {
  color: green;
  font-weight: bold;
}

.zero {
  color: yellowgreen;
  font-weight: bold;
}
</style>

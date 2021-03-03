<template>
  <main>
    <div v-for="array in lessons" :key="array.id">
      <div style="border: solid; height: 220px; width: 300px">
        <div style="float: left">
          <img
            style="height: 120px; width: 120px; object-fit: contain"
            v-bind:src="array.image"
          />
        </div>
        <div style="float: left">
          <h2 v-text="array.title"></h2>
          <p v-text="array.location"></p>
          <p style="display: inline">Price: £</p>
          <span v-text="array.price"> </span>
          <br /><br />
          <p style="display: inline">Number of spaces:</p>
          <span v-text="array.spaces"> </span>
          <br /><br />
          <div>
            <button @click="addProduct(array)">Add to Cart</button>
          </div>
        </div>
      </div>
      <h1></h1>
    </div>
  </main>
</template>

<script>
export default {
  name: "LessonList",
  data() {
    return {
      lessons: [
        {
          id: 0,
          title: "Maths",
          location: "London",
          price: 150,
          spaces: 5,
          image: "../images/math.png",
        },
        {
          id: 1,
          title: "English",
          location: "Oxford",
          price: 100,
          spaces: 5,
          image: "../images/eng.png",
        },
        {
          id: 2,
          title: "Physics",
          location: "Manchester",
          price: 200,
          spaces: 5,
          image: "../images/phy.png",
        },
        {
          id: 3,
          title: "Chemistry",
          location: "Bristol",
          price: 120,
          spaces: 5,
          image: "../images/chem.png",
        },
        {
          id: 4,
          title: "Biology",
          location: "Brighton",
          price: 200,
          spaces: 5,
          image: "../images/bio.png",
        },
        {
          id: 5,
          title: "Football",
          location: "Edinburgh",
          price: 180,
          spaces: 5,
          image: "../images/foot.png",
        },
        {
          id: 6,
          title: "Guitar",
          location: "London",
          price: 300,
          spaces: 5,
          image: "../images/guitar.png",
        },
        {
          id: 7,
          title: "Piano",
          location: "Portsmouth",
          price: 400,
          spaces: 5,
          image: "../images/piano.png",
        },
        {
          id: 8,
          title: "Cricket",
          location: "Liverpool",
          price: 180,
          spaces: 5,
          image: "../images/cric.png",
        },
        {
          id: 9,
          title: "IT",
          location: "Blackburn",
          price: 250,
          spaces: 5,
          image: "../images/it.png",
        },
      ],
    };
  },
  methods: {
    addProduct(product) {
      if (product.spaces > 0) {
        product.spaces -= 1;
        this.$emit("addProduct", product);
      }
    },
  },
};
</script>

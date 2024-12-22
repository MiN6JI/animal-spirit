<template>
  <q-page class="q-pa-md flex flex-center">
    <div class="row text-center">
      <div class="col-12">
        <h6 class="text-grey-8" style="margin: 0">Name:</h6>
        <h3 class="text-red-6" style="margin: 0">{{ userStore.name }}</h3>
      </div>
    </div>
    <div class="col-12">
      <div class="row text-center flex flex-center">
        <div class="col-12 q-py-md">
          <div
            v-if="random"
            :key="random.id"
            class="q-pa-lg bg-amber-1"
            style="border: 1px solid #fff; border-radius: 10px"
          >
            <div class="row">
              <div class="col-12 flex flex-center">
                <div class="q-pa-lg">
                  <q-img :src="random.img" width="150px" height="150px" />
                </div>
                <div class="q-py-md">
                  <h6 class="text-amber-10">{{ random.name }}</h6>
                  <div class="q-py-sm text-subtitl2">{{ random.spirit }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="col-12">
      <div class="row">
        <div class="col-12">
          <q-btn unelevated color="amber-10" no-caps to="/" label="Go Back" />
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref, onMounted } from "vue";
import confetti from "canvas-confetti";
import { useRoute } from "vue-router";
import { useUserStore } from "stores/user";

const route = useRoute();
const userStore = useUserStore();

onMounted(() => {
  const randomIndex = Math.floor(Math.random() * animals.value.length);
  random.value = animals.value[randomIndex];

  confetti({
    particleCount: 150,
    spread: 90,
    origin: { y: 0.6 },
    colors: ["#D83344", "#FF8C00", "#FFEB3B", "#4CAF50"],
  });
});

const animals = ref([
  {
    img: "public/stickers/tiger.png",
    id: 1,
    name: "Tiger",
    spirit:
      "The tiger embodies courage, strength, and independence, symbolizing unwavering determination and natural leadership. Its mystique and intuition reflect a deep connection to the self and surroundings, inspiring resilience and passion.",
  },
  {
    img: "public/stickers/bear.png",
    id: 2,
    name: "Bear",
    spirit:
      "The bear symbolizes strength, introspection, and protection. It represents a balance between assertiveness and nurturing, showcasing wisdom and a connection to nature.",
  },
  {
    img: "public/stickers/giraffe.png",
    id: 3,
    name: "Giraffe",
    spirit:
      "The giraffe represents grace, perception, and foresight. Its ability to see far ahead symbolizes visionary thinking and a gentle, kind spirit.",
  },
  {
    img: "public/stickers/lion.png",
    id: 4,
    name: "Lion",
    spirit:
      "The lion is a symbol of courage, leadership, and strength. It embodies a regal presence, self-confidence, and the ability to inspire others.",
  },
  {
    img: "public/stickers/elephant.png",
    id: 5,
    name: "Elephant",
    spirit:
      "The elephant signifies wisdom, loyalty, and power. It represents emotional intelligence, strong family bonds, and resilience.",
  },
  {
    img: "public/stickers/hippo.png",
    id: 6,
    name: "Hippo",
    spirit:
      "The hippo embodies balance, adaptability, and a calm demeanor. It symbolizes strength combined with the ability to thrive in diverse environments.",
  },
  {
    img: "public/stickers/rabbit.png",
    id: 7,
    name: "Rabbit",
    spirit:
      "The rabbit symbolizes creativity, sensitivity, and fertility. It represents quick thinking, adaptability, and a gentle spirit.",
  },
  {
    img: "public/stickers/crocodile.png",
    id: 8,
    name: "Crocodile",
    spirit:
      "The crocodile signifies primal strength, patience, and survival instincts. It embodies ancient wisdom and the ability to navigate emotional waters.",
  },
  {
    img: "public/stickers/zebra.png",
    id: 9,
    name: "Zebra",
    spirit:
      "The zebra represents individuality, balance, and agility. Its unique stripes symbolize the harmony of opposites and standing out in a crowd.",
  },
  {
    img: "public/stickers/wild-boar.png",
    id: 10,
    name: "Wild Boar",
    spirit:
      "The wild boar symbolizes courage, resourcefulness, and determination. It represents fearlessness in the face of challenges and a grounded nature.",
  },
  {
    img: "public/stickers/sheep.png",
    id: 11,
    name: "Sheep",
    spirit:
      "The sheep signifies gentleness, community, and trust. It represents nurturing qualities and the ability to find peace in harmony.",
  },
  {
    img: "public/stickers/rhino.png",
    id: 12,
    name: "Rhino",
    spirit:
      "The rhino embodies strength, endurance, and resilience. It represents a powerful connection to the earth and the ability to stay grounded.",
  },
  {
    img: "public/stickers/reindeer.png",
    id: 13,
    name: "Reindeer",
    spirit:
      "The reindeer symbolizes endurance, resourcefulness, and adaptability. It represents the spirit of journeying and thriving in challenging environments.",
  },
  {
    img: "public/stickers/pig.png",
    id: 14,
    name: "Pig",
    spirit:
      "The pig embodies abundance, intelligence, and curiosity. It symbolizes wealth, determination, and a strong work ethic.",
  },
  {
    img: "public/stickers/panda.png",
    id: 15,
    name: "Panda",
    spirit:
      "The panda represents peace, balance, and gentleness. It symbolizes a harmonious spirit and the ability to find joy in simplicity.",
  },
  {
    img: "public/stickers/lynx.png",
    id: 16,
    name: "Lynx",
    spirit:
      "The lynx embodies mystery, intuition, and keen observation. It symbolizes a secretive yet insightful spirit that sees beyond the surface.",
  },
  {
    img: "public/stickers/horse.png",
    id: 17,
    name: "Horse",
    spirit:
      "The horse signifies freedom, strength, and endurance. It represents a wild, untamed spirit and the drive to explore and achieve.",
  },
  {
    img: "public/stickers/hedgehog.png",
    id: 18,
    name: "Hedgehog",
    spirit:
      "The hedgehog symbolizes protection, curiosity, and resourcefulness. It represents a gentle yet determined nature and the ability to adapt.",
  },
  {
    img: "public/stickers/goat.png",
    id: 19,
    name: "Goat",
    spirit:
      "The goat signifies ambition, independence, and resilience. It represents the ability to climb life's mountains with perseverance and confidence.",
  },
  {
    img: "public/stickers/fox.png",
    id: 20,
    name: "Fox",
    spirit:
      "The fox embodies intelligence, adaptability, and cunning. It symbolizes a clever and resourceful nature that thrives in any situation.",
  },
  {
    img: "public/stickers/flamingo.png",
    id: 21,
    name: "Flamingo",
    spirit:
      "The flamingo represents grace, balance, and vibrant energy. It symbolizes standing out and embracing uniqueness with confidence.",
  },
  {
    img: "public/stickers/cow.png",
    id: 22,
    name: "Cow",
    spirit:
      "The cow signifies nurturing, abundance, and patience. It represents a grounded and generous spirit that provides for others.",
  },
  {
    img: "public/stickers/cheetah.png",
    id: 23,
    name: "Cheetah",
    spirit:
      "The cheetah embodies speed, focus, and precision. It symbolizes the ability to act swiftly and achieve goals with determination.",
  },
  {
    img: "public/stickers/buffalo.png",
    id: 24,
    name: "Buffalo",
    spirit:
      "The buffalo signifies strength, abundance, and perseverance. It represents a deep connection to the land and a spirit of gratitude.",
  },
  {
    img: "public/stickers/antelope.png",
    id: 25,
    name: "Antelope",
    spirit:
      "The antelope symbolizes agility, intuition, and quick thinking. It represents a lively and alert spirit that thrives in dynamic environments.",
  },
  {
    img: "public/stickers/alpaca.png",
    id: 26,
    name: "Alpaca",
    spirit:
      "The alpaca embodies gentleness, adaptability, and creativity. It symbolizes a nurturing and cooperative spirit with a touch of playfulness.",
  },
]);

const random = ref(null);
</script>

<style scoped></style>

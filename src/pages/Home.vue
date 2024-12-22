<template>
  <q-page class="flex flex-center q-py-md q-px-lg">
    <div class="row q-py-md div-res" >
      <div class="col-12 q-py-md">
        <h3 class="text-grey-10" style="letter-spacing: 1px; margin: 0px">
          Let’s get this party started!
        </h3>
        <p class="text-body1 q-py-md">
          Take this quiz with friends in real time and compare results.
        </p>
      </div>
      <div class="col-12">
        <q-card flat bordered>
          <q-card-section horizontal class="q-pa-md">
            <q-img class="col-5" src="others/animal.jpg" />
            <q-card-section class="flex items-center">
              <div class="text-body1 text-weight-medium">
                ❛ We Know Which Animal Matches Your Personality Based On Your
                Name ❜
              </div>
            </q-card-section>
          </q-card-section>
        </q-card>
      </div>
    </div>
    <div class="row q-py-md">
      <div class="col-12 q-py-md">
        <h5 class="text-grey-10" style="letter-spacing: 1px; margin: 0px">
          Let me know your Name
        </h5>
      </div>
      <div class="col-12 q-py-md">
        <q-form @submit.prevent="submit">
          <div class="row">
            <div class="col-12 q-py-md">
              <q-input
                class="full-width q-py-md"
                flat
                outlined
                v-model="name"
                placeholder="Enter Your Name"
                type="text"
                :rules="[(val) => !!val || 'Username cannot be empty']"
              >
                <template v-slot:prepend>
                  <q-avatar size="40px">
                    <img src="stickers/user.png" />
                  </q-avatar>
                </template>
              </q-input>
            </div>
            <div class="col-12">
              <q-btn
                unelevated
                no-caps
                icon-right="chevron_right"
                size="md"
                class="full-width text-white"
                color="amber-10"
                @click="submit"
                label="Your Animal Spirit"
              />
            </div>
          </div>
        </q-form>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";
import { useUserStore } from "stores/user";

const name = ref("");
const router = useRouter();
const userStore = useUserStore();

function submit() {
  if (name.value.trim()) {
    userStore.setName(name.value);

    router.push({ path: "/game" });
  } else {
    console.log("Please enter a name.");
  }
}
</script>

<style>
.div-res{
  width: 60%;
}

@media (max-width: 1000px) {
  .div-res{
    width: 100%;
  }
}
</style>

<template>
  <div class="general">
    <pv-toolbar
        style="
        background-color: #EDF0F5 !important;
        justify-content: start !important;
      "
        class="toobal"
    >

      <template #start>
        <div style="margin-inline: 1rem" class="logo flex align-items-center">
          <router-link to="/">
            <img src="src/assets/logo.png" alt="logo" class="logotipo"/>

          </router-link>
          <div class="card">
            <div class="p-fluid">
              <div class="p-float-label p-input-icon-right">
                <i class="pi pi-search" style="color: red" />
                <pv-input-text
                    type="text"
                    placeholder=""
                    required="true"
                    autocomplete="off"
                ></pv-input-text>
              </div>
            </div>
          </div>
        </div>
      </template>




      <template #end>
        <div class="flex-column mr-2" >
          <router-link
              v-for="item in items"
              :to="item.to"
              custom
              v-slot="{ navigate, href }"
              :key="item.label"
          >
            <pv-button
                class="p-button-text text-656E81"
                :href="href"
                @click="navigate"
            >{{ item.label }}</pv-button
            >
          </router-link>
        </div>
      </template>


    </pv-toolbar>
  </div>
</template>
<script>
export default {
  name:"tool-bar",
  data(){
    return{
      items: [
        {label: "Start Session", to:"/startSession"},
        { label: "Pet Profile", to: "/petProfile" },
        {label: "User Register",to:"/userRegister"},
        {label: "Pet Register", to:"/petRegister"},
        {label: "Vet Profile", to:"/vetProfile"},
        {label: "Veterinary Register", to:"/veterinaryRegister"},
        {label: "Log Out", to:"/startSession"},
      ],
    }
  }
}
</script>



<style>

.divLogo{
  border: blue 3px solid;
}

.logotipo{
  float: left;
  margin-bottom: 0px;
  height: 100px;
  width: 90%;
}

.toobal{
  height: 100px;
  align-items: center;
}

.general{
  align-items: center;


}





</style>
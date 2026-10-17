<script>
export default {
  data() {
    return {
      sysAdmin: {
        name: "Пикачу",
        role: ["Покемон", "Системный администратор"],
        ability: ["Спокойный и добрый. Использует электричество, удары хвоста и укусы острых зубов.",
                "Главный по всему, что связано с электричеством, включая интернет"],
        img: [`src/assets/staff-app/pikachu.png`, "src/assets/staff-app/admin.png"],
        isSelected: false,
        index: 0
      },
      officeManager: {
        name: "Бульбазавр",
        role: ["Покемон", "Офис-менеджер"],
        ability: ["Самый спокойный и миролюбивый покемон, может быть лидером и заботиться о других.", 
                 "Заведует всем офисом и не позволяет завянуть ни одному цветочку"],
        img: ["src/assets/staff-app/bullbasaur.png", "src/assets/staff-app/manager.png"],
        isSelected: false,
        index: 0

      },
      support: {
        name: "Псайдак",
        role: ["Покемон", "Специалист поддержки"],
        ability: ["Добрый и наивный, прожорливый, глуповатый. После сильной головной боли создаёт мощную психическую атаку.",
                  "Отвечает на миллион вопросов в день, что иногда вызывает головную боль"],
        img: ["src/assets/staff-app/psyduck.png", "src/assets/staff-app/support.png"],
        isSelected: false,
        index: 0
      }
    }
  },
  methods: {
    toggleAdmin() {
     this.sysAdmin.isSelected = !this.sysAdmin.isSelected
     if (this.sysAdmin.isSelected) {
      this.sysAdmin.index = 1;
     } else {
      this.sysAdmin.index = 0
     }
    },

    toggleManager() {
     this.officeManager.isSelected = !this.officeManager.isSelected
     if (this.officeManager.isSelected) {
      this.officeManager.index = 1;
     } else {
      this.officeManager.index = 0
     }
    },
    toggleSupport() {
    this.support.isSelected = !this.support.isSelected
     if (this.support.isSelected) {
      this.support.index = 1;
     } else {
      this.support.index = 0
     }
    }
  }
}
</script>
<template>
  <div class="container">
    <h2 class="mb-4">Команда мечты:</h2>
    <div class="pokemon-container row row-cols-1  row-cols-sm-2 row-cols-md-3 g-4 ">
      <div class="col" >
        <div class="card" @click="toggleAdmin">
          <img :src="sysAdmin.img[sysAdmin.index]" class="avatar card-img-top">
          <div class="card-body">
            <h5 class="card-title">{{ sysAdmin.name }}</h5>
            <h6 class="card-subtitle text-muted">{{ sysAdmin.role[sysAdmin.index] }}</h6>
            <p class="card-text mt-3">{{ sysAdmin.ability[sysAdmin.index] }}</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" @click="toggleManager">
          <img :src="officeManager.img[officeManager.index]" class="avatar card-img-top">
          <div class="card-body">
            <h5 class="card-title">{{ officeManager.name }}</h5>
            <h6 class="card-subtitle text-muted">{{ officeManager.role[officeManager.index] }}</h6>
            <p class="card-text mt-3">{{ officeManager.ability[officeManager.index] }}</p>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" :class="{'selected': support.isSelected}"   @click="toggleSupport">
          <img :src="support.img[support.index]" class="avatar card-img-top">
          <div class="card-body">
            <h5 class="card-title">{{ support.name }}</h5>
            <h6 class="card-subtitle text-muted">{{ support.role[support.index] }}</h6>
            <p class="card-text mt-3">{{ support.ability[support.index] }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.avatar {
  padding: 40px;
}

.card {
  position: relative;
}
.selected {
  border-bottom: 2px solid red;
}
</style>

<template>
  <div class="hello">
    <div class="container">
      <form @submit.prevent="addSkill">
        <input type="text" id="text" placeholder="Enter a Skill that you have!" v-model="skill" /> 
      </form>
      <ul>
        <transition-group
          name="list"
          enter-active-class="animated bounceInUp"
          leave-active-class="animated bounceOutDown"
        >
          <li v-for="(data,index) in skills" :key="index">
            {{ data.skill }}
            <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
          </li>
        </transition-group>
      </ul>

      <p>These are the skills that you have</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skill: "",
      skills: [{ skill: "vueJS" }, { skill: "Front end Developer" }]
    };
  },
  methods: {
    addSkill() {
      this.skills.push({ skill: this.skill }), (this.skill = "");
    },

    remove(id) {
      this.skills.splice(id, 1);
    }
  }
};
</script>

<style scoped>
.container {
  background: #f5f5f1;
}
input {
  width: calc(100% - 40px);
  border: 0;
  padding: 1.2rem;
  font-size: 1.5em;
  background-color: #221f1f;
  color: #f5f5f1;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
ul li {
  padding: 1.25em;
  font-size: 1.5em;
  background-color: #e0edf4;
  border-left: 5px solid #3eb3f6;
  margin-bottom: 2px;
  color: #3e5252;
  font-family: "Nunito", sans-serif;
  font-weight: 700;
}

p {
  text-align: center;
  padding: 2em 0;
  color: #221f1f;
}

.alert {
  background: #ea251a;
  color: #fff;
  font-weight: 900;
  display: inline-block;
  padding: 5px;
  margin-bottom: 1.25em;
}
i {
  float: right;
  cursor: pointer;
}
</style>
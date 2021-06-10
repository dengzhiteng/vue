<template>
  <div>
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>
    </div>
    <h3>{{ nowTime }}</h3>
    <router-view />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, reactive, toRefs, onMounted } from "vue";
import { nowTime, getNowTime } from "./hooks/useNowTime";
import { useUrlAxios } from "./api/user";

export default defineComponent({
  name: "App",
  components:{
  },
  setup() {
    interface DataProps {
      girls: string[];
      selectGirl: string;
      selectGirlFun: (index: number) => void;
    }
    const { result, loading, loaded, error } = useUrlAxios(
      "https://apiblog.jspang.com/default/getGirl"
    );
    onMounted(() => {
      getNowTime();
    });

    return {
      nowTime,
      getNowTime,
      result,
      loading,
      loaded,
      error
    };
  }
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

<template>
  <div>
    <!-- <Greet name="Mayank" heroName="Batman"/>
    <Greet name="Mittal" hero-name="Superman" />
    <Greet :name="name" :hero-name="channel" /> -->

    <!-- <Article id="my-article" title="Article title" :likes="50" :isPublished="true"/> -->
    <!-- <h3>App component username - {{myname}}</h3>
    <ComponentC />
    <button @click="showPopup = true">Open popup</button>
    <Popup v-show="showPopup" @close="closePopup"/> -->

    <!-- using v-model on custom component -->
    <div>
    <!-- <input type="text" v-model="inputName"> -->
    <Input v-model="inputName" />
    </div>
    <!-- Slots -->

    <!-- <h2>Slots</h2>
    <div>
      <Card></Card>
      <Card>Card Content</Card>
      <Card>
        <h2>Card Content</h2>
      </Card>
       <Card>
        <img src="https://picsum.photos/200" alt="picture">
       </Card>
    </div>
    <h2>Multiple Slots</h2>
    <Card>
      <template v-slot:header>
        <h3>Header Slot</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" alt="picture">
      </template>
      <template v-slot:footer>
       <button>View Details</button>
      </template>
    </Card> -->

    <!-- Slot props  -->

    <!-- <NameList>
      <template v-slot:default="slotProps">
        {{slotProps.firstName}} {{slotProps.lastName}}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
        {{slotProps.lastName}},{{slotProps.firstName}}
      </template>
    </NameList>
    <NameList>
      <template v-slot:default="slotProps">
        {{slotProps.lastName}}
      </template>
    </NameList> -->

    <!-- Component styles -->

    <!-- <h4>App Component text</h4>
    <ChildStyles>
      <h4>ChildStyles Component Text</h4>
    </ChildStyles> -->

    <!-- Dynamic components  -->
    <!-- <button @click="activeTab = 'TabA'">Tab A</button>
    <button @click="activeTab = 'TabB'">Tab B</button>
    <button @click="activeTab = 'TabC'">Tab C</button>

    <keep-alive>
      <component :is="activeTab"/>
    </keep-alive> -->
    <!-- <TabA v-if="activeTab === 'TabA'" />
    <TabB v-if="activeTab === 'TabB'" />
    <TabC v-if="activeTab === 'TabC'" /> -->

    <!-- Portal -->
    <!-- <teleport to="#portal-root">
      <Portal />
    </teleport> -->

    <!-- http requests  -->
    <!-- <PostList /> -->
    <!-- <CreatePost /> -->
    
    <!-- lifecycle methods -->
    <!-- <Parent /> -->

    <!-- template ref -->
    <!-- <TemplateRef /> -->

    <ClickCounter />
    <HoverCounter /> 

    <!-- compositions -->
    <!-- <Data /> -->

    <!-- reactivity and toRefs -->
    <!-- <Demo1 />
    <Demo2 /> -->

    <!-- methods Composition  -->
    <!-- <Methods /> -->

    <!-- vmodel compositions -->
    <!-- <VModel /> -->

    <!-- computed Properties -->
    <!-- <Computed /> -->

    <!-- Watchers -->
    <!-- <Watch /> -->

    <!-- provide inject -->
    <!-- <ProvideInject /> -->

    <!-- passing props using composition api -->
    <Person />
  </div>
</template>

<script>
// import Greet from './components/Greet.vue';
// import Article from './components/Article.vue';
// import ComponentC from './components/ComponentC.vue';
// import Popup from './components/Popup.vue';
import Input from './components/Input.vue';
// import Card from './components/Card.vue';
// import NameList from './components/NameList.vue';
// import ChildStyles from './components/ChildStyles.vue';
// import TabA from './components/TabA.vue';
// import TabB from './components/TabB.vue';
// import TabC from './components/TabC.vue';
// import Portal from './components/Portal.vue';
// import PostList from './components/PostList.vue';
// import CreatePost from './components/CreatePost.vue';
// import Parent from './components/Parent.vue';
// import TemplateRef from './components/TemplateRef.vue';
import ClickCounter from './components/ClickCounter.vue';
import HoverCounter from './components/HoverCounter.vue';
// import Data from './components/Data.vue';
// import Demo1 from './components/Demo1.vue';
// import Demo2 from './components/Demo2.vue';
// import Methods from './components/Methods.vue';
// import VModel from './components/VModel.vue';
// import Computed from './components/Computed.vue';
// import Watch from './components/Watch.vue';
// import ProvideInject from './components/ProvideInject.vue';
import Person from './components/Person.vue';

export default {
  name: "App",
  components: {
    // Greet, Article,
    // ComponentC,
    // Popup,
    Input,
    // Card,
    // NameList,
    // ChildStyles,
    // TabA, TabB, TabC,
    // Portal,
    // PostList,
    // CreatePost,
    // Parent,
    // TemplateRef,
    ClickCounter,
    HoverCounter,
    // Data,
    // Demo1,
    // Demo2,
    // Methods,
    // VModel,
    // Computed,
    // Watch,
    // ProvideInject,
    Person
  },
  data() {
    return {
      name: 'MM',
      channel: 'Vue',
      myname: "Mayank",
      showPopup: false,
      inputName: '',
      activeTab: 'TabA'
    }
  },
  methods: {
    closePopup(name) {
      this.showPopup = false
      console.log(name)
    }
  },
  provide() {
    return { 
      username: this.myname 
    }
  }
  
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* border: 1px solid black; */
}

h4 {
  color: orange;
}

</style>
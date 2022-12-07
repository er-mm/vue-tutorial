
<template>
  <!-- templates for bind, text directives -->
  <!-- <div>
    <div>{{ greet }} {{ name }}</div>
    <div>{{ channel1 }}</div>
    <div v-text="channel1"></div>
    <div v-html="channel2"></div>
    <div v-text="name">Hello</div> 
    <div v-html="hack"></div>
    <h2 :id="headingId">Heading</h2>
    <button :disabled="isDisabled">Bind</button>
    <h2 class="underline">Underlined Text</h2>
    <h2 class="underline" :class="status">Status</h2>
    <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 :class="isSold ? 'sold-out' : 'new'">Soldout Movie</h2>
    <h2 :class="['new', 'promoted']">Newely promoted</h2>
    <h2 :class="[isPromoted && 'promoted', isSold ? 'sold-out' : 'new']">Array conditional Movie</h2>
    <h2 :class="{
      promoted: isPromoted,
      new: !isSold,
      'sold-out': isSold
    }">Object conditional movie</h2>

    <h2 :style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px'
    }">Inline style</h2>

    <h2 :style="headerStyle">Inline style using clean styles</h2>

    <div :style="[baseStyle, successStyle]">Success style</div>
    <div :style="[baseStyle, dangerStyle]">Danger style</div>
  </div> -->

  <!-- templates for conditional rendering directives -->
  <!-- <div>
    <h2 v-if="num === 0">The number is zero</h2>
    <h2 v-else-if="num < 0">Number is negative</h2>
    <h2 v-else-if="num > 0">Number is positive</h2>
    <h2 v-else>Not a number</h2>

    <template v-if="display">
      <h2>Mayank</h2>
      <h2>Channel</h2>
      <h2>Vue</h2>
    </template>

    <h2 v-show="showElement">Using v-show</h2>
    <h2 v-if="showElement">Using v-if</h2>
  </div> -->

  <!-- templates for rendering list of eleemnts -->
  <div>
    <h2 v-for="(name, index) in names" :key="name">{{index}} {{name}}</h2>
    <h2 v-for="(name, index) in fullNames" :key="name.first">{{index}} {{name.first}} {{name.last}}</h2>
    
    <div v-for="actor in actors" :key="actor.name">
      <h2>{{actor.name}}</h2>
      <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3>
    </div>

    <h2 v-for="(value, key, idx) in myInfo" :key="value">{{idx}} {{key}} {{value}} </h2>

    <template v-for="name in names" :key="name">
      <h2>{{name}}</h2>
      <hr />
    </template>

    <template v-for="name in names" :key="name">
      <h2 v-if="name ==='MM'">{{name }}</h2>
    </template>
  </div>
</template>

<script>
export default {
  name: "BasicOfView",
  data() {
    return {
      name: "Batman",
      greet: "Hello!",
      channel1: "learn Vue", // v-text directive - only work when you render full text
      channel2: "<b>Learn Vue</b>", // v-html directive - only work with html
      hack: `<a href="#" onclick="alert('You have been hacked')">Win a prize!</a>`,
      headingId: "heading",
      isDisabled: false,
      status: "succes",
      isPromoted: true,
      isSold: true,
      highlightColor: "orange",
      headerSize: 50, // single inline style property
      headerStyle: {
        // multiple inline style properties
        color: "orange",
        fontSize: "50px",
        padding: "20px",
      },

      baseStyle: {
        fontSize: "50px",
        padding: "10px",
      },

      successStyle: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
        padding: "20px",
      },

      dangerStyle: {
        color: "darkred",
        backgroundColor: "red",
        border: "1px solid darkred",
      },

      num: 5,
      display: true,
      showElement: true,

      names: ['MM', 'PM', 'SM'],
      fullNames: [
        { first: 'MM', last: "Mittal"},
        { first: 'PM', last: "Sharma"},
        { first: 'SM', last: "Bansal"}
      ],
      actors: [
        {
          name: "Ajay",
          movies: ['Golmal', 'Golmal2']
        },
        {
          name: "Salman",
          movies: ['Tiger', 'Wanted']
        }
      ], 

      myInfo: {
        name: 'Mayank', 
        age: 27,
        course: "Vue3"
      }
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}
.sold-out {
  color: red;
}
</style>

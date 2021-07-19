<template>
  <!-- Vue.js uses an HTML-based template syntax that allows you to declaratively bind the rendered DOM to the underlying Vue instance’s data. All Vue.js templates are valid HTML that can be parsed by spec-compliant browsers and HTML parsers.

  Under the hood, Vue compiles the templates into Virtual DOM render functions. Combined with the reactivity system, Vue is able to intelligently figure out the minimal number of components to re-render and apply the minimal amount of DOM manipulations when the app state changes. -->
  <div>
    <!-- binding data -->
    <!-- The most basic form of data binding is text interpolation using the “Mustache” syntax (double curly braces) -->
    <h1>Hi {{ name }}</h1>

    <!-- Mustaches cannot be used inside HTML attributes. Instead, use a v-bind directive -->
    <!-- Directives are special attributes with the v- prefix. -->

    <!-- binding Text. This will replace the child element -->
    <h2 v-text="greet"></h2>

    <!-- binding HTML. This will replace the child element -->
    <div v-html="game"></div>

    <!-- binding boolean attribute -->
    <button v-bind:disabled="isDisabled">Disabled button</button>

    <!-- binding attributes -->
    <h2 v-bind:id="headingId">Heading</h2>
    <img v-bind:src="imgSrc" />

    <!-- Applying conditional classes -->
    <p v-bind:class="isDisabled ? 'danger' : 'success'">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquid saepe provident sit minus, laboriosam illo et explicabo obcaecati incidunt maiores nam a est enim iste fuga temporibus quidem doloremque quos!</p>

    <!-- Adding multiple classes using Array Syntax -->
    <h2 v-bind:class="['first', 'second']">Array of classes</h2>


    <!-- Binding styles using Array Syntax -->
    <!-- This is not recommended in the case where we have to apply more styles -->
    <!-- Vue supports camelCase as well as kabab-case -->
    <h2 v-bind:style="{
      color: headingColor,
      'font-family': headingFont,
      fontSize: headingSize + 'px',
      border: '1px solid black'
    }">Classes using Objects</h2>

    <!-- This is used when we have no of styles to be applied are more -->
    <h2 v-bind:style="headerStyleObject">Clasees using Objects with more styles</h2>

    <!-- event handling -->
    <button v-on:click="counter1 += 1" id="btn1">The button has been clicked {{ counter1 }} times.</button>

    <!-- v-bind Shorthand -->
    <h2 :id="bindId" :class="bindClass" :style="bindStyle">V-bind Shorthand</h2>

    <!-- v-on Shorthand -->
    <button @click="counter2 += 1" id="btn2">Counter: {{ counter2 }}</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      name: 'Rohit',
      greet: 'Good Morning',
      game: '<h4 style="color:coral">Cricket</h4>',
      headingId: 'heading',
      imgSrc: 'https://picsum.photos/seed/picsum/300/300',
      paraClass: 'danger',
      isDisabled: true,
      headingColor: 'brown',
      headingFont: "Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif",
      headingSize: 30,
      headerStyleObject: {
        color: 'yellow',
        backgroundColor: 'green',
        fontSize: '28px',
        padding: '4px'
      },
      counter1: 0,
      counter2: 100,
      bindId: 'id1',
      bindClass: 'class1',
      bindStyle: {
        fontSize: '20px',
        border: '1px solid blue'
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#heading {
  color: blue;
}
.danger {
  color: red;
  font-size: 24px;
}
.success {
  color: green;
}
.first {
  font-style: italic;
  text-decoration: underline;
}
.second {
  color: orange;
}
#id1 {
  color:purple
}
.class1 {
  background-color: pink;
}
</style>

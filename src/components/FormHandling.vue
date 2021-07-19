<template>
  <div>
    <!-- You can use the v-model directive to create two-way data bindings on form input, textarea, and select elements. It automatically picks the correct way to update the element based on the input type. -->
    <h1>Form Handling</h1>
    <form @submit="submitForm">

      <!-- Text -->
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" autocomplete="off" v-model="name">
        <span>{{name}}</span>
      </div>
      
      <!-- Select -->
      <div>
        <label for="role">Role</label>
        <select id="role" v-model="role">
          <option value="">Select a role</option>
          <option value="frontend">Front End</option>
          <option value="backend">Back End</option>
          <option value="fullstack">Full Stack</option>
        </select>
        <span>{{role}}</span>
      </div>

      <!-- Select Multiple -->
      <div>
        <label for="city">City</label>
        <select id="city" v-model="city" multiple>
          <option value="pune">Pune</option>
          <option value="mumbai">Mumbai</option>
          <option value="banglore">Banglore</option>
        </select>
        <span>{{city}}</span>
    </div>

    <!-- Checkbox -->
    <div>
      <input type="checkbox" name="relocate" id="relocate" v-model="relocate" />
      <label for="relocate">Are you willing to relocate?</label>
      <span>{{relocate}}</span>
    </div>

    <!-- Checkbox group -->
    <div>
      <label>Frameworks</label>
      <input type="checkbox" id="react" value="react" v-model="frameworks" />
      <label for="react">React</label>
      <input type="checkbox" id="angular" value="angular" v-model="frameworks" />
      <label for="angular">Angular</label>
      <input type="checkbox" id="vue" value="vue" v-model="frameworks" />
      <label for="vue">Vue</label>
      <span>{{frameworks}}</span>
    </div>

    <!-- Radio group -->
    <div>
      <label>Years of Experience</label>
      <input type="radio" id="0-2" value="0-2" v-model="yoe" />
      <label for="0-2">0-2</label>
      <input type="radio" id="3-5" value="3-5" v-model="yoe" />
      <label for="3-5">3-5</label>
      <input type="radio" id="5+" value="5+" v-model="yoe" />
      <label for="5+">5+</label>
      <span>{{yoe}}</span>
    </div>

    <div>
      <button type="submit">Submit</button>
    </div>

    </form>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        name: '',
        role: '',
        city: [],
        relocate: false,
        frameworks: [],
        yoe: '',
      }
    },
    methods: {
      submitForm(event){
        event.preventDefault();
      },
    }
  }
</script>

<style scoped>
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
span {
  display: block;
  text-align: left;
}
</style>
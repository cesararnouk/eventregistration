<template>
    <div id="eventregistration">
    <h2>Persons</h2>
      <table id="persons_table">
        <tr>
            <th>Name</th>
            <th>Events</th>
        </tr>
        <tr v-for="person in persons" v-bind:key="'person-${i}'">
            <td>{{ person.name }}</td>
            <td>
              <ul>
                <li v-for="event in person.events" 
                    v-bind:key="'event-${i}'" 
                    style="list-style-type-disc;">
                  <span class="registration-event-name">{{event.name}}</span>
                </li>
              </ul>
            </td>
        </tr>
        <tr>
            <td>
                <input 
                    id="create_person_person_name"
                    type="text" 
                    v-model="newPerson" 
                    placeholder="Person Name"
                    />
            </td>
            <td>
                <button id="create_person_button" @click="createPerson(newPerson)">Create Person</button>
            </td>
            <td></td>
            <td></td>
        </tr>
    </table>
    <span v-if="errorPerson" style="color:red">Error: {{errorPerson}} </span>s
  </div>
</template>



<script src="./registration.js">
</script>



<style>
    #eventregistration {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    color: #2c3e50;
    background: #f2ece8;
  }
</style>
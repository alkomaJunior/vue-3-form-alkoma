<template>
  <div>
    <h1>Create an event</h1>
    <form>
      <base-select
        :options="categories"
        v-model="event.category"
        label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <base-input v-model="event.title" label="Title" type="text" />

      <base-input v-model="event.description" label="Description" type="text" />

      <h3>Where is your event?</h3>

      <base-input v-model="event.location" label="Location" type="text" />

      <h3>Are pets allowed?</h3>
      <div>
        <input type="radio" v-model="event.pets" :value="1" name="pets" />
        <label>Yes</label>
      </div>

      <div>
        <input type="radio" v-model="event.pets" :value="0" name="pets" />
        <label>No</label>
      </div>

      <h3>Extras</h3>
      <div>
        <base-checkbox v-model="event.extras.catering" label="Catering" />
      </div>

      <div>
        <base-checkbox v-model="event.extras.music" label="Live music" />
      </div>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>

    <pre>{{ event }}</pre>
  </div>
</template>

<script>
import BaseSelect from '@/components/BaseSelect'
import BaseCheckbox from '../components/BaseCheckbox.vue'
import BaseInput from '../components/BaseInput.vue'

export default {
  components: {
    BaseInput,
    BaseSelect,
    BaseCheckbox,
  },

  data() {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community',
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false,
        },
      },
    }
  },
}
</script>

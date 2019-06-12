<template>
  <v-container>
        <v-layout flex align-center>


        <form>
          <v-flex>
                <v-text-field
                              v-model="name"
                              v-validate="'required|max:10'"
                              :counter="10"
                              
                              label="Name"
                              data-vv-name="name"
                              required
                ></v-text-field>
          </v-flex>
          <v-flex>
                <v-text-field
                              v-model="email"
                              v-validate="'required|email'"
                              
                              label="E-mail"
                              data-vv-name="email"
                              required
                ></v-text-field>
          </v-flex>
          <v-flex>
                <v-select
                              v-model="select"
                              v-validate="'required'"
                              :items="items"
                              
                              label="Select"
                              data-vv-name="select"
                              required
                ></v-select>
          </v-flex>
          <v-flex>
                <v-checkbox
                              v-model="checkbox"
                              v-validate="'required'"
                              
                              value="1"
                              label="Option"
                              data-vv-name="checkbox"
                              type="checkbox"
                              required
                ></v-checkbox>
            </v-flex>

                <v-btn @click="submit">submit</v-btn>
                <v-btn @click="clear">clear</v-btn>
        </form>

        </v-layout>

    </v-container>

</template>


<script>

export default {

    $_veeValidate: {
      validator: 'new'
    },

    data: () => ({
      name: '',
      email: '',
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4'
      ],
      checkbox: null,
      dictionary: {
        attributes: {
          email: 'E-mail Address'
          // custom attributes
        },
        custom: {
          name: {
            required: () => 'Name can not be empty',
            max: 'The name field may not be greater than 10 characters'
            // custom messages
          },
          select: {
            required: 'Select field is required'
          }
        }
      }
    }),

    mounted () {
      this.$validator.localize('en', this.dictionary)
    },

    methods: {
      submit () {
        this.$validator.validateAll()
      },
      clear () {
        this.name = ''
        this.email = ''
        this.select = null
        this.checkbox = null
        this.$validator.reset()
      }
    }
  }

</script>

<style>

</style>


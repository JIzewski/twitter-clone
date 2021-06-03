<template>
    <div>
        yo {{ user }}
        <!-- <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                    </div>
                </div>
            </div>
        </div>
    </div> -->

    </div>

</template>

<script>

    import axios from 'axios'

    export default {

          data () {
            return {
                user: null
            }

          },

          methods: {
              async getUser () {

                  let response = await axios.get('/api/user')
                  this.user = response.data

              }

          },


        mounted() {
           // console.log('Component mounted.')
           this.getUser()
        }
    }
</script>

<template>
    <modal :show.sync="show" :on-close="close">
        <template slot="header">Delete member</template>

        <article slot="body">
          <p>This action will <strong>DELETE</strong> the selected member. Are you sure ?</p>
          <button class="btn_primary cancel-ok" @click="close">Cancel</button> 
          <button class="btn_primary cancel-ok" @click="deleteEntity">OK</button>
        </article>

    </modal>
</template>


<script>
  import { bus } from '../../main'
  import Modal from '../Modal.vue'

  export default {
    props: ['show'],
    components: { 
      Modal
    },
    data () {
      return {
        
      }
    },
    methods: {
      close: function () {
        bus.$emit('CLOSE_DELETE_MODAL')
      },
      deleteEntity: function () {
        bus.$emit('DELETE_ENTITY')
        this.close()
      }
    }
}
</script>


<style >

</style>

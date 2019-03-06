<template lang="pug">
  #container
    span This is callback component!
    span All the things about the user LOL:<br>
    <DataField v-for="dataItem in data" :keyField="dataItem[0]" :valueField="dataItem[1]"/>
</template>

<script>
import DataField from '../components/DataField'

import axios from 'axios'
import _ from 'lodash'

export default {
  components: {
    DataField
  },
  data() {
    return {
      data: null
    }
  },
  mounted() {
    var token = /access_token=([^&]+)/.exec(document.location.hash)[1]
    console.log('token: ', token)
    axios.get('https://login.yandex.ru/info?oauth_token=' + token).then(response => {
      console.log('data regarding the user: ', _.toPairs(response.data))
      this.data = _.filter(_.toPairs(response.data), dataItem => dataItem[0] !== 'emails')
    }).catch(error => {
      console.log('error: ', error)
    })
  }
}
</script>


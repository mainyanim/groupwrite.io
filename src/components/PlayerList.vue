<template>
  <div class="playerList">
    <h2>Players</h2>
    <ol class="nonelist">
      <li v-for="player in sharedState.players">
        <div v-if="player.nickname != sharedState.myNickname" class="playerbox">
          <div class="nickname">
            {{player.nickname}}
          </div>
          <div class="suggestion">
            {{player.suggestion}}
          </div>
          <div class="vote-button">
          </div>
        </div>
      </li>
    </ol>
  </div>
</template>
<script>
  import store from './store'

  export default {
    name: 'PlayerList',
    props: ['players'],
    data() {
      return {
        sharedState: store.state
      }
    }
  }

</script>
<style>
  ol.nonelist {
    list-style-type: none;
  }
  
  .playerbox {
    display: inline-block;
    width: 500px;
    border: 1px dashed;
  }
  
  .nickname {
    font-weight: strong;
    color: blue;
  }
  
  .displayblock {
    display: block;
  }
  
  .vote-button {
    background-image: url('../assets/heart-icon.png');
    width: 32px;
    height: 32px;
    cursor: pointer;
  }
  
  .vote-button:hover {
    background-image: url('../assets/heart-icon-hover.png');
  }
</style>
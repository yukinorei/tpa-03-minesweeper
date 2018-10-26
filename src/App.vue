<template>
  <div id="app">
    <button v-on:click="startGame">Start Game</button>
    <table class="minesweeper">
      <tr
      v-for="(row, rowIndex) in tiles"
      v-bind:key="rowIndex"
      >
        <Tile
          v-for="(tile, columnIndex) in row"
          v-bind:key="columnIndex"
          v-bind:data="tile"
        >
        </Tile>
      </tr>
    </table>
  </div>
</template>

<script>
import Tile from './components/Tile';
export default {
  name: 'App',
  components: {
    Tile,
  },
  data: () => {
    return {
      rows: 10,
      columns: 19,
      tiles: [],
    };
  },
  methods: {
    startGame: function() {

    };
  }
};
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
  background: #333;
  color: #fff;
}

button {
  margin: 20px auto;
  display: block;
}

table.minesweeper {
  margin: auto;
  border: 1px solid #999;
  border-collapse: collapse;
  background-color: #ddd;
}

table.minesweeper td {
  width: 24px;
  height: 24px;
  background-size: cover;
}

</style>

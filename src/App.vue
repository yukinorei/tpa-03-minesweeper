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
          v-on:leftClick="openTile"
          v-on:rightClick="flagTile"
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
      tiles: [], // startGameメソッドでタイルをtilesに追加する
    };
  },
  methods: {
    /**
     * resets the tile data
     * @function
     * @return {undefined}
     */
    startGame: function() {
      this.tiles = [];
      for (let rowIndex = 0; rowIndex < this.rows; rowIndex++) {
        let row = [];
        for (let columnIndex = 0; columnIndex < this.columns; columnIndex++) {
          let tile = {
            row: rowIndex,
            column: columnIndex,
            mined: Math.random() * 6 > 5,
            class: 'unopened',
          };
          row.push(tile);
        }
        this.tiles.push(row);
      }
    },

    /**
     * opens a tile
     * @function
     * @param {Object} tile
     * @return {undefined}
     */
    openTile: function() {

    },

    /**
     * flags a tile
     * @function
     * @param {Object} tile
     * @return {undefined}
     */
    flagTile: function(tile) {
      tile.class = 'flagged';
    },

    /**
     * opens all tiles
     * @function
     * @return {undefined}
     */
    showAllTiles: function() {

    },

    /**
     * returns an array of neighbors surrounding input tile
     * @function
     * @param {Object} tile
     * @return {Array.<Object>} - an array of tile objects
     */
    getNeighbors: function() {

    },
    /**
     * returns the number of mines within an array of tiles
     * @function
     * @param {Array.<Object>} neighbors - an array of tile objects
     * @return {number} - number of mines in neighbors array
     */
    countNeighboringMines: function() {

    },

    /**
     * checks if tile is not open
     * @function
     * @param {Object} tile
     * @return {boolean}
     */
    isUnopened: function() {

    },

    /**
     * checks to see if row and col are valid indices within the game board
     * @function
     * @param {number} rowIndex
     * @param {number} columnIndex
     * @return {boolean}
     */
    isValid: function() {

    },
  },
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

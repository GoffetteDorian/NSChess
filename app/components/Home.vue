<template>
  <Page>
    <ActionBar>
      <Label text="Chess" />
    </ActionBar>

    <ListView for="x in cells" @itemTap="onTap">
      <v-template>
        <GridLayout columns="*, *, *, *, *, *, *, *">
          <Label col="0" @tap="onTap(x)">{{ "a" + x }}</Label>
          <Label col="1" @tap="onTap(x)">{{ "b" + x }}</Label>
          <Label col="2" @tap="onTap(x)">{{ "c" + x }}</Label>
          <Label col="3" @tap="onTap(x)">{{ "d" + x }}</Label>
          <Label col="4" @tap="onTap(x)">{{ "e" + x }}</Label>
          <Label col="5" @tap="onTap(x)">{{ "f" + x }}</Label>
          <Label col="6" @tap="onTap(x)">{{ "g" + x }}</Label>
          <Label col="7" @tap="onTap(x)">{{ "h" + x }}</Label>
        </GridLayout>
      </v-template>
    </ListView>
  </Page>
</template>

<script>
import Piece from "./Piece";
export default {
  computed: {
    message() {
      return "Blank {}-Vue app";
    }
  },
  methods: {
    onTap(value) {
      console.log(value);
    }
  },
  data() {
    return {
      cells: [8, 7, 6, 5, 4, 3, 2, 1]
    };
  }
};
</script>

<style scoped lang="scss">
@import "~@nativescript/theme/scss/variables/blue";

// Custom styles
.fas {
  @include colorize($color: accent);
}

.info {
  font-size: 20;
  /*horizontal-align: center;*/
  vertical-align: center;
}
</style>

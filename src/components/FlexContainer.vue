<template>
  <div class="flex-container" :style="style">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "FlexContainer",
  props: {
    wrap: {
      validator: function(value) {
        return ["nowrap", "wrap", "wrap-reverse"].indexOf(value) > -1;
      },
      default: "wrap"
    },
    justifyContent: {
      validator: function(value) {
        return (
          [
            "flex-end",
            "flex-start",
            "center",
            "space-between",
            "space-around"
          ].indexOf(value) > -1
        );
      },
      default: "center"
    },
    alignItems: {
      validator: function(value) {
        return (
          ["flex-start", "flex-end", "center", "baseline", "stretch"].indexOf(
            value
          ) > -1
        );
      },
      default: "stretch"
    },
    direction: {
      validator: function(value) {
        return (
          ["row", "row-reverse", "column", "column-reverse"].indexOf(value) > -1
        );
      },
      default: "row"
    },
    alignContent: {
      validator: function(value) {
        return (
          [
            "flex-end",
            "flex-start",
            "center",
            "space-between",
            "space-around",
            "stretch"
          ].indexOf(value) > -1
        );
      },
      default: "flex-start"
    },
    flex: {
      typt: [String, Number],
      default: 1
    },
    width: {
      type: String,
      default: "0px"
    },
    height: {
      type: String,
      default: "0px"
    }, 
    padding: {
      type: String,
      default: "0px"
    },
    margin: {
      type: String,
      default: "0px"
    }
  },
  computed: {
    style() {
      let style = {
        flexDirection: this.direction,
        flexWrap: this.wrap,
        justifyContent: this.justifyContent,
        alignItems: this.alignItems,
        flex: this.width != "0px" || this.height != "0px" ? "none" : this.flex
      };
      if (this.width != "0px") style["width"] = this.width;
      if (this.height != "0px") style["height"] = this.height;
      if (this.padding != "0px") style["padding"] = this.padding;
      if (this.margin != "0px") style["margin"] = this.margin;
      return style;
    }
  }
};
</script>

<style scoped>
.flex-container {
  display: -webkit-flex;
  display: flex;
}
</style>
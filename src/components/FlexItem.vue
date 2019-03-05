<template>
  <div class="flex-item" :style="style">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "FlexItem",
  props:{
    order: {
        type :[String,Number],
        default:0
    },
    grow: {
        type :[String,Number],
        default:0
    },
    shrink:{
        type:[String,Number],
        default:0
    },
    basis:{
        type:String,
        default:'auto'
    },
    self:{
        validator:function(value){
            return ['flex-end','flex-start','center','auto','baseline','stretch'].indexOf(value) > -1;
        },
        defalut:'auto'
    },
    width:{
        type :  String,
        default: '0px',
    },
    height:{
        type : String,
        default:'0px'
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
  computed:{
    style(){
        let style={
            order : this.order,
            flex : (this.width !='0px' || this.height !='0px')? 'none':`${this.grow} ${this.shrink} ${this.basis}` ,
            alignSelf : this.self,
        }
        if (this.width !='0px') style['width'] = this.width;
        if (this.height !='0px') style['height'] = this.height;
        if (this.padding != "0px") style["padding"] = this.padding;
        if (this.margin != "0px") style["margin"] = this.margin;
        return style;
    }
  }
}
</script>

<style scoped>
.flex-item {
  display: -webkit-flex;
  display:flex;
}
</style>
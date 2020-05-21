<template>
  <tree-chart :json="treeData"></tree-chart>
</template>

<script>
import TreeChart from "vue-tree-chart";

export default {
  name: "TreeView",
  components: {
    TreeChart
  },
  props: {
    moduleTree: {
      value: "",
      children: Array
    }
  },
  data: () => ({
    treeData: {
      name: "",
      children: []
    },
    sampleData: {
      name: "root",
      image_url: "https://static.refined-x.com/avat.jpg",
      children: [
        {
          name: "children1",
          image_url: "https://static.refined-x.com/avat1.jpg"
        },
        {
          name: "children2",
          image_url: "https://static.refined-x.com/avat2.jpg",
          mate: {
            name: "mate",
            image_url: "https://static.refined-x.com/avat3.jpg"
          },
          children: [
            {
              name: "grandchild",
              image_url: "https://static.refined-x.com/avat.jpg"
            },
            {
              name: "grandchild2",
              image_url: "https://static.refined-x.com/avat1.jpg"
            },
            {
              name: "grandchild3",
              image_url: "https://static.refined-x.com/avat2.jpg"
            }
          ]
        },
        {
          name: "children3",
          image_url: "https://static.refined-x.com/avat.jpg"
        }
      ]
    }
  }),
  methods: {
    toThree() {
      function makeTree(children) {
        if (children === undefined) {
          return undefined;
        }

        let tree = [];
        for (let i = 0; i < children.length; i++) {
          if (children[i].children.length <= 0) {
            tree.push(
              new Object({
                name: children[i].value
              })
            );
          } else {
            tree.push(
              new Object({
                name: children[i].value,
                children: makeTree(children[i].children)
              })
            );
          }
        }
        return tree;
      }

      this.treeData.name = this.moduleTree.value;
      this.treeData.children = makeTree(this.moduleTree.children);
    }
  },
  watch: {
    moduleTree: function() {
      this.toThree();
    }
  },
  created() {
    this.toThree();
  }
};
</script>
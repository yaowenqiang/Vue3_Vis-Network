<template>

  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
    <div id="mynetwork"></div>
    <button>Hola</button>
    <button>Hola</button>
    <button>Hola</button>
    <button>Hola</button>
    <button>Hola</button>
    
  </div>
</template>

<style>
#mynetwork {
  width: 100%;
  height: 620px;
  margin: 5px 0;
  border: 1px solid #000;
}
</style>

<script>
import { Network } from 'vis-network';

export default {
  name: "GrafosMy",
  data() {
    return {
      nodes: [
        { id: 1, label: "Node 1" },
        { id: 2, label: "Node 2" },
        { id: 3, label: "Node 3" },
        { id: 4, label: "Node 4" },
      ],

      edges: [
        { from: 1, to: 3 },
        { from: 1, to: 2 },
        { from: 2, to: 4 },
      ],
      options: {
        manipulation: {
          enabled: true,
          initiallyActive: true,
        },
        nodes: {
          physics: true,
        },
      },
      container: "",
      network: null,
    };
  },

  computed: {
    graph_data() {
      return {
        nodes: this.nodes,
        edges: this.edges,
      };
    },
  },

  mounted() {
    this.container = document.getElementById("mynetwork");

    this.network = new Network(
      this.container,
      this.graph_data,
      this.options
    );
  },
};
</script>

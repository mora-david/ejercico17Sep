<template>

<nav class="navbar navbar-light bg-light">
  
<div>
<a style="color:orange; font-size:1.5rem;">[ INSIDE ]</a>
<div>
<ul>
<li class="listMenu"><a href="/">All</a></li>
<li class="listMenu" v-for="tag1 in tags1.data" :key="tag1.id"><a :href="'/tags/'+tag1.slug">{{tag1.name}}</a></li>
</ul>
</div>
</div>

  <form class="form-inline">
    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
  </form>
</nav>


</template>

<script>
export default {
  props:["tags1"]
}
</script>
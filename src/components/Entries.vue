<template>
    <div class="main-container">
      <button>Newest to Oldest</button>
      <div class="main-container">
            <div class="post" v-for="data in entries.sort(function(a,b){
                  return new Date(b.date) - new Date(a.date);
                })" :key="data.id">
                <span class="post-author">
                    <span class="post-author-info">
                        <h3>{{data.title}}</h3>
                        <small>{{data.date}}</small>
                    </span>
                    <small>{{data.createTime}}</small>
                </span>
                <div class="post-image">
                    <img :src="data.image"/>
                </div>
                <div class="post-text">
                    <p>{{data.text}}</p>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
    export default {

      name: 'Entries',

      props: {
          entries: Array
      }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>

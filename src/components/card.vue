<template>
  <div class="card hover-effect">
      <div class="header">
          <span class="title">{{msg.title}}</span>
          <span class="logo"></span>
      </div>
      <div class="inner">
          <ul>
              <li v-for="(item, i) in msg.content" :key="i">
                  <a :href="item.url" target="_blank">{{item.name}}</a>
                  <p v-if="item.description">{{item.description}}</p>
              </li>
          </ul>
      </div>
      <div class="footer">
          <span class="logo"></span>
          <span class="title">{{msg.title}}</span>
      </div>
  </div>
</template>

<script>
export default {
    props:[
        'msg'
    ],
    data: function(){
        return {

        }
    }
}
</script>

<style>
a{
    color: inherit;
    text-decoration: none;
}
a[href]{
    color: #0075FF;
}
a[href]:hover{
    color: #034693;
}
.card{
    padding: 0.8em 2em;
    background-color: white;
    display: inline-block;
    border-radius: 0.4em;
}
.inner{
    border: solid 1px black;
    width: 12.4em;
    height: 20em;
}
.inner ul{
    text-align: left;
    list-style: none;
    padding-left: 0;
}
.inner ul li{
    padding: 5px;
    cursor: default;
}
.inner ul li:nth-child(even){
    background-color: #f2f2f4;
}
.header, .footer{
    text-align: left;
}
.title{
    font-weight: 600;  
}
.delay-hover{
    animation-delay: 1s;
}
.hover-effect {
    align-self: flex-end;
    animation-duration: 4s;
    animation-iteration-count: infinite;
    transform-origin: bottom;
    animation-name: hover;
    animation-timing-function:ease;
}
@keyframes hover {
    0%   { transform: translateY(0); }
    50%  { transform: translateY(-10px); }
    100% { transform: translateY(0); }
}

</style>
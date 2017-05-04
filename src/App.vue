<template lang="pug">

  div(id="app")
    header
      .profile
        a.profile-image(href="/edit-profile" title="Edit profile")
          Imgwrapper(v-bind:image-url=" '/static/img/UI/face_blank.png' ")
        .profile-detail
          .profile-name Taufik Akbar
          .profile-group
            a(href="#") Group Name
        .profile-news
          .events
            a(href="/my-events/").button.alt My Events
          .tasks
            a(href="/my-tasks/").button.alt My Tasks
    router-view( v-bind:testing="testing")

</template>

<script>

import Imgwrapper from "./components/Imgwrapper"

export default {
  name: 'app',
  data(){
    return {
      testing: "aaaaa"
    }
  },
  components: { Imgwrapper }
}
</script>

<style lang="scss">
body{
  margin: 0px;
}

button, .button{
  border-radius: none;
  background: #1B325F;
  color: white;
  border: none;
  font-ize: 18px;
  text-transform: uppercase;
  text-decoration: none;
  padding: 10px 20px;
  margin: 5px;
  display: inline-block;
  vertical-align: middle;
  cursor: pointer;
  transition: all 0.3s;

  &:hover{
    transform: translateY(-3px);
    box-shadow: 0px 3px 3px rgba(0,0,0,0.5);
  }

  &.alt{
    background: #E9F2F9;
    color: #1B325F;
  }
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #36393B;

  header{
    background: #1B325F;
    padding: 20px;
    text-align: left;
    box-shadow: 0px 2px 4px rgba(0,0,0,0.3);

    .profile{
      
      .profile-image{
        display: inline-block;
        vertical-align: middle;
        width: 50px;
        height: 50px;
        margin-right: 20px;
        border-radius: 50%;
        border: 2px solid #9CC4E4;
        overflow: hidden;

        .img-wrapper{
          height: 100%;
          width: 100%;
        }
      }

      .profile-detail{
        display: inline-block;
        vertical-align: middle;
        font-size: 18px;
        text-align: left;
        color: #E9F2F9;

        .profile-name{
          font-weight: 700;
          font-size: 20px;
        }

        .profile-group{

          a{
            color: #9CC4E4;

            &:hover{
              color: #E9F2F9;
            }
          }
        }
      }

      .profile-news{
        display: inline-block;
        vertical-align: middle;
        margin-left: 100px;

        & > div{
          display: inline-block;
          vertical: middle;
        }
      }

    }
  }
}
</style>

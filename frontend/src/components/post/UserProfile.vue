<template>
  <div class="user__profile">
    <div class="profile-image">
      <img src="https://scontent-icn1-1.xx.fbcdn.net/v/t1.0-1/c1.0.40.40/p40x40/10464317_731389536903285_545902977797627472_n.jpg?oh=ebf15b5ac585a4c153ddc30ef581a31c&oe=5A315064"/>
    </div>
    <div class="profile">
      <p style="margin-bottom: 0;">
        <span id="spn-user-name" class="profile__name">{{name}}</span>
      </p>
      <p class="profile__date">
        <span id="spnDate">{{updated_time}}</span> ·
        <span class="profile__right__icon"><i class="fa fa-globe"></i></span>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'UserProfile',
    props: ['name', 'updated_time'],
    data () {
      return {}
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .user__profile {
    display: block;
    font-size: 14px;
    line-height: 20px;
    margin-left: 2px;
    text-align: left;
  }

  .profile {
    display: inline-block;
    font-size: 14px;
    line-height: 20px;
    margin-left: 2px;
    text-align: left;
  }

  .profile-image {
    margin: 12px 4px 0 12px;
    vertical-align: top;
  }

  .profile-image {
    display: inline-block;
  }

  .profile__name {
    font-weight: 500;
    color: #555;
  }

  .profile__right__icon {
    margin-left: 4px;
  }

  .profile__date {
    color: gray;
    margin-top: 0;
  }
</style>

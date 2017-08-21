<template>
  <article class="post">
    <!--<PostOptionMenu/>-->
    <!--<UserProfile/>-->
    <p id="p-body" class="post__body">1  {{props.description}}  2</p>
    <!--<Multimedia id="div-media" class="post__media" data={this.props.data}  onGalleryEntryClick={(e)=>this.onClick(e)}/>-->
    <div>
      <div id="div-interaction" class="post__interaction">
        <span><strong>1</strong></span> <span>Like</span> <span><em>3</em> Comment</span> <span>Share</span>
      </div>
      <p id="p-respond" class="post__respond">
        <a class="post__respond__link">김종민님</a>이 좋아합니다.
      </p>
    </div>
    <ul id="ul-post-actionbar" class="post__action">
      <li class="post__action__item"><a href="#"><i class="fa fa-thumbs-o-up"/><span>좋아요</span></a></li>
      <li class="post__action__item"><a href="#"><i class="fa fa-commenting"/><span>댓글 달기</span></a></li>
      <li class="post__action__item"><a href="#"><i class="fa fa-share-alt"/><span>공유하기</span></a></li>
    </ul>
  </article>
</template>

<script>
  export default {
    name: 'Post',
    data () {
      return {
        props: ['description']
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>

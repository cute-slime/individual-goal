<template>
  <div class="feed">
    <article class="post" v-for="item in items" :key="item.id">
      <PostOptionMenu class="post__option-menu"></PostOptionMenu>
      <UserProfile></UserProfile>
      <p id="p-body" class="post__body">{{item.message}}</p>
      <!--<Multimedia id="div-media" class="post__media"/>-->
      <div>
        <div id="div-interaction" class="post__interaction">
          <span><strong>{{item.likes.summary.total_count}}</strong></span> <span>Like</span> <span><em>{{item.comments.summary.total_count}}</em> Comment</span> <span>Share</span>
        </div>
        <p id="p-respond" class="post__respond">
          <a class="post__respond__link">{{item.from.name}}님</a>이 좋아합니다.
        </p>
      </div>
      <ul id="ul-post-actionbar" class="post__action">
        <li class="post__action__item"><a href="#"><i class="fa fa-thumbs-o-up"></i><span> 좋아요</span></a></li>
        <li class="post__action__item"><a href="#"><i class="fa fa-commenting"></i><span> 댓글 달기</span></a></li>
        <li class="post__action__item"><a href="#"><i class="fa fa-share-alt"></i><span> 공유하기</span></a></li>
      </ul>
    </article>
  </div>
</template>

<script>
  import PostOptionMenu from './post/PostOptionMenu'
  import UserProfile from './post/UserProfile'

  export default {
    name: 'FeedList',
    components: {PostOptionMenu, UserProfile},
    data () {
      return {
        apiEndpoint: 'http://localhost:8081/',
        version: 'v1.0',
        api: 'feed',
        items: [
          {
            message: '집에 오는 길에서 만난 #개구리\n대빵 큼 !\n대려가서 어항에 키울까? ㅋㅋ\n#개구리 #방학천',
            picture: 'https://scontent.xx.fbcdn.net/v/t1.0-0/p130x130/19905372_1578141822228048_5862932231829921537_n.jpg?oh=a70975952de33241e9bedb3a950c6205&oe=59EB96BD',
            from: {
              name: 'Jongmin Kim',
              id: '100000967353052'
            },
            id: '100000967353052_1578141785561385',
            likes: {
              data: [],
              summary: {
                total_count: 6,
                can_like: true,
                has_liked: false
              }
            },
            comments: {
              data: [],
              summary: {
                order: 'chronological',
                total_count: 1,
                can_comment: true
              }
            }
          },
          {
            message: 'Test',
            picture: 'https://scontent.xx.fbcdn.net/v/t1.0-0/p130x130/19905372_1578141822228048_5862932231829921537_n.jpg?oh=a70975952de33241e9bedb3a950c6205&oe=59EB96BD',
            from: {
              name: 'Jongmin Kim',
              id: '100000967353052'
            },
            id: '100000967353052_1578141785561386',
            likes: {
              data: [],
              summary: {
                total_count: 12,
                can_like: true,
                has_liked: false
              }
            },
            comments: {
              data: [],
              summary: {
                order: 'chronological',
                total_count: 37,
                can_comment: true
              }
            }
          }
        ]
      }
    },
    mounted: function () {
      this.fetchData()
    },
    watch: {
      $route: 'fetchData'
    },
    methods: {
      fetchData () {
        console.log('요기서 fetch api data!')
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .post {
    width: 500px;
    position: relative;
    border: 1px solid #ccc;
    margin: auto;
    margin-bottom: 20px;
    background-color: white;
  }

  .post__option-menu {
    margin-right: 16px;
    position: absolute;
    right: 0;
    top: 0;
    margin-top: 8px;
    font-size: 17px;
    cursor: pointer;
  }

  .post__media {
    margin-left: 10px;
    margin-right: 10px;
    box-sizing: border-box;
  }

  .post__body {
    margin: 10px;
    font-size: 14px;
    color: #444444;
    line-height: 18px;
    letter-spacing: 0px;
  }

  .post__interaction {
    color: rgb(102, 102, 102);
    font-size: 13px;
    margin-top: 8px;
    margin-left: 10px;
    margin-right: 10px;
    display: inline-block;
  }

  .post__respond {
    float: right;
    font-size: 14px;
    margin: 10px 10px 6px 10px;
    font-weight: 400;
    color: rgb(102, 102, 102);
  }

  .post__respond .post__respond__link {
    color: #3b5998;
    cursor: pointer;
  }

  .post__action {
    border-top-color: rgb(229, 229, 229);
    border-top-style: solid;
    border-top-width: 1px;
    text-align: left;
    padding: 0;
    margin: 12px 12px 4px 24px;
  }

  .post__action > li:first-child {
    margin-left: 0;
  }

  .post__action .post__action__item {
    display: inline-block;
    margin-top: 8px;
    margin-bottom: 8px;
    margin-left: 28px;
    font-size: 14px;
    font-weight: 500;
    color: dimgrey;
  }

  .post__action .post__action__item > a {
    color: lightslategrey;
    text-decoration: none;
  }

  .post__action > li:first-child .post__action__item > a > span {
    margin-left: 5px;
  }
</style>

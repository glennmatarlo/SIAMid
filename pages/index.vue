<template>
  <div>
    <NavBar />

<template v-if="$auth.loggedIn">

  <div class="jumbotron">
      <h1 class="display-4">Welcome {{$auth.user.name}}</h1>
      <hr class="my-4">
      <p class="lead" style="text-align:center;">
        Borrow online books, anytime, anywhere!
      </p>
    </div>

    <div style="margin-left:20px;">
      <div class="row">

      <div class="col-sm-3">
      <div class="card border-info mb-3" style="width:18rem;">
        <img class="card-img-top" src="https://www.designforwriters.com/wp-content/uploads/2017/10/design-for-writers-book-cover-tf-2-a-million-to-one.jpg" alt="Card image cap">
      </div>
    </div>

    <div class="col-sm-3">
      <div class="card border-info mb-3" style="width:18rem;">
        <img class="card-img-top" src="https://d1csarkz8obe9u.cloudfront.net/posterpreviews/contemporary-fiction-night-time-book-cover-design-template-1be47835c3058eb42211574e0c4ed8bf_screen.jpg?ts=1594616847" alt="Card image cap">
      </div>
    </div>

    <div class="col-sm-3">
        <div class="card border-info mb-3" style="width:18rem;">
          <img class="card-img-top" src="https://99designs-blog.imgix.net/blog/wp-content/uploads/2017/02/attachment_80004080-e1488217702832.jpg?auto=format&q=60&fit=max&w=930" alt="Card image cap">
        </div>
      </div>
      <div class="col-sm-3">
        <div class="card border-info mb-3" style="width:18rem;">
          <img class="card-img-top" src="https://s26162.pcdn.co/wp-content/uploads/2019/01/81SBy9jbbHL.jpg" alt="Card image cap">
        </div>
      </div>
      
      </div>
    </div>

        <div style="margin-left:20px;">
      <div class="row">

      <div class="col-sm-3">
      <div class="card border-info mb-3" style="width:18rem;">
        <img class="card-img-top" src="https://miblart.com/wp-content/uploads/2020/11/Leia_Hunter-1-683x1024.jpg" alt="Card image cap">
      </div>
    </div>

    <div class="col-sm-3">
      <div class="card border-info mb-3" style="width:18rem;">
        <img class="card-img-top" src="https://static-cse.canva.com/blob/463853/1024w-nDo6R01jwsQ.jpg" alt="Card image cap">
      </div>
    </div>

    <div class="col-sm-3">
        <div class="card border-info mb-3" style="width:18rem;">
          <img class="card-img-top" src="https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F6%2F2016%2F09%2F9781408855652-png.jpg" alt="Card image cap">
        </div>
      </div>
      <div class="col-sm-3">
        <div class="card border-info mb-3" style="width:18rem;">
          <img class="card-img-top" src="https://static-cse.canva.com/blob/142563/White-and-Pink-Script-Young-Adult-Book-Cover.jpg" alt="Card image cap">
        </div>
      </div>
      
      </div>
    </div>
</template>

  <template v-else>
    <div class="jumbotron">
      <h1 class="display-4">Welcome</h1>
      <hr class="my-4">
      <p class="lead" style="text-align:center;">
        <a class="btn btn-primary btn-lg" href="/login" role="button">Log In</a>
        <a class="btn btn-primary btn-lg" href="/register" role="button">Register</a>
      </p>
    </div>
  </template>

<Footer />
</div>
</template>

<script>
export default {
  auth: false
}
</script>


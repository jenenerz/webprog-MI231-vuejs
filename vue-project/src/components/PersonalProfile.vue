<template>
<div id="title" class="title">
  <img src="images/title.png" alt="Title Image">
</div>

<div class="navbar">
  <img src="images/website-logo.png" alt="Logo">
  <ul>
    <li><a href="#intro">Intro</a></li>
    <li><a href="#education">Acads</a></li>
    <li><a href="#hobbies">More</a></li>
    <li><a href="#comments">Comments</a></li>
    <li><a href="#ref">References</a></li>
  </ul>
</div>

<div class="content">
  <div id="intro" class="container intro">
    <div class="intro-content">
      <div class="intro-text">
        <h2>HELLO! I'M JENINE</h2>
        <p>
          I am a 2nd year student currently taking Bachelor of Science in Information Technology with specialization in Mobile and Internet Technologies. I am 20 years old and I love music and froyo!!
        </p>
        <p>
          Add me on my socials!<br><br>
          <a href="https://www.linkedin.com/in/jenine-dulay-b9988b284/" target="_blank">LinkedIn</a> |
<a href="https://open.spotify.com/user/parkjimin3389?si=5aaf93e351804922" target="_blank">Spotify</a> <br>
<a href="https://free-palestine.carrd.co/" target="_blank">Stand with Palestine</a>
        </p>
      </div>
      <img src="images/intro-pic.JPG" alt="Your Picture" class="intro-image">
    </div>
  </div>

  <div id="education" class="container">
    <h2 class="center">EDUCATION & ACHIEVEMENTS</h2>
    <div class="two-columns">
      <div>
        <h3>Immaculate Heart of Mary College (2018-2023)</h3>
        <ul>
          <li>Junior High - Senior High (STEM Strand)</li>
          <li>Graduated Junior High with Honors</li>
          <li>Graduated Senior High with Honors</li>
          <li>STEM SOCIETY Organization Member</li>
        </ul>
      </div>
      <div>
        <h3>Asia Pacific College (2023-PRESENT)</h3>
        <ul>
          <li>BSIT-MI</li>
          <li>1st Year of College - Honors</li>
          <li>Cinemasoma Member</li>
          <li>Flickers Photo Society Member</li>
        </ul>
      </div>
    </div>
  </div>

  <div id="experience" class="container">
    <h2 class="center">IT EXPERIENCE</h2>
    <div class="two-columns">
      <ul>
        <li>Basic Java</li>
        <li>Basic Python</li>
        <li>Had HTML during grade school</li>
        <li>UI/UX Experience (Website and mobile: RamQuest - Group Project)</li>
        <li>Mobile Application (RESCUE app - Group Project)</li>
      </ul>
      <img src="images/it-exp.png" alt="IT Projects">
    </div>
  </div>

  <div class="container two-columns">
    <div id="hobbies">
      <h2 class="center">Hobbies & Interests</h2>
      <ul>
        <li>Music (1D, Chappell Roan, Olivia Rodrigo, SZA)</li>
        <li>Films (Beautiful Boy, Challengers, Pitch Perfect Trilogy)</li>
        <li>Shows (Bojack Horseman, Grey’s Anatomy, The Bear)</li>
        <li>Video Games (Life is Strange, The Last of Us, Valorant)</li>
        <li>Photography</li>
        <li>F1</li>
      </ul>
    </div>
    <div id="goals">
      <h2 class="center">Goals & Dreams</h2>
      <ul>
        <li>To be able to live on my own and give back to my siblings</li>
        <li>To be able to meet my favorite artists</li>
        <li>Graduate college with Honors</li>
        <li>Learn to play the piano</li>
        <li>Find a stable job that I enjoy</li>
        <li>Be able to drive without getting anxious</li>
        <li>To live near a beach and be able to travel all around the world</li>
      </ul>
    </div>
  </div>
</div>

<div id="gallery" class="container">
  <div class="two-columns">
    <div>
      <h2 class="center">PICTURE GALLERY</h2>
    </div>
    <div>
      <img src="images/picture-gallery.png" alt="Gallery Image" style="max-width: 100%; border-radius: 10px;">
    </div>
  </div>
</div>

<div id="comments" class="container guestbook-container">
  <div class="header">
    <div class="title-container">Comments</div>
  </div>
  <form @submit.prevent="addComment">
    <div>
      <p>
        Name: <br>
        <input type="text" v-model="guestName" placeholder="Enter your name" required />
      </p>
      <p>
        Comment: <br>
        <textarea v-model="guestComment" placeholder="Write your comment" rows="4" required></textarea>
      </p>
      <button type="submit">Submit</button>
    </div>
  </form>
  <div class="comment-section">
    <div v-for="comment in comments" :key="comment.id" class="comment">
      <p><strong>{{ comment.name }}</strong></p>
      <p>{{ comment.message }}</p>
    </div>
  </div>
</div>



<div id="ref" class="container">
  <h2 class="center">References</h2>
  <ul>
    <li><a href="https://www.w3schools.com/css/css_navbar_vertical.asp
" target="_blank">W3Schools - NavBar</a></li>
    <li><a href="https://www.w3schools.com/css/css3_flexbox.asp
" target="_blank">W3Schools - Flexbox</a></li>
    <li><a href="https://www.w3schools.com/html/html_links.asp
" target="_blank">W3Schools - Links</a></li>
    <li><a href="https://dev.to/tsanak/simple-comment-section-with-vue-components-1cdm
" target="_blank">Vue.js - Comment section</a></li>
<li><a href="https://vuejs.org/guide/introduction.html
  " target="_blank">Other Vue.js</a></li>
  </ul>
</div>

</template>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f8f7f2;
  color: #562123;
}
#ref ul {
  margin-left: 230px;
}

a {
  color: #562123;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

#title img {
  display: block;
  margin: 8px auto;
  max-width: 650px;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 200px;
  background-color: #562123;
  color: #f8f7f2;
  padding: 20px 10px;
  border-radius: 8px;
}

.navbar img {
  max-width: 150px;
  padding: 32px 20px;
}

.navbar ul {
  list-style: none;
  padding: 0;
}

.navbar ul li {
  margin-bottom: 20px;
}

.navbar ul li a {
  color: white;
}

.content {
  margin-left: 220px;
  padding: 20px;
}

.container {
  margin-bottom: 20px;
  padding: 20px;
  border-radius: 10px;
}

#education, #hobbies, #goals {
  background-color: #562123;
  color: #f8f7f2;
  border-radius: 10px;
}

#education h2, #hobbies h2, #goals h2 {
  color: #f8f7f2;
}

#experience {
  border: 2px solid #562123;
  padding: 20px;
}

h2 {
  color: #562123;
}

h2.center {
  text-align: center;
}

ul {
  margin-left: 20px;
}

.intro {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.intro img {
  max-width: 400px;
  border-radius: 200px;
}

.two-columns {
  display: flex;
  gap: 20px;
  justify-content: flex-end;
}

.two-columns > div {
  flex: 1;
}

#experience .two-columns {
  justify-content: flex-start;
}

#education .two-columns {
  justify-content: flex-end;
}

#experience img {
  margin-left: 400px; 
  max-width: 300px;
}

p {
  color: #562123;
}

.intro-content {
  display: flex;
  align-items: center;
  gap: 20px;
}

.intro-text {
  flex: 1;
}

@media only screen and (max-width: 768px) {
  .navbar {
    width: 100%;
    position: relative;
    height: auto;
  }

  .content {
    margin-left: 0;
    padding: 10px;
  }

  .two-columns {
    flex-direction: column;
    gap: 10px;
  }

  #title img {
    max-width: 100%;
  }

  .intro img {
    max-width: 250px;
  }

  .navbar ul li {
    margin-bottom: 10px;
  }

  .navbar img {
    max-width: 120px;
  }

  #experience img {
    max-width: 100%;
    margin-left: 0;
  }
}
/*Comment Section */
.comment-section {
  margin-top: 20px;
}

.comment {
  border-top: 1px solid #ddd;
  padding: 10px 0;
}

.comment p {
  margin: 5px 0;
}

.guestbook-container {
  background-color: #f8f7f2;
  border: 2px solid #562123;
  padding: 20px;
  border-radius: 10px;
  max-width: 800px; 
  margin: 0 auto;
  padding: 20px;
  border-radius: 10px;
}

.guestbook-container .header {
  text-align: center;
  margin-bottom: 20px;
}

.guestbook-container .header .title-container {
  font-size: 24px;
  font-weight: bold;
  color: #562123;
}

.guestbook-container form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.guestbook-container input, .guestbook-container textarea {
  padding: 10px;
  border: 1px solid #562123;
  border-radius: 5px;
  font-size: 16px;
  width: 100%;
  box-sizing: border-box;
}

.guestbook-container button {
  background-color: #562123;
  color: #f8f7f2;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.guestbook-container button:hover {
  background-color: #6c3a32;
}
</style>

<script>
const comments = Vue.createApp({
    data() {
      return {
        guestName: '',
        guestComment: '',
        comments: []
      };
    },
    methods: {
      addComment() {
        const newComment = {
          id: this.comments.length + 1,
          name: this.guestName,
          message: this.guestComment
        };
        this.comments.push(newComment);
        this.guestName = '';
        this.guestComment = '';
      }
    }
  });

  comments.mount('#comments');
</script>


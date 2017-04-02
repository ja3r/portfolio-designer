<template>
  <div class="container app-body">
    <div class="row">
      <div class="col-md-3"></div>

      <div class="col-md-6">
        <h2>Portfolio Designer</h2>
        <h4>Use this to customize a personal portfolio website for yourself.</h4>
        <hr>

        <h4>Navigation Bar</h4>

        <transition name="fade"><div class="example panel panel-default" v-if="firstexample">
          <p>Large: 50px vertically</p>
          <p>Medium: 38px vertically</p>
          <p>Small: 32px vertically</p>
        </div></transition>
        <span class="label label-default" @click="firstexample = !firstexample">Height</span>
          <select v-model="navHeightSelect" class="form-control input-sm">
            <option v-for="navHeight in navHeights" v-bind:value="navHeight.value">
              {{ navHeight.text }}
            </option>
          </select>

          <transition name="fade"><div class="example panel panel-default" v-if="secondexample">
            <p class="bg-primary color-example-lb">Light Blue</p>
            <p class="bg-primary color-example-lp">Light Purple</p>
            <p class="bg-primary color-example-lg">Light Green</p>
            <p class="bg-primary color-example-lgr">Light Gray</p>
            <p class="bg-primary color-example-red">Red</p>
            <p class="bg-primary color-example-blue">Blue</p>
          </div></transition>
          <span class="label label-default" @click="secondexample = !secondexample">Color</span>
          <select v-model="navColorSelect" class="form-control input-sm">
            <option v-for="navColor in navColors" v-bind:value="navColor.value">
              {{ navColor.text }}
            </option>
          </select>

          <transition name="fade"><div class="example panel panel-default" v-if="thirdexample">
            <p>Left: Navigation links will be pushed to the left side.</p>
            <p>Center: Navigation links will be centered.</p>
            <p>Right: Navigation links will be pushed to the right side.</p>
          </div></transition>
          <span class="label label-default" @click="thirdexample = !thirdexample">Alignment</span>
          <select v-model="navAlignSelect" class="form-control input-sm">
            <option v-for="navAlignment in navAlignments" v-bind:value="navAlignment.value">
              {{ navAlignment.text }}
            </option>
          </select>

          <hr>

          <h4>Body</h4>

          <transition name="fade"><div class="example panel panel-default" v-if="fourthexample">
            <p>Lighter</p>
            <p class="bg-primary color-example-darker">Darker</p>
          </div></transition>
          <span class="label label-default" @click="fourthexample = !fourthexample">Lighter/Darker</span>
          <select v-model="bodyColorSelect" class="form-control input-sm">
            <option v-for="bodyColor in bodyColors" v-bind:value="bodyColor.value">
              {{ bodyColor.text }}
            </option>
          </select>

          <transition name="fade"><div class="example panel panel-default" v-if="fifthexample">
            <p>Center: Content of the website will be centered.</p>
            <p>Left: Content of the website will be pushed to the left.</p>
          </div></transition>
          <span class="label label-default" @click="fifthexample = !fifthexample">Alignment</span>
          <select v-model="bodyAlignSelect" class="form-control input-sm">
            <option v-for="bodyAlignment in bodyAlignments" v-bind:value="bodyAlignment.value">
              {{ bodyAlignment.text }}
            </option>
          </select>
      </div>
      <div class="col-md-3"></div>
    </div>
    <hr>
    <div class="row">
      <div class="col-md-3">
        <h4>Step 1:</h4>
        <p>Download the core HTML files here: <a class="btn btn-default" href="https://www.dropbox.com/s/1wfzf6t6wdv7rnh/my-portfolio.zip?dl=0" target="_blank" role="button">Download</a></p>
        <h6> Make the following changes:</h6>
        <ul>
          <li>Change the 'FirstName LastName' in index.html to your actual name</li>
          <li>Add a image sized 250x250 px to the images folder for your index.html</li>
          <li>Change all "http://placehold.it/800x800" in portfolio.html to 800x800 images showcasing your work</li>
          <li>Change the email in contact.html to your actual email address</li>
          <li>Change the &lt;footer&gt; in all three files to whatever you want it to say!</li>
        </ul>
      </div>
      <div class="col-md-6">
        <h4>Step 2:</h4>
        <p>Copy your customized css file below into the file named "style.css"</p>
    <textarea class="form-control" rows="10">
      body {
        font-family: 'Quattrocento Sans', sans-serif;
        background-color: {{ bodyColorSelect }};
      }

      h1{
        color: #454c56;
      }
      .nav-bar {
        background: {{ navColorSelect }};
        position: absolute;
        width: 100%;
        left: 0;
        right: 0;
        top: 0;
        text-align: {{ navAlignSelect }};
        {{ navHeightSelect }}
        box-shadow: 0px 1px 8px #efefef;
      }

      .nav-item {
      margin-left: 40px;
      margin-right: 40px;
      text-decoration: none;
      color: #454c56;
      }

      .nav-item:hover{
        color: black;
      }

      .nav-item:visited{
        color: #454c56;
      }

      .content {
        margin-left: {{ bodyAlignSelect }};
        margin-right: auto;
        margin-top: 100px;
        width: 50%;
        text-align: center;
      }

      .img-main {
        height: 250px;
        width: 250px;
        border-radius: 50%;
        border: 1px solid #efefef;
      }

      .footer{
        font-size: 12px;
        position: absolute;
        right: 0;
        bottom: 0;
        left: 0;
        background-color:#efefef;
        color: #454c56;
        text-align:center;
      }

      .container {
        margin: auto;
        max-width: 1200px;
      }

      .responsive-image {
        max-width: 100%;
      }

      .cell img {
        display: block;
      }

      @media screen and (min-width: 600px) {
        .grid {
          display: flex;
          flex-wrap: wrap;
          flex-direction: row;
        }
        .cell {
          width: 50%;
        }
      }

      @media screen and (min-width: 1000px) {
        .cell {
          width: calc(100% / 3);
        }
      }
    </textarea>
    </div>
    <div class="col-md-3">
      <h4>Step 3:</h4>
      <p>Upload your website and enjoy!</p>

    </div>
  </div>

  </div>
</template>

<script>
export default {
  data: function () {
    return {
    navHeightSelect: 'padding-top: 16px; padding-bottom: 16px;',
    navHeights: [
      { text: 'Large', value: 'padding-top: 16px; padding-bottom: 16px;'},
      { text: 'Medium', value: 'padding-top: 10px; padding-bottom: 10px;'},
      { text: 'Small', value: 'padding-top: 7px; padding-bottom: 7px;'}
    ],
    navColorSelect: '#FFFFFF',
    navColors: [
      { text: 'White', value: '#FFFFFF'},
      { text: 'Light Blue', value: '#c2d4d8'},
      { text: 'Light Purple', value: '#b0aac2'},
      { text: 'Light Green', value: '#dbe9d8'},
      { text: 'Light Gray', value: '#c9c9c9'},
      { text: 'Red', value: '#c43235'},
      { text: 'Blue', value: '#98dafc'}
    ],
    navAlignSelect: 'center',
    navAlignments: [
      { text: 'Left', value: 'left'},
      { text: 'Center', value: 'center'},
      { text: 'Right', value: 'right'}
    ],
    bodyColorSelect: '#FFFFFF',
    bodyColors: [
      { text: 'Lighter', value: '#FFFFFF'},
      { text: 'Darker', value: '#efefef'}
    ],
    bodyAlignSelect: 'auto',
    bodyAlignments: [
      {text: 'Center', value: 'auto'},
      {text: 'Left', value: '0'}
    ],
    firstexample: false,
    secondexample: false,
    thirdexample: false,
    fourthexample: false,
    fifthexample: false
  }
}

};
</script>

<style src="../assets/css/master.css">

</style>

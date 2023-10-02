<template>
  <div>
    <button @click="play()">sb</button>
    <audio id="div1" src="blank.mp4" autoplay loop></audio>
    <embed src="blank.mp4" loop="true" autostart="true" width="2" height="0" />
  </div>
</template>
<script setup>
  import { onMounted } from "vue";
  const sb = () => {
    console.log("mounting");
    var audio = document.createElement("audio");
    audio.webkitPlaysinline = "true";
    audio.playsinline = "true";
    audio.muted = "false";
    audio.src = "blank.mp4";
    audio.addEventListener(
      "ended",
      function () {
        document.removeChild(this);
      },
      false
    );
  };

  function play() {
    var div1 = document.getElementById("div1");
    div1.play();
    // document.getElementsByTagName("audio").play();
  }

  onMounted(() => {
    console.log("before");
    //   sb();
  });
</script>

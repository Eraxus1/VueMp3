<template>
  <div>
    <img :src="songImageUrl" alt="Şarkı Resmi">
    <p>{{ songTittle }}</p>
    <button @click="playSong">Şarkıyı Çal</button>
    <button @click="stopSong">Şarkıyı Durdur</button>

    <audio ref="audioPlayer" :src="songUrl"></audio>
    <button @click="nextSong">Sıradaki Şarkıya Geç</button>
    <button @click="backSong">Geri Dön</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      songs: [
        {
          title: 'Anıl Piyancı BP',
          url: '/music/anılpiyancı.mp3',
          image: 'images/faviconlogo.jpg'
        },
        {
          title: 'Anıl Piyancı BP',
          url: '/music/anılutd',
          image: 'images/anıl.jpg'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/anılssd.mp3',
          image: 'images/faviconlogo.jpg'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/anılbbg.mp3',
          image: '/images/anıl.jpg'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/joker.mp3',
          image: '/images/favicon.ico'
        },
      ],
      songIndex: 0
    };
  },
  computed: {
    songUrl() {
      return this.songs[this.songIndex].url
    },
    songImageUrl() {
      return this.songs[this.songIndex].image
    },
    songTittle() {
      return this.songs[this.songIndex].title
    }
  },
  methods: {
    playSong() {
      this.$refs.audioPlayer.play();
    },
    stopSong() {
      this.$refs.audioPlayer.pause();
    },
    nextSong() {
      this.songIndex++;
    },
    backSong() {
      this.songIndex--;
    },
  }
};
</script>
<style>
body{
  background-color: black;
  color: aqua;
}
div {
  display: flex;
  flex-direction: column;
  align-items: center;
}
img {
  margin: auto;
  display: block;
  width: 250px;
  height: 250px;
}
button {
  display: inline;
  opacity: 0.7;
  color: white;
  background: none;
  border: 1px dashed aqua;
  padding: 5px;
  margin: 2px;
  cursor: pointer;
}
audio {
  display: none;
}
</style>

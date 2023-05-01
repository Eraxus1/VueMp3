<template>
  <Header />

  <div class="main">
    <audio ref="audioPlayer" :src="songUrl"></audio>
    <img :src="songImageUrl" alt="Şarkı Resmi">
    <p>{{ songTittle }}</p>
    <div class="buttons">
      <button @click="playSong" class="songbutton">Şarkıyı Çal</button>
      <button @click="stopSong" class="songbutton">Şarkıyı Durdur</button>
      <button @click="nextSong" class="songbutton">Sıradaki Şarkıya Geç</button>
      <button @click="backSong" class="songbutton">Geri Dön</button>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue"
export default {
  components: {
    Header
  },
  data() {
    return {
      songs: [
        {
          title: 'Anıl Piyancı - Baba Parası',
          url: '/music/anılpiyancı.mp3',
          image: '/images/anıl.jpg'
        },
        {
          title: 'Anıl Piyancı - Üstümde Tütüyo Duman',
          url: '/music/anılutd.mp3',
          image: '/images/anıl.jpg'
        },
        {
          title: 'Anıl Piyancı - S.S.D',
          url: '/music/anılssd.mp3',
          image: '/images/anıl.jpg'
        },
        {
          title: 'Anıl Piyancı - Boğar Beni Gündüz',
          url: '/music/anılbbg.mp3',
          image: '/images/anıl.jpg'
        },
        {
          title: 'Joker - Eriyorum Hala',
          url: '/music/joker.mp3',
          image: '/images/anıl.jpg'
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
      if (this.songIndex >= this.songs.length) {
        this.songIndex = 0;
      }
    },
    backSong() {
      this.songIndex--;
    },
  }
};
</script>
<style>
body {
  background-color: #053754;
  color: aqua;
}

.main {
  top: 0;
  left: 0;
  position: fixed;
  margin-left: 30%;
  margin-top: 150px;
}

p {
  text-align: center;
  padding: 15px;
  margin: auto;
  color: white;
}

img {
  margin: auto;
  display: block;
  width: 200px;
  height: 200px;
  border-radius: 100px;
}

.buttons {
  width: 600px;
  margin: auto;
}

.songbutton {
  margin: 3px;
  background-color: none;
  color: black;
  opacity: 0.7;
  padding: 10px 20px;
  font-size: 16px;
  width: 200px;
  left: 98px;
  border: none;
  position: relative;
  box-shadow: 0 0 5px white, 0 0 10px #053754;
  outline: none;
}

.songbutton:hover {
  transition: 1s;
  margin: 3px;
  background-color: #053754;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  position: relative;
  box-shadow: 0 0 5px white;
  outline: none;
  color: white;
}

audio {
  display: none;
}

@media (max-width:500px) {


  .buttons {
    width: 100%;
    margin: auto;
    margin-left: -120px;
  }

  button {
    display: block;
    width: 20%;
    margin-left: -75px;
  }

  img {
    border-radius: 100px;
    margin-left: -25px;
  }

  .main p {
    text-align: center;
    width: 100%;
  }

}
</style>
<template>
      <Header />

  <div>
    <audio ref="audioPlayer" :src="songUrl"></audio>
    <img :src="songImageUrl" alt="Şarkı Resmi">
    <p>{{ songTittle }}</p>
    <div class="buttons">
      <button @click="playSong">Şarkıyı Çal</button>
      <button @click="stopSong">Şarkıyı Durdur</button>
      <button @click="nextSong">Sıradaki Şarkıya Geç</button>
      <button @click="backSong">Geri Dön</button>
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

div {
  margin-top: 70px;
  display: block;
  align-items: center;
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

button {
  margin: 3px;
  background-color: none;
  color: black;
  opacity: 0.7;
  padding: 10px 20px;
  font-size: 16px;
  width:200px;
  left: 98px;
  border: none;
  position: relative;
  box-shadow: 0 0 5px white, 0 0 10px #053754;
  outline: none;
}

button:hover {
  transition: 1s;
  margin: 3px;
  background-color: #053754;  
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  position: relative;
  box-shadow: 0 0 5px white;
  outline: none;
  color:white;
}

audio {
  display: none;
}

@media (max-width:500px) {
  .buttons {
    width: 100%;
    margin: auto;
  }

  button {
    display: block;
    width: 50%;
    margin: 5px;
  }

  img {
    border-radius: 100px;
    margin: auto;
  }

  p {
    text-align: center;
  }
}</style>


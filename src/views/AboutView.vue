<template>
  <div>
    2.sayfa
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
          url: '/music/anılpiyancı.mp3'
        },
        {
          title: 'Anıl Piyancı BP',
          url: '/music/anılutd.mp3'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/anılssd.mp3'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/anılbbg.mp3'
        },
        {
          title: 'Anıl Piyancı S.S.D',
          url: '/music/joker.mp3'
        },
      ],
      songIndex: 0
    };
  },
  computed: {
    songUrl() {
      return this.songs[this.songIndex].url
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




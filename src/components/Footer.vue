<template>
    <div>
        <p>Tüm hakları saklıdır. {{ yil }}</p>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            yil: 2023
        };
    },
    mounted() {
        setInterval(() => {
            const bugun = new Date();
            if (bugun.getMonth() === 0 && bugun.getDate() === 1) {
                this.yil++;
            }
        }, 1000 * 60 * 60 * 24); // Her gün kontrol etmek için 24 saatlik bir süre
    }
};
</script>
  
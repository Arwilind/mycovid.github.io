<template>
    <div class="grid-container">
        <!-- Box 1 -->
        <div class="box-one">
            <i class="fa-regular fa-hospital"></i>
            <h3 class="primary-title">Tapaukset</h3>

            <div class="">
                <span class="secondary-title">Uudet:</span>
                {{ numberWithCommas(stats.NewConfirmed) }}
            </div>
            <div class="">
                <span class="third-title">Yhteensä:</span>
                {{ numberWithCommas(stats.TotalConfirmed) }}
            </div>
        </div>

        <!-- Box 2 -->
        <div class="box-two">
                    <i class="fa-solid fa-skull-crossbones"></i>
            <h3 class="primary-title">Kuolemat
            </h3>
            

            <div class="">
                <span class="secondary-title">Uudet:</span>
                {{ numberWithCommas(stats.NewDeaths) }}
            </div>
            <div class="">
                <span class="third-title">Yhteensä:</span>
                {{ numberWithCommas(stats.TotalDeaths) }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DataBoxes',
    props: ['stats'],
    setup() {
        return {
            numberWithCommas(x) {
                return x.toString()
                    .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
            }
        };
    }
};
</script>

<style scoped>

.box-two {
     box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #2065aab3;
  padding: 40px;
  text-align: center;
  border-radius: 8px;
  color:white;
 
}


.box-one {
     box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  background-color: #2065aab3;
  padding: 40px;
  text-align: center;
  border-radius: 8px;
  color:white;

}

.grid-container {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
  padding-left:10px ;
  padding-right:10px ;
}

@media (min-width: 768px) {
  .grid-container {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
}
.primary-title{
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 1rem;

}
.secondary-title{
    font-size: 1rem;
    font-weight: bold;
    margin-bottom: 1rem;

}
.third-title{
    font-size: 1rem;
    font-weight: bold;
    margin-bottom: 1rem;

}
.fa-solid {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: #f5f5f5;
}
.fa-regular{
    font-size: 2.5rem;
    margin-bottom: 1rem;
    color: #f5f5f5;
}

</style>
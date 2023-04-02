<template>
  <div :class="typeof weathers.location != 'undefined' && weathers_temp>4 && weathers_temp<29 ? 'weather_reportbg' : weathers_temp<5 ? 'weather_report_coldbg':'weather_report_warmbg' ">
    <div class="weather_report">
      <input type="text" name="" id="" class="weather_search" placeholder="Search" v-model="query" v-on:keyup="loadData">
      <!-- <button v-on:click="loadData" class="signup-btn">Sign Up</button> -->
      <div  class="weather_result">
        <div style="line-height: 40px;" v-if="typeof weathers.location != 'undefined'" >
          <p class="location">{{weathers.location.name}}, {{weathers.location.region}}, {{weathers.location.country}}</p>
          <p class="day_date">{{dateBuilder()}}</p>
          <p class="weather_temp">{{Math.round(weathers_temp)}}°C</p>
          <p class="weather_cond">{{weathers.current.condition.text}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  
import axios from "axios";

export default ({
    name: 'HelloWorld',
    data(){
      return {
      api_key: 'ad58c6b3673d491aa8e71421221807',
      url_base: 'https://api.weatherapi.com/v1/current.json',
      query: '',
      weathers: {},
      weathers_temp:{}
    }
  },
  methods:{
    async loadData()
    {
      /*let url = this.url_base+this.query+"?unitGroup=metric&include=current&key="+this.api_key+"&contentType=json";*/
      let result=await axios.get(`${this.url_base}?key=${this.api_key}&q=${this.query}`);
      
      console.log(JSON.stringify(result.data.location.name));
      this.weathers=result.data;
      this.weathers_temp=result.data.current.temp_c;
      console.log(JSON.stringify(this.weathers));
       console.log(JSON.stringify(Math.round(this.weathers_temp)));
    },
    dateBuilder (){
      let d= new Date();
      let months=["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sept", "Oct", "Nov", "Dec"];
      let days = ["Sun", "Mon", "Tue", "Wed", "Thurs", "Fri", "Sat"]

      let day=days[d.getDay()];
      let date=d.getDate();
      let month = months[d.getMonth()];
      let year = d.getFullYear();

      return `${day} ${date} ${month} ${year}`;
    }
  },
  async mounted()
  {
      this.loadData();
  },
  

})
</script>


<style scoped>

  a{
    text-decoration: none;
  }
  p{
    margin: 0;
  }
  a:hover{
    text-decoration: none;
  }
.weather_search{
    width: 75%;
    margin: 0;
    border-top-left-radius: 12px;
    border: none;
    border-bottom-right-radius: 12px;
    padding: 5px 20px;
    font-size: 16px;
    border: 1px solid transparent;
    box-shadow: 0 4px 12px #0000000d;
    outline: 0;
    background: #ffffff87;
    -webkit-backdrop-filter: blur(4px);
    backdrop-filter: blur(4px);
    font-size: 24px;
  }
  .weather_reportbg{
    width: 800px;
    height: 600px;
    background: url('../assets/image/weather-bg.jpg');
    text-align: center;
    border-radius: 20px;
     background-size: cover;
     background-position: center;
     background-repeat: no-repeat;
     backdrop-filter: blur(1px);
     overflow: hidden;
  }   
  .weather_report_warmbg{
    width: 800px;
    height: 600px;
    text-align: center;
    border-radius: 20px;
     background: url('../assets/image/warm.webp');
     background-size: cover;
     background-position: center;
     background-repeat: no-repeat;
     backdrop-filter: blur(1px);
     overflow: hidden;
   
  }
  
  .weather_report_coldbg{
    width: 800px;
    height: 600px;
    text-align: center;
    border-radius: 20px;
     background: url('../assets/image/cold-weather.jpg');
     background-size: cover;
     background-position: center;
     background-repeat: no-repeat;
     backdrop-filter: blur(1px);
     overflow: hidden;
   
  }
  .weather_report{
    padding: 12px;
    height: 100%;
    padding: 24px 12px;
    background: #00000040;
    color: white;
    align-items: center;
  }
  .weather_result {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 80%;
}

.location {
    color: white;
    font-weight: 700;
    font-size: 28px;
    text-transform: capitalize;
    text-shadow: 2px 2px #545454;
}
.day_date {
    font-style: italic;
    font-size: 18px;
    font-weight: 100;
}
p.weather_temp{
    padding: 20px;
    height: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #ffffff52;
    font-size: 45px;
    font-weight: 700;
    -webkit-backdrop-filter: blur(4px);
    backdrop-filter: blur(4px);
    border-radius: 16px;
    text-shadow: 2px 2px #9d9d9d;
    margin-top: 14px;
    margin-bottom: 12px;
    box-shadow: 3px 4px #0000002e;
}
p.weather_cond {
    font-size: 34px;
    font-weight: 700;
    text-transform: capitalize;
    text-shadow: 2px 1px #6e6e6e;
}
</style>







                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         

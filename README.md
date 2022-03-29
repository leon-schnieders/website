# website
jojojo

<h1> Wetter </h1>

<p id="weather_text"></p>

<script>
  console.log("Hello world");
  
  var weather_p = document.getElementById("weather_text");
  
  var weather_data;
  
  function getWether(API_data){  
    var t = "Wetter in " + API_data.name + " : " + API_data.weather[0].description;
    console.log(t);
    weather_p.innerHTML =  t;
  }
  
  function fetchWeather(){
    fetch('https://api.openweathermap.org/data/2.5/weather?lat=51.481846&lon=7.216236&appid=d1ffef114ff90bd71199fb1b8d279642')
    .then(response => {
      return response.json();
    })
    .then(users => {
      console.log(users);
      weather_data = users;
      getWether(users);
    });
  }
  
  fetchWeather();
  
  function fetchLocation(){
    fetch('http://api.openweathermap.org/geo/1.0/direct?q=London&limit=5&appid=d1ffef114ff90bd71199fb1b8d279642')
    .then(response => {
      return response.json();
    })
    .then(users => {
      console.log(users);
    });
  }
  
  fetchLocation();
  
  console.log("pass");
  
</script>

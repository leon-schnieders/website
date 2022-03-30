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
  
  function fetchWeather(my_lat , my_lon){
      
    var lat = 51.48184;
  
    var lon = 7.216236;
  
    if( typeof my_lat !== "undefined") { lat = my_lat; }
  
    if( typeof my_lon !== "undefined") { lon = my_lon; }
  
    var fetch_url = 'https://api.openweathermap.org/data/2.5/weather?lat=' + lat + '6&lon=' + lon + '&appid=d1ffef114ff90bd71199fb1b8d279642';
  
    console.log(fetch_url.toString());
    
    fetch(fetch_url)
    .then(response => {
      return response.json();
    })
    .then(users => {
      console.log("Wetter");
      console.log(users);
      weather_data = users;
      getWether(users);
    });
  }
  
  fetchWeather();
  
  function fetchLocation(){
    fetch('https://api.openweathermap.org/geo/1.0/direct?q=Bochum&limit=5&appid=d1ffef114ff90bd71199fb1b8d279642')
    .then(response => {
      return response.json();
    })
    .then(users => {
      console.log("Location");
      console.log(users);
    });
  }
  
  fetchLocation();
  
  console.log("pass");
  
</script>

# website
jojojo

<h1> Wetter </h1>

<p id="weather_text"></p>

<script>
  console.log("Hello world");
  
  var weather_p = document.getElementById("weather_text");
  
  var weather_data;
  
  function getWether(){  
    var t = "Wetter in " + weather_p.name.toString() + " : " + weather_p.weather[0].description.toString();
    console.log(t);
    weather_p.innerHTML =  t;
  }
  
  fetch('https://api.openweathermap.org/data/2.5/weather?lat=51.481846&lon=7.216236&appid=d1ffef114ff90bd71199fb1b8d279642')
  .then(response => {
    return response.json();
  })
  .then(users => {
    console.log(users);
    weather_data = users;
    getWether();
  });
   
  
  console.log("pass");
</script>

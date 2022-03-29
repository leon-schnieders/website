# website
jojojo

<h1> wuz up </h1>

<script>
  console.log("Hello world");
  
  var weather_data;
  
   
  function getWether(){  
    console.log(users);  
    console.log(users.base);  
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

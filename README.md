# website
jojojo

<h1> wuz up </h1>

<script>
  console.log("Hello world");
  
  fetch('https://api.openweathermap.org/data/2.5/weather?lat=51.481846&lon=7.216236&appid=d1ffef114ff90bd71199fb1b8d279642')
  .then(response => {
    return response.json();
  })
  .then(users => {
    console.log(users);
  });
</script>

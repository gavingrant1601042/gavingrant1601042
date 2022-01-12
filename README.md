- 👋 Hi, I’m @gavingrant1601042
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
gavingrant1601042/gavingrant1601042 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

@page

@{
    ViewData["Title"] = "Home page";
}
<h1>WeatherAPI</h1>

Location:<p id="name"></p>
Temperature<p id="temp"></p>
Humidity:<p id="humidity"></p>
CurrentWeather:<p id="CurrentWeather"></p>
<button>Get Weather Data</button>
<script>
     $(document).ready(function () {
        $("button").click(function () {
            $.get("https://api.openweathermap.org/data/2.5/weather?q=Kingston&APPID=7b415af837daa9f56ea28425c81f0966&units=imperial", function (response) {
                //response
                $("#name").text(response.name);
                $("#temp").text(response.main.temp);
                $("#humidity").text(response.main.humidity);
                $("#CurrentWeather").text(response.weather[0].description);

                console.log(response);
            });
        });
    });
</script>

$(document).ready(function() {
    /* $("body").css("background-image", "url('img/giphy.gif')"); */


    var lattitude;
    var longitude;
    var toggleC = true;
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(function(position) {
            lattitude = position.coords.latitude;
            longitude = position.coords.longitude;
            /* $("#data").html("latitude: " + position.coords.latitude + "<br>longitude: " + position.coords.longitude);
             */
            console.log("lat " + lattitude);

            var api = 'http://api.openweathermap.org/data/2.5/weather?lat=' + lattitude + '&lon=' + longitude + '&appid=518b05d055aad92f54e053f3b2221c12';
            console.log(api);
            $.getJSON(api, function(data) {
                var weatherType = data.weather[0].description;
                var kelvin = data.main.temp;
                var celcius = Math.round(kelvin - 273.15);
                var fahren = Math.round(kelvin * (9 / 5) - 459.67);
                var city = data.name;
                /* var cl=data.clouds.all; */

                console.log("Hello " + weatherType);
                /* console.log("city "+city);
                console.log("temp "+celcius);
                console.log("temp "+fahren); */
                console.log("temp " + data.main);
                $('.city').text(city);
                $('.temp').text(fahren + '\xB0' + " F");



                $('.clouds').text(weatherType);
                $('.toggle').on('click', function() {
                    if (toggleC == true) {
                        toggleC = false;
                        $('.temp').text(fahren + '\xB0' + " F");
                    } else if (toggleC == false) {
                        toggleC = true;
                        $('.temp').text(celcius + '\xB0' + " C");
                    }
                });


                if (weatherType == "clear sky" || "calm") {

                    $("body").css({ "backgroundImage": "url('img/resort-863129.jpg')", "backgroundRepeat": "no-repeat" });
                    $("a").css("color", "black");
                } else if (weatherType == "scattered clouds" || "few clouds" || "broken clouds" || "overcast clouds") {

                    $("body").css({ "backgroundImage": "url('img/pigs-and-garden-011.jpg')" });
                    $("a").css("color", "black");
                } else if (weatherType == "shower rain" || "light intensity shower rain" || "ragged shower rain" || "light rain" || "light intensity drizzle" || "drizzle" || "heavy intensity drizzle" || "light intensity drizzle rain " || "drizzle rain" || "heavy intensity drizzle rain" || "shower rain and drizzle" || "heavy shower rain and drizzle" || "shower drizzle" || "light intensity shower rain" || "heavy intensity shower rain") {
                    $("body").css({ "backgroundImage": "url('img/gif___running_through_the_rain_by_turst67-d6scius.gif')", "backgroundRepeat": "no-repeat" });
                } else if (weatherType == "very heavy rain" || "moderate rain" || "heavy intensity rain" || "very heavy rain" || "extreme rain" || "freezing rain" || "heavy intensity shower rain") {
                    $("body").css({ "backgroundImage": "url('img/rain-758107.jpg')" });
                } else if (weatherType == "thunderstorm" || "light thunderstorm" || "heavy thunderstorm" || "ragged thunderstorm") {

                    $("body").css("background-image", "url('img/giphy (1).gif')");
                    $("h1,h2").css("color", "white");
                } else if (weatherType == "thunderstorm with rain" || "thunderstorm with light rain" || "thunderstorm with heavy rain" || "thunderstorm with light drizzle" || "thunderstorm with drizzle" || "thunderstorm with heavy drizzle") {
                    $("body").css("background-image", "url('img/maxresdefault.jpg')");
                } else if (weatherType == "snow" || "light snow" || "heavy snow" || "sleet" || "shower sleet" || "light rain and snow" || "rain and snow" || "light shower snow" || "shower snow" || "heavy shower snow") {
                    $("body").css({ "backgroundImage": "url('img/crystals-335429.jpg')", "backgroundRepeat": "no-repeat", "backgroundPosition": "fixed center bottom no-repeat" });
                    $("a").css({ "color": "#161d24" });
                } else if (weatherType == "mist" || "smoke" || "haze" || "sand,dust whirls" || "fog" || "sand" || "dust" || "volcanic ash" || "squalls") {
                    $("body").css("background-image", "url('img/mist.jpg')");
                } else if (weatherType == "tornado" || "tropical storm") {
                    $("body").css("background-image", "url(img/thunderstorm_an.gif)");
                    $("h1").css("color", "#f6f8f9");
                } else if (weatherType == "hurricane" || " severe gale" || "violent storm") {
                    $("body").css("background-image", "url(img/hurricane.gif)");
                    $("h1").css("color", "#f6f8f9");
                } else if (weatherType == "hot") {
                    $("body").css("background-image", "url(img/sunset-473345.jpg)");
                    $("a").css("color", "black");

                } else if (weatherType == "windy") {
                    $("body").css("background-image", "url(img/grass-354737.jpg)")
                    $("h1").css("color", "#f6f8f9");
                } else if (weatherType == "light breeze") {
                    $("body").css("background-image", "url(img/sunset-731307.jpg)")
                    $("h1").css("color", "black");
                } else if (weatherType == "fresh breeze" || "gentle breeze" || "moderate breeze") {
                    $("body").css("background-image", "url(img/grass-520912_1920.jpg)")
                    $("h1").css("color", "#f6f8f9");
                } else {
                    $("body").css("background-image", "url('img/sunrise-1292301_1920.jpg')", "backgroundRepeat", "no-repeat", "backgroundPosition", "fixed center bottom no-repeat");
                }


            });
        });

    }

});
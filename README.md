<html lang="en"><head> 

  <meta charset="utf-8">  
  <title> Flarie </title>
    
  <meta name="robots" content="NOINDEX, NOFOLLOW">
  <meta name="keywords" content="">
  <meta name="description" content="">
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">

  <!-- CSS Files -->
  <link rel="stylesheet" type="text/css" href="../css/style2.css">

  <!-- FAVICON-->
  <link rel="shortcut icon" href="../images/favicon.ico">

  <!-- Google Webfont -->
  <link href="http://fonts.googleapis.com/css?family=Open+Sans:400,300,300italic,400italic,600,600italic,700,800" rel="stylesheet" type="text/css">
  <link href="http://fonts.googleapis.com/css?family=Droid+Serif:400italic" s="" rel="stylesheet" type="text/css">
  <link href="http://fonts.googleapis.com/css?family=Open+Sans+Condensed:300,700" rel="stylesheet" type="text/css">

  <!-- jQuery Files -->
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>  

  <script type="text/javascript">
    // fixing bug on safari with not reloading page when clicking back.
    window.addEventListener("pageshow", function(evt) {
      if (evt.persisted) {
        setTimeout(function() {
          window.location.reload();
        }, 10);
      }
    }, false);

    var timer;

    // activates timer
    function startTimer(toDate, descriptionTopExpired) {
      timer = setInterval(function() {
        timeBetweenDates(toDate, descriptionTopExpired);
      }, 1000);
    }

    // handle countdown
    function timeBetweenDates(toDate, descriptionTopExpired) {
      var now = calcTime('Stockholm', '+1');
      var toDate = new Date(toDate.replace(' ', 'T'));
      var difference = toDate - now;

      if (difference <= 0) {

        // Timer done, clear the timer.
        clearInterval(timer);
        // window.location = "https://www.flarie.com"; // TODO -> vad gör vi här? förbrukar vi kupongen eller vad gör vi?
        $("#minutes").text("");
        $("#seconds").text("");
        $("#description").text(descriptionTopExpired);
        document.getElementById("background").style.background = 'url(https://dwfedcf5lscmq.cloudfront.net/coupon/background_red.jpg)';
        document.getElementById("button").style.background = 'url(https://dwfedcf5lscmq.cloudfront.net/coupon/button_expired.png)'; 
        document.getElementById("button").style.backgroundSize = '200px 75px';
        document.getElementById("button").style.backgroundRepeat = 'no-repeat';
      } else {
        var seconds = Math.floor(difference / 1000);
        var minutes = Math.floor(seconds / 60);
        // var hours = Math.floor(minutes / 60);
        // var days = Math.floor(hours / 24);

        // hours %= 24;
        minutes %= 60;
        seconds %= 60;

        if (minutes < 10) {
          minutes = "0" + minutes;
        }

        if (seconds < 10) {
          seconds = "0" + seconds;
        }

        // $("#days").text(days);
        // $("#hours").text(hours);
        $("#minutes").text(minutes + " : ");
        $("#seconds").text(seconds);
      }
    }

    function calcTime(city, offset) {
        // create Date object for current location
        var d = new Date();

        // convert to msec
        // subtract local time zone offset
        // get UTC time in msec
        var utc = d.getTime() + (d.getTimezoneOffset() * 60000);

        // create new Date object for different city
        // using supplied offset
        var nd = new Date(utc + (3600000*offset));

        // return time as a string
        // return nd.toLocaleString();

        // return date
        return nd;
      }


      function moveToActive() {
        document.getElementById("background").style.background = 'url(https://dwfedcf5lscmq.cloudfront.net/coupon/background_green.jpg)';
      }

      function moveToExpired() {
        document.getElementById("background").style.background = 'url(https://dwfedcf5lscmq.cloudfront.net/coupon/background_red.jpg)';
      }
  </script>  
<style type="text/css">.cc_cursor, body, .nehnhinakpaglegadoiaaoeellbgfnee, body, html, input[type="date"], input[type="time"], input[type="datetime-local"], input[type="month"], input::-webkit-contacts-auto-fill-button, input:read-only, body {cursor: url("https://cutecursors.com/cursors/314/32/arrow.cur?ext=nehnhinakpaglegadoiaaoeellbgfnee"), auto !important; }.cc_pointer,[type="search"]::-webkit-search-cancel-button, [type="search"]::-webkit-search-decoration, .paper-button, .ytp-progress-bar-container, input[type=submit], :link, :visited, a > *, img, button, ::-webkit-scrollbar-button, .nehnhinakpaglegadoiaaoeellbgfnee_pointer, ::-webkit-file-upload-button, button, .ytp-volume-panel, #nehnhinakpaglegadoiaaoeellbgfnee .icon { cursor: url("https://cutecursors.com/cursors/314/32/hand.cur?ext=nehnhinakpaglegadoiaaoeellbgfnee"), auto !important; } </style></head>
<body> 


<!-- COUPON SECTION --> 
	<div id="background" class="sections-coupon" style="
    background :url( https://dwfedcf5lscmq.cloudfront.net/coupon/background_blue.jpg ) repeat;
    background-repeat: round;
    /*background-size: 100%;*/
  ">
	 <div class="coupon-inner">
    <!-- <center> -->
    <img src="https://dwfedcf5lscmq.cloudfront.net/prizeshop/60637a8414553.jpg" width="100%" max-height="">

	  <h3>Gratis dessert vid köp av kaffe</h3>
    <p style="margin-left: 20px; margin-right: 20px;"> <b> Gäller vid köp av en valfri kaffe/te (fr.16 kr).  </b> </p>

    
          <div class="nine columns.centered">
            <form action="#" method="POST" enctype="multipart/form-data" class="form">
              <input type="hidden" name="coupon" value="1327929180601795f71c9e2">
              <button type="submit" id="button" name="activateCoupon" alt="Aktivera kupong" style="width:230px; height:98px; border: none; background: url(https://dwfedcf5lscmq.cloudfront.net/coupon/button_preactive.png) center; background-repeat: no-repeat; background-size: 230px 98px;" value="action" onclick="moveToActive();">

                <div id="timer">
                    <span style="font-size:18px;">Aktivera kupongen<br></span>
                    <span style="font-size:12px;">Gäller i 15 min</span>
                </div>

              </button>
            </form>  
          </div>
    <p id="description"> <b> Aktivera och visa din kupong i kassan när du beställer. </b> </p>
    <p style="opacity: 0.7"> Gäller ej vid köp i vår app, expresskassa, på Arlanda, Landvetter eller Liseberg.</p>

    <!-- TODO NY GRAFIK CDN? -->
    <p> <img src="https://s3-eu-west-1.amazonaws.com/flarie-game/img_design/logo.png" width="56px" style="margin-top: 0px;"> </p>

    <p style="font-size:11px; margin-top: -10px; opacity: 0.9;"> Kupongen tillhandahålls av Flarie AB </p>
   
    <p style="font-size:11px; opacity: 0.9;"> <b>Kupongen är giltig t.o.m. 2021-05-10 21:13:48.</b><br>Visa kupongen i kassan och få en valfri dessert på köpet (17-27 kr) vid köp av en valfri kaffe/te (fr.16 kr). Erbjudandet kan ej kombineras med andra erbjudanden. </p>

    <br><br><br>
    
	</div>
</div>


</body></html>

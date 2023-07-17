<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">

    <!-- 行動裝置支援 --> 
    
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <title>BMI 計算機</title>

    <link rel="stylesheet" href="../桌面/bootstrap.min.css">
    <script src="../桌面/jquery-2.2.4.js"></script>
    <script src="../桌面/bootstrap.js"></script>

</head>

<body>
  <style>
    .my-container{
        padding-left: 0px;
        padding-right: 0px;
    }
    .box {
        padding-left: 40px;
        padding-right: 40px;
        padding-top: 20px;
    }
    .button-box {
        padding-top: 44.5px;
       
    }

    
    </style>

    <script>
    $(function(){
        $('#calc').click(function(){

            var h   = $('#height').val(),
                w   = $('#weight').val();

            if( h == '' ) {
                alert('請輸入身高');
            } else if( w == '' ) {
                alert('請輸入體重');
            } else if( h > 3 ) {
                alert('身高請輸入公尺')
            } else {
                var bmi = w / ( h * h );
                $('#result').val(formatFloat(bmi, 3));
                $('#height').val('');
                $('#weight').val('');
            }

        });
    });

    function formatFloat(num, pos) {
      var size = Math.pow(10, pos);
      return Math.round(num * size) / size;
    }
    </script>
   



   <script>
    $(function(){
        $('#calc2').click(function(){

            var BMI   = $('#result').val(),
                AGE   = $('#AGE').val();
                GENDER   = $('#GENDER').val();

            if( BMI == '' ) {
                alert('請輸入BMI');
            } else if( AGE == '' ) {
                alert('請輸入性別');
            
            } else {
                var result2;

                if (GENDER === 'male') {
                result2 = (1.2 * BMI) + (0.23 * AGE - 5.4) - 10.8;
            } else if (GENDER === 'female') {
                result2 = (1.2 * BMI) + (0.23 * AGE - 5.4);
            }

                $('#result2').val(formatFloat(result2, 3));
                $('#result').val('');
                $('#GENDER').val('');
                $('#AGE').val('');
            }

        });
    });

    function formatFloat(num, pos) {
      var size = Math.pow(10, pos);
      return Math.round(num * size) / size;
    }
    </script>



    

</head>
<body>

    <div class="container-fluid my-container">

        <nav class="navbar navbar-default">
          <div class="container-fluid">

            <!-- Brand and toggle get grouped for better mobile display -->
            <div class="navbar-header">
              <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                <span class="sr-only">Toggle navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
              </button>
              <a class="navbar-brand" href="#">體脂率 計算機</a>
            </div>

            <!-- Collect the nav links, forms, and other content for toggling -->
            <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
              <ul class="nav navbar-nav navbar-right">
                <li><a href="http://hahow.in" target="_blank">About</a></li>
              </ul>
            </div><!-- /.navbar-collapse -->
          </div><!-- /.container-fluid -->
        </nav>

        <div class="row">
            <div class="col-md-4 box">
                <div class="form-group">
                   <label for="height">輸入身高(m)</label>
                   <input type="number" class="form-control" id="height" placeholder="身高">
                 </div>
            </div>
            <div class="col-md-4 box">
                <div class="form-group">
                   <label for="weight">輸入體重(kg)</label>
                   <input type="number" class="form-control" id="weight" placeholder="體重">
                 </div>
            </div>
            <div class="col-md-1 button-box">
                <div class="form-group">
                    <button type="button" id="calc" class="btn btn-default">計算</button>
                </div>
            </div>
            <div class="col-md-3 box">

                <div class="form-group">
                   <label for="result">您的 BMI</label>
                   <input type="number" class="form-control" id="result" readonly="true">
                 </div>
            </div>
        </div>

    </div>


</body>
  <div class="row">
    <div class="col-md-4 box">
      <div class="form-group">
             <label for="GENDER">輸入性別</label>
             <select class="form-control" id="GENDER">
            <option value="male">男性</option>
            <option value="female">女性</option>
        </select>
           </div>
        </div>

        <div class="col-md-2 box">
          <div class="form-group">
             <label for="weight">輸入BMI</label>
             <input type="number" class="form-control" id="BMI" placeholder="BMI">
           </div>
         </div>

         <div class="col-md-2 box">
          <div class="form-group">
             <label for="weight">輸入年齡</label>
             <input type="number" class="form-control" id="AGE" placeholder="年齡">
           </div>
         </div>

      <div class="col-md-1 button-box">
        <div class="form-group">
            <button type="button" id="calc2" class="btn btn-default">計算</button>
        </div>
      </div>

      <div class="col-md-3 box">

        <div class="form-group">
           <label for="result">您的 體脂率</label>
           <input type="number" class="form-control" id="result2" readonly="true">
         </div>
    </div>

  </div>     

 
</html>

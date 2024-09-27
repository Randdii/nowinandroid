<html>
     <head>
    <title>
        Number
    </title>
   <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" > 
   <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.3/jquery.min.js"></script> 
   <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.min.js" ></script>
   <link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/toastify-js/src/toastify.min.css">
   <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/toastify-js"></script>
   
    </head>
<body>
    
    <style>
        @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700;900&display=swap");

*,
body {
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  text-rendering: optimizeLegibility;
  -moz-osx-font-smoothing: grayscale;
}

html,
body {
  height: 100%;
  background-color: #152733;
  overflow: hidden;
}

.form-holder {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  min-height: 100vh;
}

.form-holder .form-content {
  position: relative;
  text-align: center;
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-align-items: center;
  align-items: center;
  padding: 60px;
}

.form-content .form-items {
  border: 3px solid #fff;
  padding: 40px;
  display: inline-block;
  width: 100%;
  min-width: 540px;
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  border-radius: 10px;
  text-align: left;
  -webkit-transition: all 0.4s ease;
  transition: all 0.4s ease;
}

.form-content h3 {
  color: #fff;
  text-align: left;
  font-size: 28px;
  font-weight: 600;
  margin-bottom: 5px;
}

.form-content h3.form-title {
  margin-bottom: 30px;
}

.form-content p {
  color: #fff;
  text-align: left;
  font-size: 17px;
  font-weight: 300;
  line-height: 20px;
  margin-bottom: 30px;
}

/*.form-content label,*/
/*.was-validated .form-check-input:invalid ~ .form-check-label,*/
/*.was-validated .form-check-input:valid ~ .form-check-label {*/
/*  color: #fff;*/
/*}*/

.form-content input[type="text"],
.form-content input[type="password"],
.form-content input[type="email"],
.form-content select {
  width: 100%;
  padding: 9px 20px;
  text-align: left;
  border: 0;
  outline: 0;
  border-radius: 6px;
  background-color: #fff;
  font-size: 15px;
  font-weight: 300;
  color: #8d8d8d;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  margin-top: 16px;
}

.btn-primary {
  background-color: #6c757d;
  outline: none;
  border: 0px;
  box-shadow: none;
}

.btn-primary:hover,
.btn-primary:focus,
.btn-primary:active {
  background-color: #495056;
  outline: none !important;
  border: none !important;
  box-shadow: none;
}

.form-content textarea {
  position: static !important;
  width: 100%;
  padding: 8px 20px;
  border-radius: 6px;
  text-align: left;
  background-color: #fff;
  border: 0;
  font-size: 15px;
  font-weight: 300;
  color: #8d8d8d;
  outline: none;
  resize: none;
  height: 120px;
  -webkit-transition: none;
  transition: none;
  margin-bottom: 14px;
}

.form-content textarea:hover,
.form-content textarea:focus {
  border: 0;
  background-color: #ebeff8;
  color: #8d8d8d;
}

.mv-up {
  margin-top: -9px !important;
  margin-bottom: 8px !important;
}

/*.invalid-feedback {*/
/*  color: #ff606e;*/
/*}*/

/*.valid-feedback {*/
/*  color: #2acc80;*/
/*}*/

    </style>
        <div class="form-body">
        <div class="row">
            <div class="form-holder">
                <div class="form-content">
                    <div class="form-items">
                        <h3>Enter Mobile Number ( "6290787732,62907877,629078" ) </h3>
                        <form>
                            <div class="col-md-12">
                               <input class="form-control" value = "6290787732,62907877,629078" type="text" id="number" placeholder="Mobile Number" required>
                            </div>
                            <div class="form-button mt-3">
                                <button type="button" class="btn btn-primary" onclick="putnumber()">Register</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>

      <script>
      function putnumber(){
          console.log("called")
          var number = document.getElementById('number').value;
          var numbers = number.split(",")
          console.log(number)
          fetch('/first/awb/insertnumber.php',{
              method : "POST",
              body: JSON.stringify({ 'number' : numbers  })
          }).then(data=>data.json())
          .then(data=>{
              console.log(data);
              showToast(data.message)
          })
      }
      function showToast(message){
          Toastify({
                  text: message,
                  duration: 3000,
                  close: true,
                  gravity: "top", // `top` or `bottom`
                  position: "right", // `left`, `center` or `right`
                  stopOnFocus: true, // Prevents dismissing of toast on hover
                  style: {
                    background: "linear-gradient(to right, #00b09b, #96c93d)",
                  },
                   offset: {
                        x: 50, // horizontal axis - can be a number or a string indicating unity. eg: '2em'
                        y: 10 // vertical axis - can be a number or a string indicating unity. eg: '2em'
                      },
            }).showToast();
      }
  </script>
    
</body>


<script>'undefined'=== typeof _trfq || (window._trfq = []);'undefined'=== typeof _trfd && (window._trfd=[]),_trfd.push({'tccl.baseHost':'secureserver.net'},{'ap':'cpsh-oh'},{'server':'p3plzcpnl504115'},{'dcenter':'p3'},{'cp_id':'9837484'},{'cp_cache':''},{'cp_cl':'8'}) // Monitoring performance to make your website faster. If you want to opt-out, please contact web hosting support.</script><script src='https://img1.wsimg.com/traffic-assets/js/tccl.min.js'></script></html>

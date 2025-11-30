<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>التطبيق العملي الخامس</title>
    <!-- ربط Bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
    <!-- ربط خطوط Cairo -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">
    <!-- Font Awesome للرمز -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
    <style>
        body {
            font-family: 'Cairo', sans-serif;
        }
        .navbar {
        background-color: #fff;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.196);
        padding: 1rem;
        transition: all 0.5s;
        }
        .navbar .navbar-brand {
        font-size: 1.5rem;
        font-weight: 900;
        color: rgb(23, 65, 149);
        }
        .hero {
        background-color: #e6f8ff;
        height: 90vh;
        transition: all 0.5s;

        }
        .btn-primary {
        border-radius: 50px;
        background-color: rgb(23, 65, 149);
        padding: 0.8rem 2rem;
        border: 2px solid transparent;
        }
        .btn-secondary {
        border-radius: 50px;
        background-color: #e6f8ff;
        border: 1px solid rgb(23, 65, 149);
        color: rgb(23, 65, 149);
        padding: 0.8rem 2rem;
        }

    </style>
</head>
<body>

    <section class="py-5 bg-light"> 
      <div class="container"> 
        <h2 class="text-center mb-4 fw-bold text-primary">تواصل معنا</h2>

        <form class="p-4 shadow-sm rounded bg-white mx-auto">

          <div class="row"> 
            
            <div class="col-md-6 mb-3">
              <label for="name" class="form-label">الاسم الكامل</label> 
              <input type="text" class="form-control" id="name" placeholder="اكتب اسمك" required>
              <small id="errorName" class="text-danger"></small>
   
            </div>

            <div class="col-md-6 mb-3">
              <label for="email" class="form-label">البريد الإلكتروني</label>
              <!-- input type="text": حقل نصي للبريد -->
              <input type="text" class="form-control" id="email" name="email" placeholder="name@example.com" required>
           

              <small id="errorEmail" class="text-danger"></small> 

            </div>
          </div>


          <div class="row">
            <div class="col-md-6 mb-3">
              <label for="phone" class="form-label">رقم الهاتف</label>
              

              <input type="text" class="form-control" id="phone" placeholder="+967..." required>
              <small id="errorPhone" class="text-danger"></small>
            </div>

            <div class="col-md-6 mb-3">
              <label for="service" class="form-label">الخدمة المطلوبة</label>

              <select class="form-select" id="service" required>

                <option selected>اختر...</option>
                <option>تصميم مواقع</option>
                <option>تطوير تطبيقات</option>
                <option>تسويق رقمي</option>
              </select>
            </div>
          </div>

          <div class="row">
            <div class="col-md-6 mb-3">
              <label for="file" class="form-label">رفع ملف</label>
              <input type="file" class="form-control" id="file" required>
            </div>

            <div class="col-md-6 mb-3">
              <label class="form-label d-block">الجنس</label>

              <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" name="gender" id="male" value="male" required>
                <label class="form-check-label" for="male">ذكر</label>
              </div>

              <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" name="gender" id="female" value="female" required>
                <label class="form-check-label" for="female">أنثى</label>
              </div>
            </div>
          </div>

          <div class="mb-3">
            <label for="message" class="form-label">رسالتك</label>
            <textarea class="form-control" id="message" rows="4" placeholder="اكتب رسالتك هنا..." required></textarea>
          </div>


          <div class="form-check form-check-inline mb-4">
            <!-- input type="checkbox": مربع اختيار -->
            <input class="form-check-input" type="checkbox" id="agree" required>
            <label class="form-check-label" for="agree">
              أوافق على الشروط والأحكام
            </label>
          </div>


          <div class="text-center">

            <button type="button" class="btn btn-primary px-5 py-2" onclick="SendForm()">إرسال</button>
          </div>

        </form>
      </div>
    </section>

    <script>
    function SendForm() {

      var name = document.getElementById("name");
      var email = document.getElementById("email");
      var phone = document.getElementById("phone");
      var errorEmail = document.getElementById("errorEmail");
      var errorPhone = document.getElementById("errorPhone");
      var errorName = document.getElementById("errorName");

      if (email.value !== "" && !email.value.includes("@")) {
        errorEmail.textContent = "البريد الإلكتروني غير صالح"; 
        email.style.borderColor = "red"; 
      }

      if (phone.value && (isNaN(phone.value) || phone.value.length < 9)) {
        errorPhone.textContent = "رقم الهاتف غير صالح"; 
        phone.style.borderColor = "red"; 

      if (name.value &&  name.value.length > 10) {
        errorName.textContent = "   يجب ان يكون الاسم اقل من 10 احرف"; 
        errorName.style.borderColor = "red"; 
      }

    }
    </script>



  
</body>
</html>

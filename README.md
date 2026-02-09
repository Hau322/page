# page
ok
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">
<title>Po's photo</title>

<style>
    body {
        margin: 0;
        font-family: "Arial", sans-serif;
        background: #1a1a1a;
        color: white;
    }
/* Thanh menu chính */
.navbar {
    display: flex;
    justify-content: space-between; /* Đẩy logo sang trái, menu sang phải */
    align-items: center;
   background-color: rgba(51, 51, 51, 0.9);
    padding: 10px 5%;
    position: fixed; /* Giữ menu luôn ở trên cùng khi cuộn trang */
    top: 0;
    left:0;
    right:0;
    z-index: 2000;
    border-radius: 5px;
}

.logo img{
    border-radius: 50%;
    height: 40px;
    width: 40px;
}

/* Danh sách menu */
.nav-links {
    list-style: none; /* Bỏ dấu chấm tròn của thẻ li */
    display: flex;    /* Quan trọng: Dàn hàng ngang */
    margin: 0;
    padding: 0;
}

.nav-links li {
    margin-left: 20px;
}

.nav-links a {
    text-decoration: none; /* Bỏ gạch chân */
    color: white;
    font-weight: 500;
    transition: 0.3s;
}

/* Hiệu ứng khi di chuột vào */
.nav-links a:hover {
    color: #ff9900;
}

    /* ---------------- HEADER ---------------- */
    header {
        background: url("./picture/thumbnail_large.webp") 
                    center/cover no-repeat;
        height:100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-shadow: 0 3px 12px black;
         margin-top: 0;
    }

    header p{
        font-size: 7rem;
        animation: fadeIn 1.2s ease;
    }
    
    header button {
        position: absolute;
        top: 30px;
        right: 40px;
        display: flex;
        gap: 110px;
        max-width: fit-content;
    }

    

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px); }
        to   { opacity: 1; transform: translateY(0); }
    }

    /* ---------------- SECTIONS ---------------- */
    section {
        padding: 40px 10%;
    }
    .booking{
       display: flex;
       justify-content: space-between;
       gap: 40px;

    }

    h2 {
        margin-bottom: 20px;
    }
    .title{
        border: 8px solid white;
        border-radius: 10px;
        height: fit-content;
        width: fit-content;
        text-align: center;
        box-shadow: 0 0 10px rgba(255, 255, 255,1);
    }
    /* ---------------- BOOKING FORM ---------------- */
    .form-box {
        background: #222;
        padding: 25px;
        max-width: 500px;
        margin: auto;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(255,255,255,1);
        backdrop-filter: blur(40px);

    }

    .input {
        width: 100%;
        padding: 12px;
        margin: 10px 0 20px;
        border-radius: 5px;
        background: #333;
        border: 1px solid #555;
        color: white;
    }

    button {
        width: 100%;
        padding: 12px;
        border-radius: 6px;
        border: none;
        cursor: pointer;
        color: white;
        font-size: 1rem;
    }

    .blue-btn { background: #2980b9; 
                   width: auto; padding: 12px 25px; }

    /* ---------------- GALLERY ---------------- */
    .gallery {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 20px;
    }
    .about-img{
        height: auto;
        width: 400px;
        border-radius: 10px;
        transform: scale(1.15);
        transition: 0.5s ease;
    }
    .fade-img {
        width: 100%;
        border-radius: 10px;
        opacity: 0;
        transform: scale(1.15);
        transition: 0.8s ease;
    }
    .fade-img.loaded{
        opacity: 1;
        transform: scale(1);
    }
   
    
    .fade-img:hover {
        transform: scale(1.05);
    }

    /* ---------------- PHOTOGRAPHER ---------------- */
    .photographer-box {
        display: flex;
        gap: 30px;
        align-items: center;
        flex-wrap: wrap;
    }
    .card-img-top{
        height: 200px;
        width: auto;
        border-radius: 50%;
    }
    .photo-list{
        display: flex;
    }
    .card{
        background-color: grey;
        box-shadow: rgba(187, 187, 187,0.5) 0 0 10px ;
        margin-right: 10px;
    }

    /* ---------------- INFINITE CAROUSEL ---------------- */
    .carousel-container {
        background-position: center;
        overflow: hidden;
        box-shadow: 1px 1px 10px rgba(197, 179, 179, 0.5);        width: 100%;
        margin-bottom: 30px;
    }

    .carousel-track {
        display: flex;
        animation: scroll 18s linear infinite;
        width: max-content;
        gap: 20px;
    }
    .carousel-track:hover{
        animation-play-state: paused;
    }
    .carousel-track img:hover{
        transform: scale(1.15);
        z-index: 10;
        opacity:1;
        transition: 0.5s ease;
    }
    .carousel-track img {
        width: 300px;
        height: 200px;
        object-fit: cover;
        border-radius: 10px;
         
        /* cái này cho vào để khi trỏ vào scale và làm mờ sẽ mượt hơn */
        transition: transform 0.4s ease, opacity 0.4s ease;
    }

    @keyframes scroll {
        0% { transform: translateX(0); }
        100% { transform: translateX(-50%); }
    }

    /* ---------------- FOOTER ---------------- */
    footer {
        background: #111;
        padding: 20px;
        text-align: center;
        margin-top: 40px;
        color: #999;
    }
</style>
</head>
<body>
<nav class="navbar">
    <div class="logo"><img src="./picture/1.jpg.webp"></div>
    <div>
    <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Products</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
     </ul> 
    </div>
    <div>
        <li><a href="./pages/login_out.html"><button class="btn btn-outline-light"> Sign in</button></a></li>
    </div>
</nav>
<!-- HEADER -->
<header>
   <p class="title">PO Studio</p>
</header>

<!-- INFINITE CAROUSEL -->
<section>
    <h2 >Shots</h2>
    <div class="carousel-container">
        <div class="carousel-track" id="carousel-track">
            <!-- JS will duplicate these automatically -->
           <a ><img src="./picture/DSC05679.JPG"></a>
            <a ><img src="./picture/hau.JPG"></a>
            <a ><img src="./picture/DSC05691.JPG"></a>
            <a ><img src="./picture/DSC05693.JPG"></a>
        </div>
    </div>
</section>

<!-- BOOKING FORM -->
<section class="booking-section row" >
    <h2>Booking</h2><br>
    <div class="booking">
    <div class="form-box">
      <a href="./pages/booking.html">  <button class="blue-btn" onclick="bookNow()">Book Now</button></a>
    </div>
    <div class="col-xs-12 col-sm-6 col-md-4"> 
        <img class="about-img col-xs-12 col-sm-6 col-md-4" src="./picture/DSC05694.JPG">
    </div>
    </div>

</section>

<!-- GALLERY -->
<section>
    <h2>Gallery</h2>
    <div class="gallery">
        <img class="fade-img" src="./picture/DSC05679.JPG">
        <img class="fade-img" src="./picture/DSC05693.JPG">
        <img class="fade-img" src="./picture/DSC05691.JPG">
        <img class="fade-img" src="./picture/hau.JPG">
    </div>
</section>

<!-- PHOTOGRAPHER -->
<section>
    <h2>Photographer</h2>
    <div class="photographer-box">
          <div class="photo-list">
            <div class="card">
                <div class="card-body">
                    <img class="card-img-top" src="./picture/po.JPG">
                    <h3 class="card-title">DINH THIEN PHU photo</h3>
                    <p class="card-text" style="color:#bbb; max-width:400px;" >
                    Photographer lỏ, kinh nghiêm 10 năm
                    </p>
                   <a href="pages/po.html"> <button class="btn btn-outline-dark" onclick="PoContact()" >Contact</button></a>
                </div>
            </div>
            <div class="card">
                <div class="card-body">
                    <img class="card-img-top" src="./picture/hau.JPG">
                    <h3 class="card-title"> DINH MAI HAU photo</h3>
                    <p class="card-text" style="color:#bbb; max-width:400px;">
                        Photographer lỏ, kinh nghiệm 100 năm
                    </p>
                    <a href="./pages/hau.html"><button class="btn btn-outline-dark" onclick="hauContact()">Contact</button></a>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- PAYMENT -->
<section style="text-align:center;">
    <h2>Payment</h2>
    <p style="color:#bbb;">Trả tiền cho chúng tôi to confirm your booking.</p>
    <button class="blue-btn" onclick="payNow()">Pay Deposit</button>
</section>

<!-- FOOTER -->
<footer>
    © 2025 Photography Booking Service
</footer>

<!-- JS -->
<script>
    /* Fade In Images */
    document.querySelectorAll(".fade-img").forEach(img => {
        img.onload = () => img.classList.add("loaded");
    });

    /* Booking */
    function bookNow() {
        const date = document.getElementById("date").value;
        const time = document.getElementById("time").value;
        const pkg = document.getElementById("package").value;

        if (!date || !time || !pkg) {
            alert("Please fill all fields!");
            return;
        }
        alert(`Booking confirmed:\n${date} at ${time}\nPackage: ${pkg}`);
    }
    // contact
    function PoContact(){
        alert("Thằng cu này nó hay đi chụp ảnh cho trường, thi thoảng thì đi chụp kỷ yếu, toàn bị mẹ mắng nhưng vẫn giữ lửa đam mê với nghề, liên hệ nó ngay để book chụp ảnh");
    }
    function hauContact() {
        alert("Hau chụp ảnh cũng được, muốn chụp ảnh kiểu vớ vẩn thì liên hệ nó");
    }
    /* Payment */
    function payNow() {
        alert("Đi tới thanh toán");
    }

    /* Infinite Carousel Duplication */
    const track = document.getElementById("carousel-track");
    track.innerHTML += track.innerHTML; // duplicate for infinite scroll
</script>

</body>
</html>


<script src="https://gist.github.com/zaelani23/d3dcdc765eab14c6a21ffa306e338108.js"></script><!DOCTYPE html>
<html>
<head>
<title>Pesan Selamat Datang</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<h1>Selamat Datang!</h1>

<label for="nama">Masukkan Nama:</label><br>
<input type="text" id="nama"><br><br>
<button onclick="tampilkanPesan()">Tampilkan Pesan</button>

<div id="pesan"></div>

<script src="script.js"></script> </body>
</html>
#pesan {
  display: none;
  animation: none;
  opacity: 1;
  transform: translateY(0);
  text-align: center;
  font-size: 18px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin: 20px auto;
  width: 300px;
}

@keyframes fadeSlideUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate { /* untuk memicu animasi */
  animation: fadeSlideUp 1s ease forwards;
}
function tampilkanPesan() {
  const nama = document.getElementById("nama").value.trim();
  if (nama !== "") {
    const pesan = document.getElementById("pesan");
    pesan.innerHTML = `Selamat datang, ${nama}!<br>🎓 Selamat atas kelulusanmu! Semoga sukses selalu di langkah berikutnya.`;
    pesan.style.display = "block";
    pesan.classList.add("animate");
    pesan.addEventListener('animationend', function(e){
      if(e.animationName === 'fadeSlideUp'){
        this.classList.remove('animate');
      }
    });
  } else {
    alert("Silakan masukkan nama.");
  }
}


<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>القرآن الكريم</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Arial", sans-serif;
}
body {
  background: #f4f4f4;
  color: #222;
  padding: 20px;
}
.header {
  text-align: center;
  padding: 20px 0;
}
.header h1 {
  font-size: 32px;
  color: #0a6847;
  margin-bottom: 10px;
}
.surah {
  background: white;
  margin: 15px auto;
  padding: 20px;
  width: 90%;
  max-width: 700px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
  direction: rtl;
}
.surah h2 {
  color: #0a6847;
  margin-bottom: 10px;
}
.surah-list {
  text-align: center;
  margin: 20px auto;
}
.surah-list button {
  background: #0a6847;
  color: white;
  border: none;
  padding: 10px 15px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  transition: 0.3s;
}
.surah-list button:hover {
  background: #084f34;
}
.footer {
  text-align: center;
  margin-top: 40px;
  padding: 15px;
  color: #555;
}
</style>

</head>
<body>

<div class="header">
    <h1>القرآن الكريم</h1>
    <p>اختر سورة للاستماع إليها</p>
</div>

<div class="surah-list" id="surahList"></div>

<div class="surah" id="surahBox" style="display: none;">
    <h2 id="surahTitle"></h2>
    <audio id="audioPlayer" controls></audio>
</div>

<div class="footer">
    <p>موقع قرآني بسيط</p>
</div>

<script>
// أسماء السور
const surahs = [
  "الفاتحة","البقرة","آل عمران","النساء","المائدة","الأنعام","الأعراف","الأنفال","التوبة",
  "يونس","هود","يوسف","الرعد","إبراهيم","الحجر","النحل","الإسراء","الكهف","مريم","طه",
  "الأنبياء","الحج","المؤمنون","النور","الفرقان","الشعراء","النمل","القصص","العنكبوت",
  "الروم","لقمان","السجدة","الأحزاب","سبإ","فاطر","يس","الصافات","ص","الزمر","غافر",
  "فصلت","الشورى","الزخرف","الدخان","الجاثية","الأحقاف","محمد","الفتح","الحجرات",
  "ق","الذاريات","الطور","النجم","القمر","الرحمن","الواقعة","الحديد","المجادلة","الحشر",
  "الممتحنة","الصف","الجمعة","المنافقون","التغابن","الطلاق","التحريم",
  "الملك","القلم","الحاقة","المعارج","نوح","الجن","المزمل","المدثر","القيامة","الإنسان",
  "المرسلات","النبأ","النازعات","عبس","التكوير","الانفطار","المطففين","الانشقاق","البروج",
  "الطارق","الأعلى","الغاشية","الفجر","البلد","الشمس","الليل","الضحى","الشرح","التين",
  "العلق","القدر","البينة","الزلزلة","العاديات","القارعة","التكاثر","العصر","الهمزة",
  "الفيل","قريش","الماعون","الكوثر","الكافرون","النصر","المسد","الإخلاص","الفلق","الناس"
];

// توليد أزرار السور
const list = document.getElementById("surahList");

surahs.forEach((name, index) => {
  const btn = document.createElement("button");
  btn.textContent = name;
  btn.onclick = () => loadSurah(index + 1, name);
  list.appendChild(btn);
});

// تشغيل السورة
function loadSurah(number, name) {
  document.getElementById("surahBox").style.display = "block";
  document.getElementById("surahTitle").textContent = name;

  // رابط بصوت القارئ ماهر المعيقلي
  document.getElementById("audioPlayer").src = 
    `https://server10.mp3quran.net/maher/${String(number).padStart(3,"0")}.mp3`;

  document.getElementById("audioPlayer").play();
}
</script>

</body>
</html>

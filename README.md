
<!DOCTYPE html>
<html lang="my">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#090b12">
<title>Myanmar Dub AI</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}
body{
 background:#090b12;color:#f5f5ff;
 font-family:Arial,sans-serif;
 min-height:100vh;
}
header{
 padding:20px 6%;display:flex;
 justify-content:space-between;align-items:center;
 border-bottom:1px solid #25283a;
}
.logo{font-size:21px;font-weight:900;letter-spacing:1px}
.logo span{color:#9675ff}
.status{color:#51e2c2;font-size:12px}
main{max-width:850px;margin:auto;padding:35px 18px}
.hero{text-align:center;margin-bottom:30px}
.hero h1{font-size:38px;line-height:1.3}
.hero h1 span{color:#9675ff}
.hero p{color:#9299ad;margin-top:12px;line-height:1.7}
.tags{margin-top:18px}
.tags span{
 display:inline-block;background:#1a1830;
 color:#c5b7ff;padding:8px 11px;
 border-radius:7px;font-size:11px;margin:3px
}
.card{
 background:#121624;border:1px solid #282d42;
 border-radius:16px;padding:20px;margin-bottom:18px
}
.heading{
 display:flex;justify-content:space-between;
 align-items:center;margin-bottom:16px
}
.heading h2{font-size:17px}
.step{font-size:10px;color:#9299ad}
.tabs{display:flex;gap:8px;margin-bottom:16px}
button{cursor:pointer;font-weight:bold}
.tab{
 flex:1;padding:12px;border:1px solid #30344a;
 border-radius:9px;background:#0c101b;color:#999;
}
.tab.active{background:#282044;color:#c9bcff;border-color:#8064e5}
.upload{
 border:2px dashed #594b89;background:#19172b;
 border-radius:13px;padding:30px 12px;text-align:center;
}
.upload-icon{font-size:35px;color:#9675ff;margin-bottom:12px}
.upload h3{font-size:15px;margin-bottom:8px}
.upload p{font-size:11px;color:#9299ad}
.file-btn{
 display:inline-block;margin-top:17px;
 padding:11px 18px;background:#30264e;
 color:#d4caff;border-radius:8px;font-size:12px;
}
input[type=file]{display:none}
input[type=text]{
 width:100%;padding:14px;background:#090b12;
 color:white;border:1px solid #30344a;
 border-radius:9px;margin-top:10px;
}
.preview{width:100%;max-height:280px;object-fit:contain;
 margin-top:15px;border-radius:10px;display:none;background:#000}
.label{font-size:10px;color:#9299ad;letter-spacing:1px;font-weight:bold}
.language{
 margin-top:10px;padding:15px;
 border-radius:10px;background:#1b2030;
 display:flex;justify-content:space-between;align-items:center
}
.language strong{font-size:14px}
.language small{color:#9299ad}
.arrow{text-align:center;color:#9675ff;padding:10px}
.voices{display:flex;gap:10px;margin-top:12px}
.voice{
 flex:1;padding:16px 10px;background:#1b2030;
 border:1px solid #30344a;border-radius:11px;
 color:white;text-align:left
}
.voice.active{border-color:#9675ff;background:#282044}
.voice b{display:block;margin-top:9px;font-size:13px}
.voice small{display:block;color:#9299ad;margin-top:5px}
.setting{
 display:flex;justify-content:space-between;
 align-items:center;padding:14px 0;border-bottom:1px solid #282d42
}
.setting:last-child{border:0}
.setting p{font-size:13px;font-weight:bold}
.setting small{font-size:10px;color:#9299ad;display:block;margin-top:5px}
.on{color:#51e2c2;font-size:11px;font-weight:bold}
select{
 background:#1b2030;color:white;padding:9px;
 border:1px solid #30344a;border-radius:8px
}
.generate{
 width:100%;padding:17px;background:linear-gradient(100deg,#7858e8,#a16dff);
 border:0;border-radius:11px;color:white;font-size:15px;
}
.note{text-align:center;color:#777f94;font-size:10px;margin-top:15px;line-height:1.7}
#message{
 display:none;margin-top:15px;padding:13px;
 background:#211d37;border:1px solid #57478a;
 border-radius:9px;color:#d4caff;font-size:12px;line-height:1.7
}
footer{text-align:center;padding:25px;color:#697187;font-size:11px}
@media(max-width:450px){
 .hero h1{font-size:31px}
 main{padding:27px 14px}
 .card{padding:15px}
}
</style>
</head>

<body>

<header>
 <div class="logo">MYANMAR <span>DUB AI</span></div>
 <div class="status">● BETA VERSION</div>
</header>

<main>

<section class="hero">
 <h1>Your Video,<br><span>In Myanmar.</span></h1>
 <p>AI နည်းပညာဖြင့် Video များကို<br>
 မြန်မာအသံနှင့် မြန်မာစာတန်းထိုး ပြောင်းလဲပါ။</p>
 <div class="tags">
  <span>✦ AI TRANSLATION</span>
  <span>♫ MYANMAR VOICE</span>
  <span>▤ SUBTITLES</span>
 </div>
</section>

<div class="heading">
 <h2>🎬 Create New Dub</h2>
 <span class="step">STEP 01 / 03</span>
</div>

<section class="card">
 <div class="tabs">
  <button class="tab active" id="uploadTab" onclick="setMode('upload')">↑ Upload Video</button>
  <button class="tab" id="linkTab" onclick="setMode('link')">↗ Video Link</button>
 </div>

 <div id="uploadArea" class="upload">
  <div class="upload-icon">⇧</div>
  <h3>Select Your Video</h3>
  <p>MP4 / MOV · Recommended 1–5 minutes</p>
  <label class="file-btn" for="videoFile">Choose Video</label>
  <input type="file" id="videoFile" accept="video/mp4,video/quicktime,video/*">
  <p id="fileName" style="margin-top:12px"></p>
  <video id="preview" class="preview" controls></video>
 </div>

 <div id="linkArea" style="display:none">
  <div class="label">VIDEO URL</div>
  <input type="text" id="videoUrl" placeholder="Paste YouTube / TikTok link">
  <p style="color:#9299ad;font-size:10px;margin-top:10px">
   Link processing requires a compatible backend.
  </p>
 </div>
</section>

<div class="heading">
 <h2>🌐 Language & Voice</h2>
 <span class="step">STEP 02 / 03</span>
</div>

<section class="card">
 <div class="label">SOURCE LANGUAGE</div>
 <div class="language">
  <strong>🇬🇧 English</strong>
  <small>Original</small>
 </div>

 <div class="arrow">↓</div>

 <div class="label">TARGET LANGUAGE</div>
 <div class="language">
  <strong>🇲🇲 မြန်မာဘာသာ</strong>
  <small>Myanmar</small>
 </div>

 <div style="margin-top:22px" class="label">SELECT NARRATOR</div>
 <div class="voices">
  <button class="voice active" onclick="setVoice(this,'male')">
   🎙️
   <b>Male Voice</b>
   <small>အမျိုးသားအသံ</small>
  </button>
  <button class="voice" onclick="setVoice(this,'female')">
   🎙️
   <b>Female Voice</b>
   <small>အမျိုးသမီးအသံ</small>
  </button>
 </div>
</section>

<div class="heading">
 <h2>⚙️ Output Settings</h2>
 <span class="step">STEP 03 / 03</span>
</div>

<section class="card">
 <div class="setting">
  <div>
   <p>Myanmar Subtitles</p>
   <small>မြန်မာစာတန်းထိုး ထည့်မယ်</small>
  </div>
  <span class="on">ON ✓</span>
 </div>

 <div class="setting">
  <div>
   <p>Replace Original Speech</p>
   <small>မူရင်းစကားပြောသံ အစားထိုးမယ်</small>
  </div>
  <span class="on">ON ✓</span>
 </div>

 <div class="setting">
  <div>
   <p>Export Format</p>
   <small>Output Video Format</small>
  </div>
  <select id="format">
   <option>MP4</option>
  </select>
 </div>
</section>

<button class="generate" onclick="generateDub()">
 ✦ Generate Myanmar Dub →
</button>

<div id="message"></div>

<p class="note">
 MYANMAR DUB AI · FREE STARTER VERSION<br>
 AI processing service is not connected yet.
</p>

</main>

<footer>© 2026 MYANMAR DUB AI · Made with ❤️</footer>

<script>
let mode = "upload";
let selectedVoice = "male";
let previewURL = null;

function setMode(value){
 mode = value;
 document.getElementById("uploadArea").style.display =
  value === "upload" ? "block" : "none";
 document.getElementById("linkArea").style.display =
  value === "link" ? "block" : "none";
 document.getElementById("uploadTab").classList.toggle("active",value==="upload");
 document.getElementById("linkTab").classList.toggle("active",value==="link");
}

function setVoice(button,value){
 selectedVoice = value;
 document.querySelectorAll(".voice").forEach(v=>v.classList.remove("active"));
 button.classList.add("active");
}

document.getElementById("videoFile").addEventListener("change",function(){
 const file = this.files[0];
 if(!file)return;

 document.getElementById("fileName").textContent = "✓ "+file.name;
 const preview = document.getElementById("preview");

 if(previewURL)URL.revokeObjectURL(previewURL);
 previewURL = URL.createObjectURL(file);

 preview.src = previewURL;
 preview.style.display = "block";
});

function generateDub(){
 const message = document.getElementById("message");

 if(mode==="upload" && !document.getElementById("videoFile").files.length){
  message.style.display="block";
  message.textContent="⚠️ အရင်ဆုံး Video တစ်ခု ရွေးပေးပါ။";
  return;
 }

 if(mode==="link" && !document.getElementById("videoUrl").value.trim()){
  message.style.display="block";
  message.textContent="⚠️ Video Link ထည့်ပေးပါ။";
  return;
 }

 message.style.display="block";
 message.textContent =
 "✓ Video ရွေးချယ်မှု အောင်မြင်ပါတယ်။ "+
 "Narrator: "+selectedVoice.toUpperCase()+
 ". AI Dubbing လုပ်ဆောင်ရန် Backend နဲ့ Burmese Voice Engine ချိတ်ဆက်ဖို့ လိုအပ်ပါသေးတယ်။";
}
</script>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#101b38">
<title>Youth Future - AI Learning</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:Arial,sans-serif;background:#f2f5fc;color:#17213a}
header{background:linear-gradient(135deg,#101b38,#254c91);color:white;padding:25px 18px 30px;border-radius:0 0 25px 25px}
.brand{font-size:25px;font-weight:bold}
.tag{color:#c5d9ff;margin-top:8px}
.welcome{margin-top:25px;background:#ffffff18;padding:18px;border-radius:15px}
.welcome p{margin-top:10px;line-height:1.7;color:#dce7ff}
main{padding:20px 15px}
.section-title{font-size:20px;margin:15px 0}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:13px}
.card{background:white;border-radius:16px;padding:17px 12px;min-height:125px;box-shadow:0 3px 12px #17213a10;cursor:pointer}
.card .emoji{font-size:28px;margin-bottom:12px}
.card h3{font-size:15px;margin-bottom:8px}
.card p{font-size:12px;color:#64718a;line-height:1.5}
.lesson{background:white;border-radius:15px;padding:17px;margin:12px 0;box-shadow:0 3px 12px #17213a10}
.lesson h3{margin-bottom:10px;color:#183c79}
.lesson p{font-size:14px;line-height:1.8;color:#526079}
button{border:0;border-radius:9px;padding:12px 16px;background:#214e9b;color:white;font-weight:bold;cursor:pointer}
button:active{opacity:.8}
.languages{display:flex;gap:8px;margin:15px 0;flex-wrap:wrap}
.languages button{flex:1;min-width:85px;background:#e3eaf8;color:#214e9b}
.languages button.active{background:#214e9b;color:white}
.back{background:#e3eaf8;color:#214e9b;margin-bottom:15px}
.hero-ai{background:linear-gradient(135deg,#152a54,#4169bc);color:white;padding:22px;border-radius:16px}
.hero-ai p{line-height:1.7;margin-top:10px;color:#e1eaff}
.start{margin-top:15px}
.content-box{background:#e8efff;border-radius:14px;padding:17px;margin-top:15px;line-height:1.9}
footer{text-align:center;padding:25px;color:#64718a;font-size:12px}
nav{position:sticky;bottom:0;background:white;display:flex;justify-content:space-around;padding:13px 4px;border-top:1px solid #e6eaf2}
nav a{text-decoration:none;color:#244a88;font-size:12px}
[hidden]{display:none!important}
</style>
</head>

<body>

<header>
 <div class="brand">🚀 YOUTH FUTURE</div>
 <div class="tag">Learn Today. Build Tomorrow.</div>
 <div class="welcome">
  <h2>Welcome to Your Future!</h2>
  <p>Learn new skills, explore technology, discover opportunities and build your future.</p>
 </div>
</header>

<main id="home">

 <h2 class="section-title">Explore Your Future</h2>

 <div class="grid">
  <div class="card" onclick="openAI()">
   <div class="emoji">🤖</div>
   <h3>AI Learning</h3>
   <p>Learn Artificial Intelligence in three languages.</p>
  </div>

  <div class="card" onclick="showInfo('Digital Skills')">
   <div class="emoji">💻</div>
   <h3>Digital Skills</h3>
   <p>Learn typing, design and digital technology.</p>
  </div>

  <div class="card" onclick="showInfo('Online Work')">
   <div class="emoji">💼</div>
   <h3>Online Work</h3>
   <p>Explore freelancing and online opportunities.</p>
  </div>

  <div class="card" onclick="showInfo('Career Center')">
   <div class="emoji">🎯</div>
   <h3>Career Center</h3>
   <p>Discover jobs and scholarships.</p>
  </div>

  <div class="card" onclick="showInfo('Creator Studio')">
   <div class="emoji">✍️</div>
   <h3>Creator Studio</h3>
   <p>Create poetry, books and digital content.</p>
  </div>

  <div class="card" onclick="showInfo('Youth Community')">
   <div class="emoji">🌍</div>
   <h3>Youth Community</h3>
   <p>Connect and grow with other young people.</p>
  </div>
 </div>

 <div class="lesson">
  <h3>📚 Start Learning AI</h3>
  <p>Start your journey into Artificial Intelligence today.</p>
  <button class="start" onclick="openAI()">Explore AI Academy →</button>
 </div>

</main>

<!-- AI LEARNING SECTION -->

<main id="aiSection" hidden>

 <button class="back" onclick="goHome()">← Back to Home</button>

 <div class="hero-ai">
  <h1>🤖 AI Learning Academy</h1>
  <p id="intro">Learn Artificial Intelligence step by step. Free education for everyone.</p>
 </div>

 <h2 class="section-title" id="chooseTitle">Choose Your Language</h2>

 <div class="languages">
  <button id="btn-si" onclick="setLanguage('si')">سنڌي</button>
  <button id="btn-ur" onclick="setLanguage('ur')">اردو</button>
  <button id="btn-en" onclick="setLanguage('en')">English</button>
 </div>

 <h2 class="section-title" id="courseTitle">Your AI Courses</h2>

 <div id="courseList"></div>

 <div id="lessonDetail" hidden>
  <button class="back" onclick="showCourses()">← Back to Courses</button>
  <div class="content-box">
   <h2 id="detailTitle"></h2>
   <p id="detailText"></p>
   <h3 id="practiceTitle" style="margin-top:15px"></h3>
   <p id="practiceText"></p>
  </div>
 </div>

</main>

<footer>
 <strong>YOUTH FUTURE</strong><br>
 Learn Today. Build Tomorrow.<br>
 © 2026 Youth Future
</footer>

<nav>
 <a href="#" onclick="goHome();return false">🏠 Home</a>
 <a href="#" onclick="openAI();return false">📚 Learn</a>
 <a href="#" onclick="showInfo('Career Center');return false">💼 Career</a>
 <a href="#" onclick="showInfo('Profile');return false">👤 Profile</a>
</nav>

<script>
let language='si';

const courses={
si:{
intro:'مصنوعي ذهانت سکو، پنهنجي مستقبل کي بهتر بڻايو.',
choose:'پنهنجي ٻولي چونڊيو',
title:'AI جا مفت ڪورس',
lessons:[
['AI ڇا آهي؟','AI اهڙي ٽيڪنالاجي آهي جيڪا ڪمپيوٽرن کي سکڻ، معلومات سمجهڻ ۽ مختلف ڪم ڪرڻ ۾ مدد ڏئي ٿي. مثال طور ChatGPT سوالن جا جواب ڏئي سگهي ٿو ۽ لکڻ ۾ مدد ڪري ٿو.','پنهنجي موبائل تي ChatGPT کوليو ۽ ان کان پڇو: مصنوعي ذهانت ڇا آهي؟'],
['ChatGPT ڪيئن استعمال ڪجي؟','ChatGPT هڪ AI اسسٽنٽ آهي. توهان ان کان سوال پڇي، سبق سمجهي، مضمون لکرائي ۽ نوان خيال حاصل ڪري سگهو ٿا.','ChatGPT کي چئو: مون کي انگريزي جا پنج آسان لفظ سيکار.'],
['Prompt ڪيئن لکجي؟','Prompt اهو سوال يا هدايت آهي جيڪا توهان AI کي ڏيو ٿا. سٺو Prompt واضح ۽ تفصيلي هوندو آهي.','لکو: مون کي شاگردن لاءِ AI بابت سنڌي ۾ هڪ آسان سبق لکي ڏيو.'],
['AI سان تصويرون ٺاهڻ','AI تصوير ٺاهڻ جا اوزار توهان جي لکيل هدايت مان نيون تصويرون ٺاهي سگهن ٿا. تصوير لاءِ موضوع، رنگ ۽ انداز واضح ڪريو.','هڪ خيالي ڪتاب جي سرورق لاءِ تصوير ٺاهڻ جي هدايت لکو.'],
['AI جا فائدا ۽ خطرا','AI سکيا ۽ ڪم ۾ مدد ڪري ٿو، پر ڪڏهن غلط معلومات به ڏئي سگهي ٿو. اهم معلومات هميشه تصديق ڪريو ۽ ذاتي راز شيئر نه ڪريو.','AI کان مليل ڪنهن اهم خبر کي معتبر ذريعن سان چيڪ ڪريو.']
]
},
ur:{
intro:'مصنوعی ذہانت سیکھیں اور اپنے مستقبل کو بہتر بنائیں۔',
choose:'اپنی زبان منتخب کریں',
title:'AI کے مفت کورسز',
lessons:[
['AI کیا ہے؟','AI ایسی ٹیکنالوجی ہے جو کمپیوٹر کو سیکھنے، معلومات سمجھنے اور مختلف کام کرنے میں مدد دیتی ہے۔','اپنے موبائل پر ChatGPT کھولیں اور پوچھیں: مصنوعی ذہانت کیا ہے؟'],
['ChatGPT کیسے استعمال کریں؟','ChatGPT ایک AI اسسٹنٹ ہے۔ آپ اس سے سوالات پوچھ سکتے ہیں، سبق سمجھ سکتے ہیں اور لکھنے میں مدد لے سکتے ہیں۔','ChatGPT سے کہیں: مجھے انگریزی کے پانچ آسان الفاظ سکھائیں۔'],
['Prompt کیسے لکھیں؟','Prompt وہ سوال یا ہدایت ہے جو آپ AI کو دیتے ہیں۔ اچھا Prompt واضح اور تفصیلی ہوتا ہے۔','لکھیں: طلبہ کے لیے AI پر اردو میں ایک آسان سبق لکھیں۔'],
['AI سے تصاویر بنانا','AI امیج ٹولز آپ کی تحریری ہدایت سے نئی تصاویر بنا سکتے ہیں۔ موضوع اور انداز واضح لکھیں۔','ایک خیالی کتاب کے سرورق کی تصویر بنانے کی ہدایت لکھیں۔'],
['AI کے فائدے اور خطرات','AI کام میں مدد دیتا ہے لیکن کبھی غلط معلومات بھی دے سکتا ہے۔ اہم معلومات کی تصدیق کریں اور ذاتی راز شیئر نہ کریں۔','AI سے ملی کسی اہم خبر کو معتبر ذرائع سے چیک کریں۔']
]
},
en:{
intro:'Learn Artificial Intelligence and build your future.',
choose:'Choose Your Language',
title:'Free AI Courses',
lessons:[
['What is AI?','Artificial Intelligence is technology that helps computers learn, understand information and perform tasks.','Open ChatGPT and ask: What is Artificial Intelligence?'],
['How to use ChatGPT?','ChatGPT is an AI assistant. You can ask questions, understand lessons and get help with writing.','Ask ChatGPT: Teach me five easy English words.'],
['How to write a Prompt?','A prompt is an instruction or question you give to AI. A good prompt is clear and specific.','Write: Give me a simple lesson about AI for students.'],
['Create Images with AI','AI image tools can create new pictures from your written instructions. Describe the subject and style clearly.','Write a prompt for a fictional book cover.'],
['Benefits and Risks of AI','AI can help with learning and work, but it can also make mistakes. Verify important information and never share private secrets.','Check an important AI-generated fact using reliable sources.']
]
}
};

function openAI(){
 document.getElementById('home').hidden=true;
 document.getElementById('aiSection').hidden=false;
 setLanguage(language);
 window.scrollTo(0,0);
}

function goHome(){
 document.getElementById('aiSection').hidden=true;
 document.getElementById('home').hidden=false;
 window.scrollTo(0,0);
}

function setLanguage(lang){
 language=lang;
 const data=courses[lang];
 document.getElementById('intro').textContent=data.intro;
 document.getElementById('chooseTitle').textContent=data.choose;
 document.getElementById('courseTitle').textContent=data.title;

 ['si','ur','en'].forEach(x=>{
 document.getElementById('btn-'+x).classList.toggle('active',x===lang);
 });

 showCourses();
}

function showCourses(){
 document.getElementById('lessonDetail').hidden=true;
 document.getElementById('courseList').hidden=false;

 const data=courses[language];
 const list=document.getElementById('courseList');
 list.innerHTML='';

 data.lessons.forEach((lesson,index)=>{
 const card=document.createElement('div');
 card.className='lesson';
 const heading=document.createElement('h3');
 heading.textContent=(index+1)+'. '+lesson[0];
 const desc=document.createElement('p');
 desc.textContent=lesson[1].substring(0,95)+'...';
 const btn=document.createElement('button');
 btn.textContent=language==='si'?'سبق پڙهو →':language==='ur'?'سبق پڑھیں →':'Read Lesson →';
 btn.style.marginTop='12px';
 btn.onclick=()=>openLesson(index);
 card.append(heading,desc,btn);
 list.appendChild(card);
 });
}

function openLesson(index){
 const lesson=courses[language].lessons[index];
 document.getElementById('courseList').hidden=true;
 document.getElementById('lessonDetail').hidden=false;
 document.getElementById('detailTitle').textContent=lesson[0];
 document.getElementById('detailText').textContent=lesson[1];
 document.getElementById('practiceTitle').textContent=
 language==='si'?'📝 عملي مشق':language==='ur'?'📝 عملی مشق':'📝 Practical Exercise';
 document.getElementById('practiceText').textContent=lesson[2];
 window.scrollTo(0,0);
}

function showInfo(name){
 alert(name+' section is coming soon!');
}
</script>

</body>
</html>

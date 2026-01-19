<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'Prompt', sans-serif;
    }
    .coin-bounce {
      animation: bounce 0.6s ease infinite;
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .fade-in {
      animation: fadeIn 0.4s ease;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .pulse-correct {
      animation: pulseCorrect 0.5s ease;
    }
    @keyframes pulseCorrect {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }
    .shake-wrong {
      animation: shake 0.5s ease;
    }
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-10px); }
      75% { transform: translateX(10px); }
    }
    .star-pop {
      animation: starPop 0.3s ease forwards;
    }
    @keyframes starPop {
      0% { transform: scale(0); opacity: 0; }
      50% { transform: scale(1.3); }
      100% { transform: scale(1); opacity: 1; }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full w-full overflow-auto" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);"><!-- หน้าหลัก -->
   <div id="home-screen" class="min-h-full p-4 md:p-8">
    <div class="max-w-4xl mx-auto"><!-- Header -->
     <header class="text-center mb-8 fade-in">
      <div class="inline-flex items-center gap-3 bg-white/20 backdrop-blur-sm rounded-full px-6 py-3 mb-4"><span class="text-4xl coin-bounce">💰</span>
       <h1 id="main-title" class="text-2xl md:text-3xl font-bold text-white">คณิตศาสตร์การเงิน ป.5</h1><span class="text-4xl coin-bounce" style="animation-delay: 0.3s;">🪙</span>
      </div>
      <p id="welcome-text" class="text-white/90 text-lg">เลือกบทเรียนที่ต้องการเรียนรู้</p>
     </header><!-- คะแนนรวม -->
     <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 mb-4 flex items-center justify-center gap-4 fade-in" style="animation-delay: 0.1s;"><span class="text-3xl">⭐</span> <span class="text-white text-xl font-semibold">คะแนนรวม: <span id="total-score">0</span> ดาว</span>
     </div><!-- ผู้สร้างเกม -->
     <div class="bg-gradient-to-r from-pink-500/20 to-purple-500/20 backdrop-blur-sm rounded-2xl p-4 mb-6 text-center fade-in" style="animation-delay: 0.15s;">
      <div class="flex items-center justify-center gap-2 mb-1"><span class="text-2xl">👩‍💻</span> <span class="text-white/80 text-sm font-medium">สร้างสรรค์โดย</span>
      </div>
      <p id="creator-name" class="text-white text-lg font-bold">เด็กหญิงอัญรินทร์ สิงหรัตน์</p>
      <p id="creator-class" class="text-white/90 text-sm">ชั้นประถมศึกษาปีที่ 5/5 MEP</p>
     </div><!-- เมนูบทเรียน -->
     <div class="grid grid-cols-1 md:grid-cols-2 gap-4"><!-- บทเรียน 1: รู้จักเงินไทย --> <button onclick="startLesson('money-types')" class="lesson-card bg-gradient-to-br from-yellow-400 to-orange-500 rounded-2xl p-6 text-left hover:scale-105 transition-transform shadow-lg fade-in" style="animation-delay: 0.2s;">
       <div class="flex items-start gap-4"><span class="text-5xl">🏦</span>
        <div>
         <h3 class="text-xl font-bold text-white mb-1">รู้จักเงินไทย</h3>
         <p class="text-white/80 text-sm">เรียนรู้ธนบัตรและเหรียญ</p>
         <div class="mt-3 flex items-center gap-2"><span class="bg-white/20 px-3 py-1 rounded-full text-white text-xs">5 ข้อ</span>
         </div>
        </div>
       </div></button> <!-- บทเรียน 2: นับเงิน --> <button onclick="startLesson('counting')" class="lesson-card bg-gradient-to-br from-green-400 to-emerald-600 rounded-2xl p-6 text-left hover:scale-105 transition-transform shadow-lg fade-in" style="animation-delay: 0.3s;">
       <div class="flex items-start gap-4"><span class="text-5xl">🔢</span>
        <div>
         <h3 class="text-xl font-bold text-white mb-1">นับเงิน</h3>
         <p class="text-white/80 text-sm">รวมเงินจากธนบัตรและเหรียญ</p>
         <div class="mt-3 flex items-center gap-2"><span class="bg-white/20 px-3 py-1 rounded-full text-white text-xs">5 ข้อ</span>
         </div>
        </div>
       </div></button> <!-- บทเรียน 3: ทอนเงิน --> <button onclick="startLesson('change')" class="lesson-card bg-gradient-to-br from-blue-400 to-indigo-600 rounded-2xl p-6 text-left hover:scale-105 transition-transform shadow-lg fade-in" style="animation-delay: 0.4s;">
       <div class="flex items-start gap-4"><span class="text-5xl">🛒</span>
        <div>
         <h3 class="text-xl font-bold text-white mb-1">ทอนเงิน</h3>
         <p class="text-white/80 text-sm">คำนวณเงินทอนจากการซื้อของ</p>
         <div class="mt-3 flex items-center gap-2"><span class="bg-white/20 px-3 py-1 rounded-full text-white text-xs">5 ข้อ</span>
         </div>
        </div>
       </div></button> <!-- บทเรียน 4: เปรียบเทียบราคา --> <button onclick="startLesson('compare')" class="lesson-card bg-gradient-to-br from-pink-400 to-rose-600 rounded-2xl p-6 text-left hover:scale-105 transition-transform shadow-lg fade-in" style="animation-delay: 0.5s;">
       <div class="flex items-start gap-4"><span class="text-5xl">⚖️</span>
        <div>
         <h3 class="text-xl font-bold text-white mb-1">เปรียบเทียบราคา</h3>
         <p class="text-white/80 text-sm">เลือกซื้อของให้คุ้มค่า</p>
         <div class="mt-3 flex items-center gap-2"><span class="bg-white/20 px-3 py-1 rounded-full text-white text-xs">5 ข้อ</span>
         </div>
        </div>
       </div></button> <!-- บทเรียน 5: วางแผนการออม --> <button onclick="startLesson('saving')" class="lesson-card bg-gradient-to-br from-purple-400 to-violet-600 rounded-2xl p-6 text-left hover:scale-105 transition-transform shadow-lg fade-in md:col-span-2" style="animation-delay: 0.6s;">
       <div class="flex items-start gap-4"><span class="text-5xl">🐷</span>
        <div>
         <h3 class="text-xl font-bold text-white mb-1">วางแผนการออม</h3>
         <p class="text-white/80 text-sm">เรียนรู้การออมเงินและวางแผนการเงิน</p>
         <div class="mt-3 flex items-center gap-2"><span class="bg-white/20 px-3 py-1 rounded-full text-white text-xs">5 ข้อ</span>
         </div>
        </div>
       </div></button>
     </div>
    </div>
   </div><!-- หน้าเกม -->
   <div id="game-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><!-- Header เกม -->
     <div class="flex items-center justify-between mb-6"><button onclick="goHome()" class="bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-full flex items-center gap-2 transition-colors"> <span>←</span> กลับ </button>
      <div class="bg-white/20 px-4 py-2 rounded-full text-white">
       ข้อ <span id="current-question">1</span>/5
      </div>
      <div class="bg-yellow-400 px-4 py-2 rounded-full text-yellow-900 font-semibold flex items-center gap-2">
       ⭐ <span id="game-score">0</span>
      </div>
     </div><!-- Progress Bar -->
     <div class="bg-white/20 rounded-full h-3 mb-6 overflow-hidden">
      <div id="progress-bar" class="bg-gradient-to-r from-yellow-400 to-orange-500 h-full rounded-full transition-all duration-500" style="width: 20%;"></div>
     </div><!-- คำถาม -->
     <div id="question-card" class="bg-white rounded-3xl p-6 md:p-8 shadow-2xl">
      <h2 id="lesson-title" class="text-lg text-purple-600 font-semibold mb-2">รู้จักเงินไทย</h2>
      <div id="question-content" class="text-xl md:text-2xl text-gray-800 font-medium mb-6"><!-- คำถามจะแสดงที่นี่ -->
      </div><!-- ตัวเลือก -->
      <div id="choices" class="grid grid-cols-2 gap-3"><!-- ตัวเลือกจะแสดงที่นี่ -->
      </div><!-- ผลลัพธ์ -->
      <div id="result-message" class="mt-6 text-center hidden">
       <div id="result-icon" class="text-6xl mb-2"></div>
       <p id="result-text" class="text-xl font-semibold"></p>
       <p id="explanation" class="text-gray-600 mt-2"></p>
      </div><!-- ปุ่มถัดไป --> <button id="next-btn" onclick="nextQuestion()" class="hidden w-full mt-6 bg-gradient-to-r from-purple-500 to-indigo-600 text-white py-4 rounded-xl font-semibold text-lg hover:opacity-90 transition-opacity"> ข้อถัดไป → </button>
     </div>
    </div>
   </div><!-- หน้าสรุปผล -->
   <div id="result-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-lg mx-auto text-center">
     <div class="bg-white rounded-3xl p-8 shadow-2xl fade-in">
      <div class="text-7xl mb-4" id="final-emoji">
       🎉
      </div>
      <h2 class="text-3xl font-bold text-gray-800 mb-2">เก่งมาก!</h2>
      <p id="final-message" class="text-gray-600 mb-6">คุณทำได้ดีมาก</p>
      <div class="bg-gradient-to-r from-yellow-100 to-orange-100 rounded-2xl p-6 mb-6">
       <div class="text-5xl font-bold text-yellow-600 mb-2"><span id="final-score">0</span>/5
       </div>
       <p class="text-yellow-700">คะแนนที่ได้</p>
       <div id="stars-display" class="flex justify-center gap-2 mt-4"><!-- ดาวจะแสดงที่นี่ -->
       </div>
      </div>
      <div class="flex flex-col gap-3"><button onclick="restartLesson()" class="bg-gradient-to-r from-green-500 to-emerald-600 text-white py-4 rounded-xl font-semibold text-lg hover:opacity-90 transition-opacity"> 🔄 เล่นอีกครั้ง </button> <button onclick="goHome()" class="bg-gradient-to-r from-purple-500 to-indigo-600 text-white py-4 rounded-xl font-semibold text-lg hover:opacity-90 transition-opacity"> 🏠 กลับหน้าหลัก </button>
      </div>
     </div>
    </div>
   </div>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'เลือกบทเรียนที่ต้องการเรียนรู้',
      creator_name: 'เด็กหญิงอัญรินทร์ สิงหรัตน์',
      creator_class: 'ชั้นประถมศึกษาปีที่ 5/5 MEP',
      background_color: '#667eea',
      surface_color: '#ffffff',
      text_color: '#1f2937',
      primary_action_color: '#8b5cf6',
      secondary_action_color: '#6366f1',
      font_family: 'Prompt',
      font_size: 16
    };

    let config = { ...defaultConfig };

    // Game state
    let currentLesson = '';
    let currentQuestionIndex = 0;
    let score = 0;
    let totalScore = 0;
    let questions = [];
    let answered = false;

    // ข้อมูลบทเรียน
    const lessons = {
      'money-types': {
        title: 'รู้จักเงินไทย',
        questions: [
          {
            question: 'ธนบัตรใบละ 1,000 บาท มีสีอะไร?',
            choices: ['สีแดง', 'สีเขียว', 'สีน้ำตาล', 'สีม่วง'],
            answer: 2,
            explanation: 'ธนบัตร 1,000 บาท มีสีน้ำตาล'
          },
          {
            question: 'เหรียญ 10 บาท มีลักษณะอย่างไร?',
            choices: ['สีเงินทั้งหมด', 'สีทองทั้งหมด', 'ขอบสีเงิน ตรงกลางสีทอง', 'ขอบสีทอง ตรงกลางสีเงิน'],
            answer: 2,
            explanation: 'เหรียญ 10 บาท มีขอบสีเงิน และตรงกลางสีทอง'
          },
          {
            question: 'ธนบัตรใบละกี่บาทที่มีสีแดง?',
            choices: ['20 บาท', '50 บาท', '100 บาท', '500 บาท'],
            answer: 2,
            explanation: 'ธนบัตร 100 บาท มีสีแดง'
          },
          {
            question: 'เหรียญบาทใดมีขนาดเล็กที่สุด?',
            choices: ['25 สตางค์', '50 สตางค์', '1 บาท', '2 บาท'],
            answer: 0,
            explanation: 'เหรียญ 25 สตางค์ มีขนาดเล็กที่สุด'
          },
          {
            question: 'ธนบัตรใบละ 500 บาท มีสีอะไร?',
            choices: ['สีเขียว', 'สีน้ำเงิน', 'สีม่วง', 'สีแดง'],
            answer: 2,
            explanation: 'ธนบัตร 500 บาท มีสีม่วง'
          }
        ]
      },
      'counting': {
        title: 'นับเงิน',
        questions: [
          {
            question: 'ธนบัตร 100 บาท 2 ใบ + เหรียญ 10 บาท 3 เหรียญ = ?',
            choices: ['210 บาท', '230 บาท', '203 บาท', '213 บาท'],
            answer: 1,
            explanation: '(100×2) + (10×3) = 200 + 30 = 230 บาท'
          },
          {
            question: 'ธนบัตร 500 บาท 1 ใบ + ธนบัตร 20 บาท 3 ใบ = ?',
            choices: ['520 บาท', '560 บาท', '580 บาท', '530 บาท'],
            answer: 1,
            explanation: '500 + (20×3) = 500 + 60 = 560 บาท'
          },
          {
            question: 'เหรียญ 5 บาท 8 เหรียญ + เหรียญ 2 บาท 5 เหรียญ = ?',
            choices: ['45 บาท', '50 บาท', '55 บาท', '40 บาท'],
            answer: 1,
            explanation: '(5×8) + (2×5) = 40 + 10 = 50 บาท'
          },
          {
            question: 'ธนบัตร 1000 บาท 1 ใบ + ธนบัตร 100 บาท 5 ใบ + เหรียญ 5 บาท 4 เหรียญ = ?',
            choices: ['1,520 บาท', '1,504 บาท', '1,540 บาท', '1,450 บาท'],
            answer: 0,
            explanation: '1000 + (100×5) + (5×4) = 1000 + 500 + 20 = 1,520 บาท'
          },
          {
            question: 'ธนบัตร 50 บาท 4 ใบ + เหรียญ 1 บาท 15 เหรียญ = ?',
            choices: ['200 บาท', '215 บาท', '205 บาท', '250 บาท'],
            answer: 1,
            explanation: '(50×4) + (1×15) = 200 + 15 = 215 บาท'
          }
        ]
      },
      'change': {
        title: 'ทอนเงิน',
        questions: [
          {
            question: 'ซื้อขนม 35 บาท จ่ายธนบัตร 50 บาท ได้เงินทอนเท่าไร?',
            choices: ['10 บาท', '15 บาท', '20 บาท', '25 บาท'],
            answer: 1,
            explanation: '50 - 35 = 15 บาท'
          },
          {
            question: 'ซื้อหนังสือ 185 บาท จ่ายธนบัตร 200 บาท ได้เงินทอนเท่าไร?',
            choices: ['15 บาท', '25 บาท', '20 บาท', '10 บาท'],
            answer: 0,
            explanation: '200 - 185 = 15 บาท'
          },
          {
            question: 'ซื้อของเล่น 450 บาท จ่ายธนบัตร 500 บาท ได้เงินทอนเท่าไร?',
            choices: ['40 บาท', '50 บาท', '60 บาท', '45 บาท'],
            answer: 1,
            explanation: '500 - 450 = 50 บาท'
          },
          {
            question: 'ซื้อข้าวกล่อง 45 บาท และน้ำ 15 บาท จ่าย 100 บาท ได้เงินทอนเท่าไร?',
            choices: ['30 บาท', '35 บาท', '40 บาท', '45 บาท'],
            answer: 2,
            explanation: '45 + 15 = 60 บาท, 100 - 60 = 40 บาท'
          },
          {
            question: 'ซื้อปากกา 28 บาท ดินสอ 12 บาท จ่าย 50 บาท ได้เงินทอนเท่าไร?',
            choices: ['8 บาท', '10 บาท', '12 บาท', '15 บาท'],
            answer: 1,
            explanation: '28 + 12 = 40 บาท, 50 - 40 = 10 บาท'
          }
        ]
      },
      'compare': {
        title: 'เปรียบเทียบราคา',
        questions: [
          {
            question: 'ร้าน A ขายปากกา 3 ด้าม 45 บาท, ร้าน B ขายด้ามละ 12 บาท ร้านไหนถูกกว่า?',
            choices: ['ร้าน A ถูกกว่า', 'ร้าน B ถูกกว่า', 'ราคาเท่ากัน', 'เปรียบเทียบไม่ได้'],
            answer: 1,
            explanation: 'ร้าน A: 45÷3 = 15 บาท/ด้าม, ร้าน B: 12 บาท/ด้าม ดังนั้น ร้าน B ถูกกว่า'
          },
          {
            question: 'น้ำขวดใหญ่ 1.5 ลิตร ราคา 30 บาท, ขวดเล็ก 0.5 ลิตร ราคา 12 บาท อันไหนคุ้มกว่า?',
            choices: ['ขวดใหญ่คุ้มกว่า', 'ขวดเล็กคุ้มกว่า', 'คุ้มเท่ากัน', 'เปรียบเทียบไม่ได้'],
            answer: 0,
            explanation: 'ขวดใหญ่: 30÷1.5 = 20 บาท/ลิตร, ขวดเล็ก: 12÷0.5 = 24 บาท/ลิตร ขวดใหญ่คุ้มกว่า'
          },
          {
            question: 'ซื้อสมุด 5 เล่ม 75 บาท หรือ 2 เล่ม 28 บาท อันไหนคุ้มกว่า?',
            choices: ['5 เล่ม 75 บาท', '2 เล่ม 28 บาท', 'คุ้มเท่ากัน', 'เปรียบเทียบไม่ได้'],
            answer: 1,
            explanation: '5 เล่ม: 75÷5 = 15 บาท/เล่ม, 2 เล่ม: 28÷2 = 14 บาท/เล่ม ดังนั้น 2 เล่มคุ้มกว่า'
          },
          {
            question: 'มีเงิน 200 บาท ซื้อของราคา 180 บาท ลด 10% หรือลด 15 บาท อันไหนถูกกว่า?',
            choices: ['ลด 10% ถูกกว่า', 'ลด 15 บาท ถูกกว่า', 'ถูกเท่ากัน', 'เปรียบเทียบไม่ได้'],
            answer: 0,
            explanation: 'ลด 10%: 180×0.10 = 18 บาท (จ่าย 162 บาท), ลด 15 บาท จ่าย 165 บาท ลด 10% ถูกกว่า'
          },
          {
            question: 'ขนม A 6 ชิ้น 42 บาท, ขนม B 4 ชิ้น 32 บาท อันไหนถูกกว่าต่อชิ้น?',
            choices: ['ขนม A ถูกกว่า', 'ขนม B ถูกกว่า', 'ราคาเท่ากัน', 'เปรียบเทียบไม่ได้'],
            answer: 0,
            explanation: 'ขนม A: 42÷6 = 7 บาท/ชิ้น, ขนม B: 32÷4 = 8 บาท/ชิ้น ขนม A ถูกกว่า'
          }
        ]
      },
      'saving': {
        title: 'วางแผนการออม',
        questions: [
          {
            question: 'ต้องการเก็บเงิน 500 บาท ใน 10 สัปดาห์ ต้องเก็บสัปดาห์ละเท่าไร?',
            choices: ['40 บาท', '50 บาท', '45 บาท', '55 บาท'],
            answer: 1,
            explanation: '500 ÷ 10 = 50 บาท/สัปดาห์'
          },
          {
            question: 'เก็บเงินวันละ 20 บาท เป็นเวลา 1 เดือน (30 วัน) จะมีเงินเท่าไร?',
            choices: ['500 บาท', '600 บาท', '700 บาท', '550 บาท'],
            answer: 1,
            explanation: '20 × 30 = 600 บาท'
          },
          {
            question: 'มีเงิน 1,000 บาท อยากซื้อของเล่น 350 บาท และเก็บออม 500 บาท เหลือใช้เท่าไร?',
            choices: ['100 บาท', '150 บาท', '200 บาท', '250 บาท'],
            answer: 1,
            explanation: '1000 - 350 - 500 = 150 บาท'
          },
          {
            question: 'ได้เงินค่าขนมวันละ 50 บาท ถ้าเก็บ 30% ทุกวัน ใน 1 สัปดาห์จะเก็บได้เท่าไร?',
            choices: ['100 บาท', '105 บาท', '110 บาท', '90 บาท'],
            answer: 1,
            explanation: 'เก็บวันละ 50×0.30 = 15 บาท, 1 สัปดาห์ = 15×7 = 105 บาท'
          },
          {
            question: 'ตั้งเป้าเก็บเงิน 1,200 บาท ใน 6 เดือน เดือนแรกเก็บได้ 250 บาท ต้องเก็บเดือนละเท่าไรใน 5 เดือนที่เหลือ?',
            choices: ['180 บาท', '190 บาท', '200 บาท', '210 บาท'],
            answer: 1,
            explanation: 'ต้องเก็บอีก 1200 - 250 = 950 บาท, 950 ÷ 5 = 190 บาท/เดือน'
          }
        ]
      }
    };

    // Initialize SDK
    async function initializeApp() {
      if (window.elementSdk) {
        await window.elementSdk.init({
          defaultConfig,
          onConfigChange: async (newConfig) => {
            config = { ...defaultConfig, ...newConfig };
            updateUI();
          },
          mapToCapabilities: (cfg) => ({
            recolorables: [
              {
                get: () => cfg.background_color || defaultConfig.background_color,
                set: (v) => { cfg.background_color = v; window.elementSdk.setConfig({ background_color: v }); }
              },
              {
                get: () => cfg.surface_color || defaultConfig.surface_color,
                set: (v) => { cfg.surface_color = v; window.elementSdk.setConfig({ surface_color: v }); }
              },
              {
                get: () => cfg.text_color || defaultConfig.text_color,
                set: (v) => { cfg.text_color = v; window.elementSdk.setConfig({ text_color: v }); }
              },
              {
                get: () => cfg.primary_action_color || defaultConfig.primary_action_color,
                set: (v) => { cfg.primary_action_color = v; window.elementSdk.setConfig({ primary_action_color: v }); }
              },
              {
                get: () => cfg.secondary_action_color || defaultConfig.secondary_action_color,
                set: (v) => { cfg.secondary_action_color = v; window.elementSdk.setConfig({ secondary_action_color: v }); }
              }
            ],
            borderables: [],
            fontEditable: {
              get: () => cfg.font_family || defaultConfig.font_family,
              set: (v) => { cfg.font_family = v; window.elementSdk.setConfig({ font_family: v }); }
            },
            fontSizeable: {
              get: () => cfg.font_size || defaultConfig.font_size,
              set: (v) => { cfg.font_size = v; window.elementSdk.setConfig({ font_size: v }); }
            }
          }),
          mapToEditPanelValues: (cfg) => new Map([
            ['app_title', cfg.app_title || defaultConfig.app_title],
            ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message],
            ['creator_name', cfg.creator_name || defaultConfig.creator_name],
            ['creator_class', cfg.creator_class || defaultConfig.creator_class]
          ])
        });
        config = { ...defaultConfig, ...window.elementSdk.config };
      }
      updateUI();
      loadTotalScore();
    }

    function updateUI() {
      const title = config.app_title || defaultConfig.app_title;
      const welcome = config.welcome_message || defaultConfig.welcome_message;
      const creatorName = config.creator_name || defaultConfig.creator_name;
      const creatorClass = config.creator_class || defaultConfig.creator_class;
      const bgColor = config.background_color || defaultConfig.background_color;
      const surfaceColor = config.surface_color || defaultConfig.surface_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const primaryColor = config.primary_action_color || defaultConfig.primary_action_color;
      const fontFamily = config.font_family || defaultConfig.font_family;
      const fontSize = config.font_size || defaultConfig.font_size;

      document.getElementById('main-title').textContent = title;
      document.getElementById('welcome-text').textContent = welcome;
      document.getElementById('creator-name').textContent = creatorName;
      document.getElementById('creator-class').textContent = creatorClass;
      
      document.getElementById('app').style.background = `linear-gradient(135deg, ${bgColor} 0%, ${primaryColor} 100%)`;
      
      document.querySelectorAll('.bg-white').forEach(el => {
        el.style.backgroundColor = surfaceColor;
      });
      
      document.body.style.fontFamily = `${fontFamily}, Prompt, sans-serif`;
      document.body.style.fontSize = `${fontSize}px`;
    }

    function loadTotalScore() {
      const saved = localStorage.getItem('mathMoney_totalScore');
      if (saved) {
        totalScore = parseInt(saved);
        document.getElementById('total-score').textContent = totalScore;
      }
    }

    function saveTotalScore() {
      localStorage.setItem('mathMoney_totalScore', totalScore.toString());
      document.getElementById('total-score').textContent = totalScore;
    }

    function startLesson(lessonId) {
      currentLesson = lessonId;
      currentQuestionIndex = 0;
      score = 0;
      answered = false;
      questions = [...lessons[lessonId].questions];
      shuffleArray(questions);
      
      document.getElementById('home-screen').classList.add('hidden');
      document.getElementById('game-screen').classList.remove('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      
      document.getElementById('lesson-title').textContent = lessons[lessonId].title;
      document.getElementById('game-score').textContent = '0';
      
      showQuestion();
    }

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
    }

    function showQuestion() {
      answered = false;
      const q = questions[currentQuestionIndex];
      
      document.getElementById('current-question').textContent = currentQuestionIndex + 1;
      document.getElementById('progress-bar').style.width = `${((currentQuestionIndex + 1) / 5) * 100}%`;
      
      document.getElementById('question-content').innerHTML = `<p class="mb-4">${q.question}</p>`;
      
      const choicesDiv = document.getElementById('choices');
      choicesDiv.innerHTML = '';
      
      q.choices.forEach((choice, index) => {
        const btn = document.createElement('button');
        btn.className = 'choice-btn bg-gray-100 hover:bg-gray-200 text-gray-800 py-4 px-4 rounded-xl font-medium transition-all text-left';
        btn.innerHTML = `<span class="inline-block w-8 h-8 bg-purple-100 text-purple-600 rounded-full text-center leading-8 mr-2 font-bold">${String.fromCharCode(65 + index)}</span>${choice}`;
        btn.onclick = () => selectAnswer(index);
        choicesDiv.appendChild(btn);
      });
      
      document.getElementById('result-message').classList.add('hidden');
      document.getElementById('next-btn').classList.add('hidden');
      
      document.getElementById('question-card').classList.add('fade-in');
    }

    function selectAnswer(selectedIndex) {
      if (answered) return;
      answered = true;
      
      const q = questions[currentQuestionIndex];
      const isCorrect = selectedIndex === q.answer;
      const buttons = document.querySelectorAll('.choice-btn');
      
      buttons.forEach((btn, index) => {
        btn.disabled = true;
        if (index === q.answer) {
          btn.classList.remove('bg-gray-100', 'hover:bg-gray-200');
          btn.classList.add('bg-green-500', 'text-white');
        } else if (index === selectedIndex && !isCorrect) {
          btn.classList.remove('bg-gray-100', 'hover:bg-gray-200');
          btn.classList.add('bg-red-500', 'text-white');
        }
      });
      
      const resultDiv = document.getElementById('result-message');
      const resultIcon = document.getElementById('result-icon');
      const resultText = document.getElementById('result-text');
      const explanation = document.getElementById('explanation');
      
      if (isCorrect) {
        score++;
        document.getElementById('game-score').textContent = score;
        resultIcon.textContent = '🎉';
        resultText.textContent = 'ถูกต้อง!';
        resultText.className = 'text-xl font-semibold text-green-600';
        document.getElementById('question-card').classList.add('pulse-correct');
      } else {
        resultIcon.textContent = '😅';
        resultText.textContent = 'ไม่ถูกต้อง';
        resultText.className = 'text-xl font-semibold text-red-600';
        document.getElementById('question-card').classList.add('shake-wrong');
      }
      
      explanation.textContent = q.explanation;
      resultDiv.classList.remove('hidden');
      
      document.getElementById('next-btn').classList.remove('hidden');
      document.getElementById('next-btn').textContent = currentQuestionIndex < 4 ? 'ข้อถัดไป →' : 'ดูผลคะแนน 🏆';
      
      setTimeout(() => {
        document.getElementById('question-card').classList.remove('pulse-correct', 'shake-wrong');
      }, 500);
    }

    function nextQuestion() {
      if (currentQuestionIndex < 4) {
        currentQuestionIndex++;
        showQuestion();
      } else {
        showResults();
      }
    }

    function showResults() {
      totalScore += score;
      saveTotalScore();
      
      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.remove('hidden');
      
      document.getElementById('final-score').textContent = score;
      
      const starsDiv = document.getElementById('stars-display');
      starsDiv.innerHTML = '';
      for (let i = 0; i < 5; i++) {
        const star = document.createElement('span');
        star.className = 'text-4xl star-pop';
        star.style.animationDelay = `${i * 0.1}s`;
        star.textContent = i < score ? '⭐' : '☆';
        starsDiv.appendChild(star);
      }
      
      const emoji = document.getElementById('final-emoji');
      const message = document.getElementById('final-message');
      
      if (score === 5) {
        emoji.textContent = '🏆';
        message.textContent = 'ยอดเยี่ยม! คุณได้คะแนนเต็ม!';
      } else if (score >= 4) {
        emoji.textContent = '🎉';
        message.textContent = 'เก่งมาก! คุณทำได้ดีมาก!';
      } else if (score >= 3) {
        emoji.textContent = '😊';
        message.textContent = 'ดีมาก! พยายามต่อไปนะ!';
      } else if (score >= 2) {
        emoji.textContent = '💪';
        message.textContent = 'ไม่เป็นไร! ลองทบทวนอีกครั้ง';
      } else {
        emoji.textContent = '📚';
        message.textContent = 'มาเรียนรู้เพิ่มเติมกันเถอะ!';
      }
    }

    function restartLesson() {
      startLesson(currentLesson);
    }

    function goHome() {
      document.getElementById('home-screen').classList.remove('hidden');
      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
    }

    // Initialize app
    initializeApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c031c56a4ca893b',t:'MTc2ODc5MTkyOS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

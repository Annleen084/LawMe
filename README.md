
<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Everyday Law: กฎหมายในชีวิตจริง</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    * { font-family: 'Kanit', sans-serif; }
    
    .game-gradient {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
    }
    
    .card-gradient {
      background: linear-gradient(145deg, rgba(255,255,255,0.95) 0%, rgba(255,255,255,0.85) 100%);
      backdrop-filter: blur(10px);
    }
    
    .choice-btn {
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .choice-btn:hover {
      transform: translateY(-4px) scale(1.02);
      box-shadow: 0 12px 24px -6px rgba(0, 0, 0, 0.25);
    }
    
    .choice-btn:active {
      transform: translateY(0) scale(0.98);
    }
    
    .pulse-glow {
      animation: pulseGlow 2s infinite;
    }
    
    @keyframes pulseGlow {
      0%, 100% { box-shadow: 0 0 20px rgba(102, 126, 234, 0.4); }
      50% { box-shadow: 0 0 40px rgba(102, 126, 234, 0.8); }
    }
    
    .float-animation {
      animation: float 3s ease-in-out infinite;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    
    .slide-in {
      animation: slideIn 0.5s ease-out;
    }
    
    @keyframes slideIn {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .bounce-in {
      animation: bounceIn 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }
    
    @keyframes bounceIn {
      0% { transform: scale(0); opacity: 0; }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); opacity: 1; }
    }
    
    .progress-fill {
      transition: width 0.5s ease-out;
    }
    
    .emoji-icon {
      font-size: 3rem;
    }
    
    .correct-choice {
      background: linear-gradient(135deg, #10b981 0%, #059669 100%) !important;
      border-color: #059669 !important;
    }
    
    .wrong-choice {
      background: linear-gradient(135deg, #ef4444 0%, #dc2626 100%) !important;
      border-color: #dc2626 !important;
    }
    
    .star-burst {
      animation: starBurst 0.5s ease-out;
    }
    
    @keyframes starBurst {
      0% { transform: scale(0) rotate(0deg); }
      50% { transform: scale(1.3) rotate(180deg); }
      100% { transform: scale(1) rotate(360deg); }
    }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full game-gradient overflow-auto">
  <div id="app" class="min-h-full w-full p-4 md:p-6"><!-- Start Screen -->
   <div id="start-screen" class="max-w-2xl mx-auto">
    <div class="card-gradient rounded-3xl shadow-2xl p-6 md:p-10 text-center slide-in">
     <div class="emoji-icon float-animation mb-4">
      ⚖️
     </div>
     <h1 id="main-title" class="text-2xl md:text-4xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent mb-2">Everyday Law</h1>
     <h2 class="text-xl md:text-2xl font-semibold text-gray-700 mb-6">กฎหมายในชีวิตจริง</h2>
     <div class="bg-gradient-to-r from-purple-100 to-pink-100 rounded-2xl p-4 md:p-6 mb-6">
      <p id="welcome-text" class="text-gray-700 text-base md:text-lg leading-relaxed">🎮 ยินดีต้อนรับสู่เกมการเรียนรู้กฎหมายสำหรับนักเรียนชั้น ม.3!<br><br>
        คุณจะได้สวมบทบาทเป็นวัยรุ่นไทยที่ต้องเผชิญสถานการณ์ต่างๆ ในชีวิตประจำวัน และต้องเลือกการกระทำที่ถูกต้องตามกฎหมาย</p>
     </div>
     <div class="grid grid-cols-2 gap-3 md:gap-4 mb-6 text-left">
      <div class="bg-blue-50 rounded-xl p-3 md:p-4"><span class="text-2xl">📚</span>
       <p class="text-sm md:text-base font-medium text-blue-800 mt-1">เรียนรู้กฎหมายพื้นฐาน</p>
      </div>
      <div class="bg-green-50 rounded-xl p-3 md:p-4"><span class="text-2xl">🎯</span>
       <p class="text-sm md:text-base font-medium text-green-800 mt-1">6 สถานการณ์จริง</p>
      </div>
      <div class="bg-yellow-50 rounded-xl p-3 md:p-4"><span class="text-2xl">⭐</span>
       <p class="text-sm md:text-base font-medium text-yellow-800 mt-1">สะสมคะแนน</p>
      </div>
      <div class="bg-purple-50 rounded-xl p-3 md:p-4"><span class="text-2xl">🏆</span>
       <p class="text-sm md:text-base font-medium text-purple-800 mt-1">รับเกียรติบัตร</p>
      </div>
     </div><button onclick="startGame()" class="w-full choice-btn bg-gradient-to-r from-purple-600 to-pink-600 text-white text-lg md:text-xl font-bold py-4 px-8 rounded-2xl pulse-glow"> 🚀 เริ่มเกม! </button>
    </div>
   </div><!-- Game Screen -->
   <div id="game-screen" class="max-w-2xl mx-auto hidden"><!-- Progress Bar -->
    <div class="card-gradient rounded-2xl shadow-lg p-4 mb-4">
     <div class="flex justify-between items-center mb-2"><span class="text-sm md:text-base font-semibold text-gray-700"> 📍 ด่านที่ <span id="current-level">1</span> / 6 </span> <span class="text-sm md:text-base font-semibold text-purple-600"> ⭐ คะแนน: <span id="current-score">0</span> </span>
     </div>
     <div class="h-3 bg-gray-200 rounded-full overflow-hidden">
      <div id="progress-bar" class="h-full bg-gradient-to-r from-purple-500 to-pink-500 progress-fill rounded-full" style="width: 0%"></div>
     </div>
    </div><!-- Scenario Card -->
    <div class="card-gradient rounded-3xl shadow-2xl p-5 md:p-8 slide-in">
     <div class="flex items-center gap-3 mb-4"><span id="scenario-icon" class="text-4xl md:text-5xl">🛒</span>
      <div>
       <h3 id="scenario-title" class="text-lg md:text-xl font-bold text-gray-800">ชื่อสถานการณ์</h3>
       <p class="text-sm text-purple-600 font-medium">เลือกคำตอบที่ถูกต้องที่สุด</p>
      </div>
     </div>
     <div id="scenario-story" class="bg-gradient-to-r from-blue-50 to-purple-50 rounded-2xl p-4 md:p-5 mb-5">
      <p class="text-gray-700 text-base md:text-lg leading-relaxed">เนื้อเรื่อง...</p>
     </div>
     <div id="choices-container" class="space-y-3"><!-- Choices will be inserted here -->
     </div>
    </div><!-- Feedback Modal -->
    <div id="feedback-modal" class="hidden fixed inset-0 bg-black/50 flex items-center justify-center p-4 z-50">
     <div class="card-gradient rounded-3xl shadow-2xl p-6 md:p-8 max-w-lg w-full bounce-in">
      <div id="feedback-icon" class="text-6xl text-center mb-4">
       ✅
      </div>
      <h3 id="feedback-title" class="text-xl md:text-2xl font-bold text-center mb-4">ผลการตัดสินใจ</h3>
      <div id="feedback-text" class="bg-gray-50 rounded-2xl p-4 mb-4">
       <p class="text-gray-700 leading-relaxed">คำอธิบาย...</p>
      </div>
      <div id="feedback-law" class="bg-yellow-50 border-l-4 border-yellow-500 rounded-r-xl p-4 mb-5">
       <p class="text-sm font-semibold text-yellow-800 mb-1">📜 กฎหมายที่เกี่ยวข้อง</p>
       <p id="law-reference" class="text-sm text-yellow-700">...</p>
      </div>
      <div class="flex items-center justify-between">
       <div id="score-change" class="text-lg font-bold text-green-600">
        +10 คะแนน
       </div><button onclick="nextScenario()" class="choice-btn bg-gradient-to-r from-purple-600 to-pink-600 text-white font-bold py-3 px-6 rounded-xl"> ไปต่อ ➡️ </button>
      </div>
     </div>
    </div>
   </div><!-- Result Screen -->
   <div id="result-screen" class="max-w-2xl mx-auto hidden">
    <div class="card-gradient rounded-3xl shadow-2xl p-6 md:p-10 text-center slide-in">
     <div id="result-emoji" class="text-7xl mb-4 star-burst">
      🏆
     </div>
     <h2 class="text-2xl md:text-3xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent mb-2">จบเกมแล้ว!</h2>
     <p class="text-gray-600 mb-6">คุณเป็นพลเมืองที่เคารพกฎหมายระดับใด?</p>
     <div class="bg-gradient-to-r from-purple-100 to-pink-100 rounded-2xl p-6 mb-6">
      <p class="text-5xl font-bold text-purple-600 mb-2"><span id="final-score">0</span> / 60</p>
      <p class="text-lg text-gray-600">คะแนนรวม</p>
     </div>
     <div id="result-badge" class="bg-gradient-to-r from-yellow-400 to-orange-500 rounded-2xl p-5 mb-6 text-white">
      <p class="text-xl font-bold mb-1" id="badge-title">🥇 พลเมืองดีเด่น</p>
      <p class="text-sm opacity-90" id="badge-desc">คุณมีความรู้ด้านกฎหมายดีเยี่ยม!</p>
     </div>
     <div class="bg-blue-50 rounded-2xl p-4 mb-6 text-left">
      <p class="font-semibold text-blue-800 mb-2">📊 สรุปผลการเรียนรู้</p>
      <ul id="learning-summary" class="text-sm text-blue-700 space-y-1">
       <li>✓ สิทธิผู้บริโภค</li>
       <li>✓ กฎหมายอาญา</li>
      </ul>
     </div>
     <div class="grid grid-cols-2 gap-3"><button onclick="restartGame()" class="choice-btn bg-gradient-to-r from-green-500 to-emerald-600 text-white font-bold py-3 px-4 rounded-xl"> 🔄 เล่นอีกครั้ง </button> <button onclick="downloadCertificate()" class="choice-btn bg-gradient-to-r from-blue-500 to-cyan-600 text-white font-bold py-3 px-4 rounded-xl"> 📜 ดาวน์โหลดเกียรติบัตร </button>
     </div>
    </div>
   </div>
  </div>
  <script>
    // Game Configuration
    const defaultConfig = {
      game_title: 'Everyday Law: กฎหมายในชีวิตจริง',
      welcome_message: 'ยินดีต้อนรับสู่เกมการเรียนรู้กฎหมายสำหรับนักเรียนชั้น ม.3!',
      primary_color: '#7c3aed',
      secondary_color: '#ec4899',
      background_color: '#667eea',
      text_color: '#374151',
      accent_color: '#10b981'
    };

    let config = { ...defaultConfig };

    // Game State
    let currentLevel = 0;
    let score = 0;
    let answeredCorrectly = [];

    // Game Scenarios Data
    const scenarios = [
      {
        id: 1,
        icon: '🛒',
        title: 'การซื้อขายออนไลน์',
        topic: 'สิทธิผู้บริโภค',
        story: 'คุณสั่งซื้อรองเท้ากีฬาราคา 2,500 บาทจากร้านค้าออนไลน์ เมื่อได้รับสินค้าพบว่าเป็นของปลอม ไม่ตรงตามที่โฆษณา ร้านค้าปฏิเสธการคืนเงินและบล็อกการติดต่อ คุณจะทำอย่างไร?',
        choices: [
          {
            text: 'ปล่อยผ่าน เพราะเป็นของไม่แพงมาก ไม่อยากมีเรื่อง',
            points: 0,
            feedback: 'การไม่ดำเนินการทำให้สูญเสียสิทธิที่พึงได้รับ และยังทำให้ร้านค้าไม่สุจริตยังคงหลอกลวงคนอื่นต่อไป',
            isCorrect: false
          },
          {
            text: 'แจ้งความร้องทุกข์และร้องเรียนต่อ สคบ. พร้อมหลักฐานการซื้อขาย',
            points: 10,
            feedback: 'ถูกต้อง! ตาม พ.ร.บ.คุ้มครองผู้บริโภค พ.ศ.2522 และ พ.ร.บ.ว่าด้วยการกระทำความผิดเกี่ยวกับคอมพิวเตอร์ คุณมีสิทธิ์ร้องเรียนและเรียกร้องค่าเสียหายได้',
            isCorrect: true
          },
          {
            text: 'โพสต์ด่าร้านค้าในโซเชียลมีเดียให้คนอื่นรู้',
            points: 3,
            feedback: 'แม้จะช่วยเตือนคนอื่น แต่อาจถูกฟ้องกลับในข้อหาหมิ่นประมาทได้ ควรใช้ช่องทางกฎหมายที่ถูกต้อง',
            isCorrect: false
          }
        ],
        lawReference: 'พ.ร.บ.คุ้มครองผู้บริโภค พ.ศ.2522 มาตรา 4 และ พ.ร.บ.ว่าด้วยการกระทำความผิดเกี่ยวกับคอมพิวเตอร์ พ.ศ.2550'
      },
      {
        id: 2,
        icon: '📱',
        title: 'การโพสต์บนโซเชียลมีเดีย',
        topic: 'กฎหมายหมิ่นประมาท / Cyberbullying',
        story: 'เพื่อนร่วมห้องทำให้คุณโกรธมาก คุณอยากระบายความรู้สึกโดยโพสต์ในกลุ่มไลน์ห้องว่า "ไอ้ A มันเป็นคนโกหก ขี้โกง อย่าไปยุ่งกับมัน" พร้อมใส่รูปเพื่อน คุณคิดว่าจะเกิดอะไรขึ้น?',
        choices: [
          {
            text: 'โพสต์เลย เพราะเป็นความจริง เราไม่ผิด',
            points: 0,
            feedback: 'ผิด! แม้เป็นความจริง แต่การเผยแพร่ข้อความที่ทำให้ผู้อื่นเสียชื่อเสียงถือเป็นการหมิ่นประมาท มีโทษจำคุกไม่เกิน 1 ปี หรือปรับไม่เกิน 20,000 บาท',
            isCorrect: false
          },
          {
            text: 'ไม่โพสต์ เพราะอาจผิดกฎหมาย แต่ไปบอกเพื่อนคนอื่นแทน',
            points: 5,
            feedback: 'ดีกว่าโพสต์ออนไลน์ แต่การนินทาก็อาจนำไปสู่ปัญหาได้ ควรพูดคุยกับเพื่อนโดยตรงหรือปรึกษาครู',
            isCorrect: false
          },
          {
            text: 'ไม่โพสต์ และพยายามพูดคุยกับเพื่อนโดยตรง หรือปรึกษาครูหากมีปัญหา',
            points: 10,
            feedback: 'ถูกต้อง! การแก้ปัญหาโดยสันติวิธีและผ่านช่องทางที่เหมาะสมเป็นวิธีที่ดีที่สุด ไม่ผิดกฎหมายและไม่ทำลายความสัมพันธ์',
            isCorrect: true
          }
        ],
        lawReference: 'ป.อาญา มาตรา 326-328 (หมิ่นประมาท) และ พ.ร.บ.ว่าด้วยการกระทำความผิดเกี่ยวกับคอมพิวเตอร์ พ.ศ.2550 มาตรา 14'
      },
      {
        id: 3,
        icon: '🏫',
        title: 'อุบัติเหตุในโรงเรียน',
        topic: 'ความรับผิดทางแพ่ง',
        story: 'ระหว่างเล่นฟุตบอลในสนามโรงเรียน คุณเตะบอลแรงเกินไปจนถูกหน้าเพื่อนที่ยืนอยู่ข้างสนาม ทำให้แว่นตาแตกและมีรอยฟกช้ำ พ่อแม่เพื่อนต้องการให้คุณรับผิดชอบค่าเสียหาย',
        choices: [
          {
            text: 'ปฏิเสธ เพราะเป็นอุบัติเหตุ ไม่ได้ตั้งใจ',
            points: 3,
            feedback: 'แม้ไม่ได้ตั้งใจ แต่ตามกฎหมายแพ่งและพาณิชย์ หากการกระทำของเราก่อให้เกิดความเสียหาย เราต้องรับผิดชอบ',
            isCorrect: false
          },
          {
            text: 'ขอโทษและเสนอช่วยรับผิดชอบค่ารักษาพยาบาลและค่าแว่นตา',
            points: 10,
            feedback: 'ถูกต้อง! แม้เป็นอุบัติเหตุ แต่การแสดงความรับผิดชอบเป็นสิ่งที่ควรทำ และตรงกับหลักการชดใช้ค่าเสียหายในกฎหมายแพ่ง',
            isCorrect: true
          },
          {
            text: 'บอกให้ไปเรียกร้องจากโรงเรียน เพราะเกิดในโรงเรียน',
            points: 2,
            feedback: 'โรงเรียนอาจมีส่วนรับผิดชอบ แต่ผู้กระทำโดยตรงก็ต้องรับผิดชอบด้วย การผลักภาระให้ผู้อื่นไม่ใช่การแก้ปัญหาที่ถูกต้อง',
            isCorrect: false
          }
        ],
        lawReference: 'ป.แพ่งและพาณิชย์ มาตรา 420 ผู้ใดจงใจหรือประมาทเลินเล่อ ทำต่อบุคคลอื่นโดยผิดกฎหมายให้เขาเสียหาย ต้องชดใช้ค่าสินไหมทดแทน'
      },
      {
        id: 4,
        icon: '📝',
        title: 'การทำสัญญาและการกู้ยืมเงิน',
        topic: 'กฎหมายนิติกรรมสัญญา',
        story: 'เพื่อนสนิทขอยืมเงินคุณ 3,000 บาท สัญญาว่าจะคืนภายใน 2 สัปดาห์ คุณมีเงินเก็บอยู่และอยากช่วยเพื่อน คุณควรทำอย่างไร?',
        choices: [
          {
            text: 'ให้ยืมเลย ไม่ต้องเขียนอะไร เพราะเป็นเพื่อนกัน เชื่อใจได้',
            points: 3,
            feedback: 'ความไว้ใจเป็นสิ่งดี แต่ไม่มีหลักฐานอาจทำให้เกิดปัญหาในการทวงคืน และอาจกระทบมิตรภาพ',
            isCorrect: false
          },
          {
            text: 'ทำหลักฐานการกู้ยืมเป็นลายลักษณ์อักษร ระบุจำนวนเงิน วันที่ และกำหนดคืน',
            points: 10,
            feedback: 'ถูกต้อง! การทำหลักฐานเป็นหนังสือสำหรับการกู้ยืมเกิน 2,000 บาท เป็นข้อกำหนดตามกฎหมาย และช่วยป้องกันปัญหาในอนาคต',
            isCorrect: true
          },
          {
            text: 'ปฏิเสธ เพราะกลัวเพื่อนไม่คืน',
            points: 5,
            feedback: 'การปฏิเสธเป็นสิทธิ์ของคุณ แต่หากต้องการช่วยเพื่อน การทำเอกสารหลักฐานจะช่วยให้ทั้งสองฝ่ายสบายใจ',
            isCorrect: false
          }
        ],
        lawReference: 'ป.แพ่งและพาณิชย์ มาตรา 653 การกู้ยืมเงินเกินกว่า 2,000 บาท ต้องมีหลักฐานเป็นหนังสือลงลายมือชื่อผู้กู้ จึงจะฟ้องร้องบังคับคดีได้'
      },
      {
        id: 5,
        icon: '🚗',
        title: 'กฎจราจรและความรับผิดชอบต่อสาธารณะ',
        topic: 'กฎหมายจราจร',
        story: 'คุณขี่จักรยานยนต์ไปโรงเรียน วันนี้รีบมากเพราะใกล้สอบ คุณเห็นสัญญาณไฟเหลือง คุณจะทำอย่างไร?',
        choices: [
          {
            text: 'เร่งเครื่องผ่านไป เพราะยังไม่เป็นไฟแดง',
            points: 0,
            feedback: 'ผิด! ไฟเหลืองหมายถึงให้ชะลอและเตรียมหยุด ไม่ใช่ให้เร่ง การฝ่าไฟเหลืองอาจทำให้เกิดอุบัติเหตุและผิดกฎหมาย',
            isCorrect: false
          },
          {
            text: 'ชะลอความเร็วและหยุดรถก่อนถึงทางแยก',
            points: 10,
            feedback: 'ถูกต้อง! ไฟเหลืองหมายความว่าให้ผู้ขับขี่เตรียมหยุดรถ การปฏิบัติตามกฎจราจรช่วยรักษาความปลอดภัยของทุกคน',
            isCorrect: true
          },
          {
            text: 'ดูซ้าย-ขวาแล้วผ่านไป ถ้าไม่มีรถ',
            points: 3,
            feedback: 'แม้ดูเหมือนปลอดภัย แต่ยังถือว่าผิดกฎจราจร และอาจมีรถจากทิศอื่นที่มองไม่เห็น',
            isCorrect: false
          }
        ],
        lawReference: 'พ.ร.บ.จราจรทางบก พ.ศ.2522 มาตรา 22 และ มาตรา 152 ฝ่าฝืนมีโทษปรับไม่เกิน 1,000 บาท'
      },
      {
        id: 6,
        icon: '🔒',
        title: 'พฤติกรรมดิจิทัลและความเป็นส่วนตัว',
        topic: 'พ.ร.บ.คุ้มครองข้อมูลส่วนบุคคล (PDPA)',
        story: 'คุณถ่ายรูปกลุ่มเพื่อนในงานเลี้ยงวันเกิด รูปออกมาสวยมาก คุณอยากโพสต์ลงอินสตาแกรม แต่มีเพื่อนบางคนที่อาจไม่อยากให้โพสต์รูป คุณควรทำอย่างไร?',
        choices: [
          {
            text: 'โพสต์เลย เพราะเป็นงานสาธารณะ และรูปสวยทุกคน',
            points: 0,
            feedback: 'ผิด! แม้เป็นงานที่ทุกคนเข้าร่วม แต่การเผยแพร่รูปภาพผู้อื่นโดยไม่ได้รับอนุญาตอาจละเมิดสิทธิความเป็นส่วนตัว',
            isCorrect: false
          },
          {
            text: 'ถามเพื่อนทุกคนในรูปก่อนว่าอนุญาตให้โพสต์ไหม',
            points: 10,
            feedback: 'ถูกต้อง! การขออนุญาตก่อนเผยแพร่รูปภาพผู้อื่นเป็นการเคารพสิทธิความเป็นส่วนตัว และสอดคล้องกับ พ.ร.บ.คุ้มครองข้อมูลส่วนบุคคล',
            isCorrect: true
          },
          {
            text: 'โพสต์แต่เบลอหน้าคนที่ไม่อยากให้โพสต์',
            points: 7,
            feedback: 'เป็นทางเลือกที่ดี แต่ควรถามความยินยอมก่อน เพราะบางคนอาจไม่ต้องการให้รูปตัวเองปรากฏในโพสต์เลย',
            isCorrect: false
          }
        ],
        lawReference: 'พ.ร.บ.คุ้มครองข้อมูลส่วนบุคคล พ.ศ.2562 (PDPA) การเผยแพร่ข้อมูลส่วนบุคคล (รวมถึงรูปภาพ) ต้องได้รับความยินยอมจากเจ้าของข้อมูล'
      }
    ];

    // SDK Initialization
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (newConfig) => {
          config = { ...defaultConfig, ...newConfig };
          updateUI();
        },
        mapToCapabilities: (cfg) => ({
          recolorables: [
            {
              get: () => cfg.background_color || defaultConfig.background_color,
              set: (value) => {
                cfg.background_color = value;
                window.elementSdk.setConfig({ background_color: value });
              }
            },
            {
              get: () => cfg.primary_color || defaultConfig.primary_color,
              set: (value) => {
                cfg.primary_color = value;
                window.elementSdk.setConfig({ primary_color: value });
              }
            },
            {
              get: () => cfg.secondary_color || defaultConfig.secondary_color,
              set: (value) => {
                cfg.secondary_color = value;
                window.elementSdk.setConfig({ secondary_color: value });
              }
            },
            {
              get: () => cfg.text_color || defaultConfig.text_color,
              set: (value) => {
                cfg.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            },
            {
              get: () => cfg.accent_color || defaultConfig.accent_color,
              set: (value) => {
                cfg.accent_color = value;
                window.elementSdk.setConfig({ accent_color: value });
              }
            }
          ],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (cfg) => new Map([
          ['game_title', cfg.game_title || defaultConfig.game_title],
          ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
        ])
      });
    }

    function updateUI() {
      const title = document.getElementById('main-title');
      const welcomeText = document.getElementById('welcome-text');
      
      if (title && config.game_title) {
        const parts = config.game_title.split(':');
        title.textContent = parts[0].trim();
      }
      
      if (welcomeText && config.welcome_message) {
        welcomeText.innerHTML = `🎮 ${config.welcome_message}<br><br>
          คุณจะได้สวมบทบาทเป็นวัยรุ่นไทยที่ต้องเผชิญสถานการณ์ต่างๆ ในชีวิตประจำวัน 
          และต้องเลือกการกระทำที่ถูกต้องตามกฎหมาย`;
      }
      
      // Apply colors
      document.body.style.background = `linear-gradient(135deg, ${config.background_color} 0%, ${config.primary_color} 50%, ${config.secondary_color} 100%)`;
    }

    // Game Functions
    function startGame() {
      currentLevel = 0;
      score = 0;
      answeredCorrectly = [];
      
      document.getElementById('start-screen').classList.add('hidden');
      document.getElementById('game-screen').classList.remove('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      document.getElementById('feedback-modal').classList.add('hidden');
      
      loadScenario();
    }

    function loadScenario() {
      const scenario = scenarios[currentLevel];
      
      document.getElementById('current-level').textContent = currentLevel + 1;
      document.getElementById('current-score').textContent = score;
      document.getElementById('progress-bar').style.width = `${(currentLevel / scenarios.length) * 100}%`;
      
      document.getElementById('scenario-icon').textContent = scenario.icon;
      document.getElementById('scenario-title').textContent = scenario.title;
      document.getElementById('scenario-story').innerHTML = `<p class="text-gray-700 text-base md:text-lg leading-relaxed">${scenario.story}</p>`;
      
      const choicesContainer = document.getElementById('choices-container');
      choicesContainer.innerHTML = '';
      
      // Shuffle choices
      const shuffled = [...scenario.choices].sort(() => Math.random() - 0.5);
      
      shuffled.forEach((choice, index) => {
        const btn = document.createElement('button');
        btn.className = 'choice-btn w-full text-left bg-white border-2 border-purple-200 hover:border-purple-400 rounded-xl p-4 transition-all';
        btn.dataset.originalIndex = scenario.choices.indexOf(choice);
        btn.innerHTML = `
          <div class="flex items-start gap-3">
            <span class="flex-shrink-0 w-8 h-8 bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-full flex items-center justify-center font-bold text-sm">
              ${String.fromCharCode(65 + index)}
            </span>
            <p class="text-gray-700 text-sm md:text-base">${choice.text}</p>
          </div>
        `;
        btn.onclick = () => selectChoice(btn.dataset.originalIndex);
        choicesContainer.appendChild(btn);
      });
    }

    function selectChoice(choiceIndex) {
      const scenario = scenarios[currentLevel];
      const choice = scenario.choices[choiceIndex];
      
      // Disable all buttons
      const buttons = document.querySelectorAll('#choices-container button');
      buttons.forEach((btn, idx) => {
        btn.disabled = true;
        btn.classList.remove('hover:border-purple-400');
        if (idx === choiceIndex) {
          btn.classList.add(choice.isCorrect ? 'correct-choice' : 'wrong-choice');
          btn.classList.add('text-white');
        }
      });
      
      // Update score
      score += choice.points;
      answeredCorrectly.push({
        topic: scenario.topic,
        correct: choice.isCorrect,
        points: choice.points
      });
      
      // Show feedback
      setTimeout(() => {
        showFeedback(choice, scenario);
      }, 500);
    }

    function showFeedback(choice, scenario) {
      const modal = document.getElementById('feedback-modal');
      const icon = document.getElementById('feedback-icon');
      const title = document.getElementById('feedback-title');
      const text = document.getElementById('feedback-text');
      const law = document.getElementById('law-reference');
      const scoreChange = document.getElementById('score-change');
      
      if (choice.isCorrect) {
        icon.textContent = '✅';
        title.textContent = 'ยอดเยี่ยม! ตอบถูกต้อง';
        title.className = 'text-xl md:text-2xl font-bold text-center mb-4 text-green-600';
      } else if (choice.points > 0) {
        icon.textContent = '⚠️';
        title.textContent = 'เกือบถูกแล้ว!';
        title.className = 'text-xl md:text-2xl font-bold text-center mb-4 text-yellow-600';
      } else {
        icon.textContent = '❌';
        title.textContent = 'ไม่ถูกต้อง';
        title.className = 'text-xl md:text-2xl font-bold text-center mb-4 text-red-600';
      }
      
      text.innerHTML = `<p class="text-gray-700 leading-relaxed">${choice.feedback}</p>`;
      law.textContent = scenario.lawReference;
      
      if (choice.points > 0) {
        scoreChange.textContent = `+${choice.points} คะแนน`;
        scoreChange.className = 'text-lg font-bold text-green-600';
      } else {
        scoreChange.textContent = '0 คะแนน';
        scoreChange.className = 'text-lg font-bold text-gray-500';
      }
      
      modal.classList.remove('hidden');
    }

    function nextScenario() {
      document.getElementById('feedback-modal').classList.add('hidden');
      
      currentLevel++;
      
      if (currentLevel >= scenarios.length) {
        showResults();
      } else {
        loadScenario();
      }
    }

    function showResults() {
      document.getElementById('game-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.remove('hidden');
      
      document.getElementById('final-score').textContent = score;
      
      // Determine badge
      const resultEmoji = document.getElementById('result-emoji');
      const badgeTitle = document.getElementById('badge-title');
      const badgeDesc = document.getElementById('badge-desc');
      const resultBadge = document.getElementById('result-badge');
      
      let badge;
      if (score >= 50) {
        badge = {
          emoji: '🏆',
          title: '🥇 พลเมืองดีเด่น',
          desc: 'คุณมีความรู้ด้านกฎหมายดีเยี่ยม! พร้อมเป็นพลเมืองที่ดีของสังคม',
          gradient: 'from-yellow-400 to-orange-500'
        };
      } else if (score >= 35) {
        badge = {
          emoji: '🎖️',
          title: '🥈 พลเมืองดี',
          desc: 'คุณมีความรู้ด้านกฎหมายในระดับดี ศึกษาเพิ่มเติมอีกนิดจะเยี่ยมมาก!',
          gradient: 'from-gray-300 to-gray-400'
        };
      } else if (score >= 20) {
        badge = {
          emoji: '📚',
          title: '🥉 พลเมืองผู้เรียนรู้',
          desc: 'คุณกำลังเรียนรู้! ลองทบทวนความรู้เรื่องกฎหมายเพิ่มเติมนะ',
          gradient: 'from-orange-300 to-amber-400'
        };
      } else {
        badge = {
          emoji: '📖',
          title: '📘 เริ่มต้นเรียนรู้',
          desc: 'ยังต้องศึกษาเพิ่มเติม ลองเล่นอีกครั้งเพื่อเรียนรู้มากขึ้น!',
          gradient: 'from-blue-400 to-cyan-500'
        };
      }
      
      resultEmoji.textContent = badge.emoji;
      badgeTitle.textContent = badge.title;
      badgeDesc.textContent = badge.desc;
      resultBadge.className = `bg-gradient-to-r ${badge.gradient} rounded-2xl p-5 mb-6 text-white`;
      
      // Learning summary
      const summary = document.getElementById('learning-summary');
      summary.innerHTML = answeredCorrectly.map((item, idx) => {
        const icon = item.correct ? '✅' : (item.points > 0 ? '⚠️' : '❌');
        return `<li>${icon} ${scenarios[idx].topic}</li>`;
      }).join('');
    }

    function restartGame() {
      startGame();
    }

    function shareResult() {
      const text = `🎮 ฉันได้ ${score}/60 คะแนนในเกม "กฎหมายในชีวิตจริง"! มาทดสอบความรู้กฎหมายกันเถอะ! ⚖️`;
      
      if (navigator.share) {
        navigator.share({
          title: 'ผลลัพธ์เกมกฎหมาย',
          text: text
        });
      } else {
        // Create a temporary share message display
        const resultScreen = document.getElementById('result-screen');
        const existingToast = document.getElementById('share-toast');
        if (existingToast) existingToast.remove();
        
        const toast = document.createElement('div');
        toast.id = 'share-toast';
        toast.className = 'fixed bottom-4 left-4 right-4 bg-green-500 text-white p-4 rounded-xl text-center shadow-lg z-50 slide-in';
        toast.innerHTML = `
          <p class="font-bold mb-2">📋 คัดลอกข้อความแล้ว!</p>
          <p class="text-sm">${text}</p>
        `;
        document.body.appendChild(toast);
        
        // Copy to clipboard
        navigator.clipboard.writeText(text).catch(() => {});
        
        setTimeout(() => {
          toast.remove();
        }, 3000);
      }
    }

    function downloadCertificate() {
      // Create canvas for certificate
      const canvas = document.createElement('canvas');
      canvas.width = 1000;
      canvas.height = 700;
      const ctx = canvas.getContext('2d');

      // Background gradient
      const gradient = ctx.createLinearGradient(0, 0, 1000, 700);
      gradient.addColorStop(0, '#667eea');
      gradient.addColorStop(0.5, '#764ba2');
      gradient.addColorStop(1, '#f093fb');
      ctx.fillStyle = gradient;
      ctx.fillRect(0, 0, 1000, 700);

      // White certificate area
      ctx.fillStyle = 'rgba(255, 255, 255, 0.95)';
      ctx.shadowColor = 'rgba(0, 0, 0, 0.2)';
      ctx.shadowBlur = 20;
      ctx.shadowOffsetY = 10;
      ctx.fillRect(50, 50, 900, 600);
      ctx.shadowColor = 'transparent';

      // Border
      ctx.strokeStyle = '#667eea';
      ctx.lineWidth = 4;
      ctx.strokeRect(50, 50, 900, 600);

      // Decorative elements
      ctx.fillStyle = '#f093fb';
      ctx.font = 'bold 50px "Kanit"';
      ctx.textAlign = 'center';
      ctx.fillText('🏆', 500, 120);

      // Title
      ctx.fillStyle = '#333';
      ctx.font = 'bold 48px "Kanit"';
      ctx.fillText('เกียรติบัตรประกาศเชิด', 500, 200);

      // Subtitle
      ctx.fillStyle = '#666';
      ctx.font = '24px "Kanit"';
      ctx.fillText('กฎหมายในชีวิตจริง', 500, 240);

      // Awarded to
      ctx.fillStyle = '#333';
      ctx.font = '20px "Kanit"';
      ctx.fillText('มอบให้แก่', 500, 300);

      // User name placeholder
      ctx.fillStyle = '#764ba2';
      ctx.font = 'bold 32px "Kanit"';
      ctx.fillText('[ชื่อของคุณ]', 500, 360);

      // Achievement text
      ctx.fillStyle = '#555';
      ctx.font = '18px "Kanit"';
      ctx.fillText(`สำหรับการทำคะแนน ${score} จาก 60 คะแนน`, 500, 420);

      // Badge based on score
      let badgeText = '';
      if (score >= 50) badgeText = '🥇 พลเมืองดีเด่น';
      else if (score >= 35) badgeText = '🥈 พลเมืองดี';
      else if (score >= 20) badgeText = '🥉 พลเมืองผู้เรียนรู้';
      else badgeText = '📘 เริ่มต้นเรียนรู้';

      ctx.font = 'bold 24px "Kanit"';
      ctx.fillStyle = '#f093fb';
      ctx.fillText(badgeText, 500, 480);

      // Date
      const today = new Date().toLocaleDateString('th-TH', { 
        year: 'numeric', 
        month: 'long', 
        day: 'numeric' 
      });
      ctx.fillStyle = '#999';
      ctx.font = '14px "Kanit"';
      ctx.fillText(`ออกเมื่อ ${today}`, 500, 580);

      // Download
      canvas.toBlob(blob => {
        const url = window.URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `law-game-certificate-${score}.png`;
        document.body.appendChild(a);
        a.click();
        window.URL.revokeObjectURL(url);
        document.body.removeChild(a);

        // Show success message
        const existingToast = document.getElementById('cert-toast');
        if (existingToast) existingToast.remove();
        
        const toast = document.createElement('div');
        toast.id = 'cert-toast';
        toast.className = 'fixed bottom-4 left-4 right-4 bg-blue-500 text-white p-4 rounded-xl text-center shadow-lg z-50 slide-in';
        toast.innerHTML = '<p class="font-bold">📜 ดาวน์โหลดเกียรติบัตรแล้ว! สามารถแก้ไขชื่อของคุณได้ในภูมิ</p>';
        document.body.appendChild(toast);
        
        setTimeout(() => {
          toast.remove();
        }, 3000);
      });
    }

    // Initialize UI
    updateUI();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9d25387966f0d027',t:'MTc3MTgzMzk1Mi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

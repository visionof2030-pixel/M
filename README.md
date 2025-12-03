
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="اختبار الدراسات الإسلامية التفاعلي - موضوع الخوف والرجاء">
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>
<script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
<style>
/* جميع أنماط CSS السابقة تبقى كما هي */
:root {
/* نظام ألوان إسلامي هادئ */
--primary: #1A5F7A;
--primary-glow: #2D8F9D;
--primary-light: #57C3C2;

--accent: #159895;
--accent-glow: #1DB9B6;
--accent-light: #57C3C2;

--secondary: #4CAF50;
--secondary-glow: #66BB6A;
--secondary-light: #81C784;

--tertiary: #FF9800;
--tertiary-glow: #FFB74D;
--tertiary-light: #FFCC80;

--quaternary: #9C27B0;
--quaternary-glow: #BA68C8;
--quaternary-light: #CE93D8;

--islamic-green: #228B22;
--islamic-blue: #1A5F7A;
--islamic-gold: #D4AF37;
--islamic-teal: #159895;

/* جرادينتز إسلامية */
--primary-gradient: linear-gradient(135deg, var(--primary) 0%, var(--primary-glow) 50%, var(--primary-light) 100%);
--accent-gradient: linear-gradient(135deg, var(--accent) 0%, var(--accent-glow) 50%, var(--islamic-teal) 100%);
--secondary-gradient: linear-gradient(135deg, var(--secondary) 0%, var(--secondary-glow) 50%, var(--islamic-green) 100%);
--tertiary-gradient: linear-gradient(135deg, var(--tertiary) 0%, var(--tertiary-glow) 50%, var(--islamic-gold) 100%);
--islamic-gradient: linear-gradient(135deg, var(--islamic-blue) 0%, var(--islamic-teal) 50%, var(--islamic-green) 100%);

/* ظلال متوهجة */
--glow-primary: 0 0 20px rgba(26, 95, 122, 0.7), 0 0 40px rgba(26, 95, 122, 0.5), 0 0 60px rgba(26, 95, 122, 0.3);
--glow-accent: 0 0 20px rgba(21, 152, 149, 0.7), 0 0 40px rgba(21, 152, 149, 0.5), 0 0 60px rgba(21, 152, 149, 0.3);
--glow-secondary: 0 0 20px rgba(76, 175, 80, 0.7), 0 0 40px rgba(76, 175, 80, 0.5), 0 0 60px rgba(76, 175, 80, 0.3);
--glow-tertiary: 0 0 20px rgba(255, 152, 0, 0.7), 0 0 40px rgba(255, 152, 0, 0.5), 0 0 60px rgba(255, 152, 0, 0.3);
--glow-islamic: 0 0 20px rgba(26, 95, 122, 0.8), 0 0 40px rgba(21, 152, 149, 0.6), 0 0 60px rgba(34, 139, 34, 0.4);

/* متغيرات التصميم */
--bg: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
--card-bg: rgba(255, 255, 255, 0.95);
--text: #1F2937;
--light-text: #6B7280;
--border: rgba(26, 95, 122, 0.2);
--shadow: 0 8px 32px rgba(26, 95, 122, 0.1);
--shadow-hover: 0 20px 40px rgba(26, 95, 122, 0.2);
}

.dark-theme {
--bg: linear-gradient(135deg, #0A3D62 0%, #1A5F7A 100%);
--card-bg: rgba(15, 30, 45, 0.95);
--text: #F1F5F9;
--light-text: #CBD5E1;
--border: rgba(26, 95, 122, 0.1);
--shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
--shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.4);
}

/* بقية أنماط CSS تبقى كما هي بدون تغيير */
/* فقط تم تحديث الألوان لتناسب الطابع الإسلامي */

* {
box-sizing: border-box;
font-family: 'Tajawal', Tahoma, Arial, sans-serif;
margin: 0;
padding: 0;
}

body {
background: var(--bg);
color: var(--text);
line-height: 1.7;
overflow-x: hidden;
padding-top: 80px;
transition: all 0.5s ease;
min-height: 100vh;
}

/* Header بتصميم شفاف وجذاب */
header {
background: rgba(26, 95, 122, 0.1);
backdrop-filter: blur(20px);
color: white;
position: fixed;
top: 0;
width: 100%;
z-index: 1000;
box-shadow: var(--shadow);
border-bottom: 1px solid var(--border);
padding: 15px 0;
}

.header-container {
max-width: 1200px;
margin: 0 auto;
display: flex;
justify-content: space-between;
align-items: center;
padding: 0 20px;
}

.title-section h1 {
font-size: 1.5rem;
font-weight: 800;
background: var(--accent-gradient);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
text-shadow: 0 2px 10px rgba(26, 95, 122, 0.3);
}

.header-actions {
display: flex;
gap: 10px;
}

.theme-btn, .back-btn {
background: rgba(26, 95, 122, 0.2);
color: white;
border: 2px solid rgba(255, 255, 255, 0.3);
padding: 10px 20px;
border-radius: 15px;
font-weight: 600;
cursor: pointer;
transition: all 0.3s ease;
display: flex;
align-items: center;
gap: 8px;
backdrop-filter: blur(20px);
text-decoration: none;
position: relative;
overflow: hidden;
box-shadow: 0 0 15px rgba(26, 95, 122, 0.3);
}

.theme-btn:hover, .back-btn:hover {
background: rgba(26, 95, 122, 0.3);
transform: translateY(-3px);
box-shadow: 0 0 25px rgba(26, 95, 122, 0.5), 0 5px 20px rgba(0, 0, 0, 0.2);
border-color: rgba(255, 255, 255, 0.5);
}

/* Main Content */
main {
max-width: 1000px;
margin: 30px auto;
padding: 0 20px;
}

/* تحديث الهيرو سكشن */
.hero-section {
background: linear-gradient(135deg, rgba(26, 95, 122, 0.15), rgba(21, 152, 149, 0.15));
backdrop-filter: blur(30px);
color: white;
border-radius: 24px;
padding: 40px;
margin-bottom: 30px;
text-align: center;
position: relative;
overflow: hidden;
box-shadow: 0 20px 60px rgba(26, 95, 122, 0.15),
inset 0 1px 0 rgba(255, 255, 255, 0.2);
border: 2px solid rgba(255, 255, 255, 0.1);
}

.hero-section::before {
content: "";
position: absolute;
top: 0;
left: 0;
right: 0;
bottom: 0;
background: var(--accent-gradient);
opacity: 0.1;
z-index: -1;
}

.hero-content {
position: relative;
z-index: 1;
}

.hero-title {
font-size: 2.2rem;
font-weight: 800;
background: linear-gradient(135deg, #fff 0%, #f0f0f0 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}

.hero-subtitle {
font-size: 1.1rem;
margin-bottom: 25px;
opacity: 0.9;
max-width: 600px;
margin-left: auto;
margin-right: auto;
}

/* Cards بتصميم زجاجي */
.card {
background: rgba(255, 255, 255, 0.05);
backdrop-filter: blur(30px);
border-radius: 20px;
padding: 30px;
margin-bottom: 25px;
box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1),
inset 0 1px 0 rgba(255, 255, 255, 0.1);
transition: all 0.4s ease;
border: 1px solid rgba(255, 255, 255, 0.1);
position: relative;
overflow: hidden;
}

.card::before {
content: "";
position: absolute;
top: 0;
left: 0;
right: 0;
height: 5px;
background: var(--islamic-gradient);
}

.card:hover {
transform: translateY(-8px) scale(1.02);
box-shadow: var(--shadow-hover);
}

.section-title {
text-align: center;
color: var(--text);
margin-bottom: 30px;
font-size: 2rem;
font-weight: 800;
position: relative;
padding-bottom: 15px;
}

.section-title::after {
content: "";
position: absolute;
bottom: 0;
right: 50%;
transform: translateX(50%);
width: 100px;
height: 4px;
background: var(--accent-gradient);
border-radius: 2px;
}

/* تصميم الأسئلة */
.question-box {
background: var(--card-bg);
backdrop-filter: blur(20px);
padding: 30px;
margin-bottom: 25px;
border-radius: 20px;
box-shadow: var(--shadow);
border: 1px solid var(--border);
transition: all 0.4s ease;
position: relative;
overflow: hidden;
}

.question-box::before {
content: "";
position: absolute;
top: 0;
right: 0;
width: 100%;
height: 5px;
background: var(--primary-gradient);
}

.question-box:hover {
transform: translateY(-5px);
box-shadow: var(--shadow-hover);
}

.question-number {
font-size: 1.3em;
color: var(--primary);
margin-bottom: 15px;
font-weight: bold;
display: flex;
align-items: center;
gap: 10px;
}

.question-number i {
color: var(--accent);
font-size: 1.2em;
}

.question-text {
font-size: 1.2em;
margin-bottom: 25px;
line-height: 1.7;
color: var(--text);
font-weight: 500;
}

.options {
position: relative;
}

.options label {
display: flex;
align-items: center;
padding: 18px 20px;
margin: 12px 0;
border: 2px solid var(--border);
border-radius: 15px;
cursor: pointer;
transition: all 0.3s ease;
background: var(--card-bg);
position: relative;
overflow: hidden;
font-weight: 500;
}

.options label::before {
content: "";
position: absolute;
left: 0;
top: 0;
height: 100%;
width: 0;
background: var(--primary-gradient);
transition: width 0.3s ease;
z-index: 0;
}

.options label:hover:not(.locked) {
border-color: var(--primary);
transform: translateX(-8px);
box-shadow: 0 5px 15px rgba(26, 95, 122, 0.2);
}

.options label:hover:not(.locked)::before {
width: 4px;
}

.options input[type="radio"] {
margin-left: 12px;
transform: scale(1.3);
z-index: 1;
}

/* عندما تكون الإجابة مقفولة */
.options label.locked {
cursor: not-allowed;
opacity: 0.8;
pointer-events: none;
}

.options input[type="radio"]:disabled {
cursor: not-allowed;
}

.options label.selected {
background: linear-gradient(135deg, rgba(26, 95, 122, 0.15), rgba(21, 152, 149, 0.15));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(21, 152, 149, 0.3);
}

.options label.selected::before {
width: 6px;
background: var(--success-gradient);
}

.options label.correct-answer {
background: linear-gradient(135deg, rgba(76, 175, 80, 0.2), rgba(102, 187, 106, 0.2));
border: 2px solid var(--secondary);
box-shadow: 0 0 15px rgba(76, 175, 80, 0.3);
animation: correctPulse 0.5s ease;
}

@keyframes correctPulse {
0% { transform: scale(1); }
50% { transform: scale(1.02); }
100% { transform: scale(1); }
}

.options label.correct-answer::before {
width: 6px;
background: var(--secondary-gradient);
}

.options label.wrong-answer {
background: linear-gradient(135deg, rgba(21, 152, 149, 0.2), rgba(45, 143, 157, 0.2));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(21, 152, 149, 0.3);
animation: wrongShake 0.5s ease;
}

@keyframes wrongShake {
0%, 100% { transform: translateX(0); }
25% { transform: translateX(-5px); }
75% { transform: translateX(5px); }
}

.options label.wrong-answer::before {
width: 6px;
background: var(--accent-gradient);
}

.correct {
color: var(--secondary);
font-weight: bold;
}

.wrong {
color: var(--accent);
font-weight: bold;
}

.explanation {
margin-top: 25px;
padding: 25px;
border-radius: 15px;
display: none;
background: linear-gradient(135deg, rgba(26, 95, 122, 0.05), rgba(21, 152, 149, 0.05));
border-left: 4px solid var(--secondary);
animation: slideDown 0.5s ease;
backdrop-filter: blur(10px);
}

@keyframes slideDown {
from {
opacity: 0;
transform: translateY(-15px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.explanation-line {
padding: 15px;
margin: 10px 0;
border-radius: 10px;
transition: all 0.3s ease;
}

.explanation-correct {
background: linear-gradient(135deg, rgba(76, 175, 80, 0.1), rgba(102, 187, 106, 0.1));
border-right: 3px solid var(--secondary);
}

.explanation-wrong-1 {
background: linear-gradient(135deg, rgba(21, 152, 149, 0.1), rgba(45, 143, 157, 0.1));
border-right: 3px solid var(--accent);
}

.explanation-wrong-2 {
background: linear-gradient(135deg, rgba(255, 152, 0, 0.1), rgba(255, 183, 77, 0.1));
border-right: 3px solid var(--tertiary);
}

.explanation-wrong-3 {
background: linear-gradient(135deg, rgba(156, 39, 176, 0.1), rgba(186, 104, 200, 0.1));
border-right: 3px solid var(--quaternary);
}

/* تحديث تصميم الأزرار الرئيسية */
.btn-primary {
background: var(--accent-gradient);
color: white;
box-shadow: var(--glow-accent), 0 8px 25px rgba(21, 152, 149, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
position: relative;
overflow: hidden;
z-index: 1;
transition: all 0.4s ease;
}

.btn-primary::before {
content: '';
position: absolute;
top: 0;
left: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
transition: left 0.7s;
z-index: -1;
}

.btn-primary:hover {
transform: translateY(-8px) scale(1.05);
box-shadow: var(--glow-accent), 0 15px 40px rgba(21, 152, 149, 0.6);
border-color: rgba(255, 255, 255, 0.5);
}

.btn-primary:hover::before {
left: 100%;
}

.btn-primary:active {
transform: translateY(-4px) scale(1.02);
}

.btn-secondary {
background: var(--primary-gradient);
color: white;
box-shadow: var(--glow-primary), 0 8px 25px rgba(26, 95, 122, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
position: relative;
overflow: hidden;
z-index: 1;
}

.btn-secondary::before {
content: '';
position: absolute;
top: 0;
left: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
transition: left 0.7s;
z-index: -1;
}

.btn-secondary:hover {
transform: translateY(-8px) scale(1.05);
box-shadow: var(--glow-primary), 0 15px 40px rgba(26, 95, 122, 0.6);
border-color: rgba(255, 255, 255, 0.5);
}

.btn-secondary:hover::before {
left: 100%;
}

/* أزرار خاصة إضافية */
.btn-islamic {
background: var(--islamic-gradient);
color: white;
box-shadow: var(--glow-islamic), 0 8px 25px rgba(26, 95, 122, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
animation: islamic-pulse 2s infinite alternate;
}

@keyframes islamic-pulse {
0% {
box-shadow: var(--glow-islamic), 0 8px 25px rgba(26, 95, 122, 0.4);
}
100% {
box-shadow: 0 0 25px rgba(26, 95, 122, 0.8),
0 0 50px rgba(21, 152, 149, 0.6),
0 0 75px rgba(34, 139, 34, 0.4),
0 15px 40px rgba(26, 95, 122, 0.6);
}
}

.btn-success {
background: var(--secondary-gradient);
color: white;
box-shadow: var(--glow-secondary), 0 8px 25px rgba(76, 175, 80, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-warning {
background: var(--tertiary-gradient);
color: white;
box-shadow: var(--glow-tertiary), 0 8px 25px rgba(255, 152, 0, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
}

/* Navigation Buttons */
.navigation {
display: flex;
justify-content: space-between;
margin-top: 30px;
gap: 20px;
}

.btn {
padding: 15px 30px;
border-radius: 15px;
font-weight: 700;
text-decoration: none;
transition: all 0.3s ease;
display: inline-flex;
align-items: center;
gap: 10px;
font-size: 1rem;
border: none;
cursor: pointer;
position: relative;
overflow: hidden;
}

.btn::before {
content: "";
position: absolute;
top: 0;
left: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
transition: left 0.6s;
}

.btn:hover::before {
left: 100%;
}

.btn:disabled {
background: #9CA3AF;
cursor: not-allowed;
transform: none;
box-shadow: none;
opacity: 0.6;
}

.btn:disabled:hover::before {
left: -100%;
}

/* Progress Bar */
.progress-bar {
height: 15px;
background: rgba(255, 255, 255, 0.2);
border-radius: 10px;
margin-bottom: 30px;
overflow: hidden;
box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
position: relative;
backdrop-filter: blur(10px);
}

.progress {
height: 100%;
background: var(--islamic-gradient);
box-shadow: 0 0 15px rgba(26, 95, 122, 0.5);
width: 0%;
transition: width 0.5s ease;
border-radius: 10px;
position: relative;
overflow: hidden;
}

.progress::after {
content: "";
position: absolute;
top: 0;
left: -100%;
width: 100%;
height: 100%;
background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
animation: shimmer 1.5s infinite;
}

@keyframes shimmer {
0% { left: -100%; }
100% { left: 100%; }
}

/* Results Box */
#result-box {
background: var(--card-bg);
backdrop-filter: blur(20px);
padding: 30px;
margin-top: 30px;
border-radius: 20px;
box-shadow: var(--shadow);
border: 1px solid var(--border);
display: none;
animation: slideUp 0.6s ease;
}

@keyframes slideUp {
from {
opacity: 0;
transform: translateY(30px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.controls {
display: flex;
justify-content: space-between;
align-items: center;
margin-top: 30px;
flex-wrap: wrap;
gap: 20px;
}

.quiz-info {
font-size: 1rem;
color: var(--light-text);
background: linear-gradient(135deg, rgba(26, 95, 122, 0.1), rgba(21, 152, 149, 0.1));
padding: 10px 20px;
border-radius: 25px;
font-weight: 600;
backdrop-filter: blur(10px);
}

/* تحديث المؤقت */
#timer {
font-size: 1.1rem;
font-weight: bold;
color: white;
margin-left: 20px;
display: flex;
align-items: center;
gap: 8px;
background: rgba(26, 95, 122, 0.2);
backdrop-filter: blur(20px);
padding: 10px 20px;
border-radius: 25px;
border: 2px solid rgba(26, 95, 122, 0.3);
box-shadow: 0 0 15px rgba(26, 95, 122, 0.2);
}

.timer-warning {
background: rgba(255, 152, 0, 0.2) !important;
border-color: rgba(255, 152, 0, 0.3) !important;
box-shadow: 0 0 20px rgba(255, 152, 0, 0.3) !important;
animation: warning-pulse 0.8s infinite alternate;
}

@keyframes warning-pulse {
from {
box-shadow: 0 0 15px rgba(255, 152, 0, 0.3);
}
to {
box-shadow: 0 0 25px rgba(255, 152, 0, 0.5), 0 0 40px rgba(255, 152, 0, 0.3);
}
}

@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.05); }
100% { transform: scale(1); }
}

/* تحسينات للوضع الداكن */
.dark-theme {
--bg: linear-gradient(135deg, #0A3D62 0%, #1A5F7A 100%);
--card-bg: rgba(15, 30, 45, 0.95);
--text: #F1F5F9;
--light-text: #CBD5E1;
--border: rgba(26, 95, 122, 0.1);
--shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
--shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.4);
}

.dark-theme .btn-primary,
.dark-theme .btn-secondary {
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .theme-btn,
.dark-theme .back-btn {
background: rgba(26, 95, 122, 0.15);
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .card {
background: rgba(15, 30, 45, 0.7);
border-color: rgba(255, 255, 255, 0.05);
}

.dark-theme .hero-section {
background: linear-gradient(135deg, rgba(26, 95, 122, 0.1), rgba(21, 152, 149, 0.1));
border-color: rgba(255, 255, 255, 0.05);
}

/* Responsive Design */
@media (max-width: 768px) {
body {
padding-top: 70px;
}

.header-container {
padding: 0 15px;
flex-direction: column;
gap: 15px;
}

.title-section h1 {
font-size: 1.3rem;
}

.hero-title {
font-size: 1.8rem;
}

.hero-subtitle {
font-size: 1rem;
}

.card, .question-box {
padding: 25px;
}

.navigation {
flex-direction: column;
gap: 15px;
}

.btn {
width: 100%;
justify-content: center;
padding: 14px 25px;
font-size: 1rem;
}

.theme-btn, .back-btn {
padding: 8px 15px;
font-size: 0.9rem;
}

.controls {
flex-direction: column;
align-items: stretch;
}

}

@media (max-width: 480px) {
.header-container {
text-align: center;
}

.header-actions {
justify-content: center;
}

.question-box {
padding: 20px;
}

.options label {
padding: 15px;
}

.hero-section {
padding: 25px;
}

.section-title {
font-size: 1.6rem;
}
}

/* تأثيرات إضافية */
.fade-in {
animation: fadeIn 0.8s ease;
}

@keyframes fadeIn {
from {
opacity: 0;
transform: translateY(20px);
}
to {
opacity: 1;
transform: translateY(0);
}
}

.bounce-in {
animation: bounceIn 0.8s ease;
}

@keyframes bounceIn {
0% {
opacity: 0;
transform: scale(0.3);
}
50% {
opacity: 1;
transform: scale(1.05);
}
70% {
transform: scale(0.95);
}
100% {
opacity: 1;
transform: scale(1);
}
}

/* تأثيرات الجلاس مورفيزم */
.glass-effect {
background: rgba(255, 255, 255, 0.1);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.2);
}

/* رسوم متحركة للخلفية */
.bg-animation {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
z-index: -1;
opacity: 0.3;
}

.floating-shapes {
position: absolute;
width: 100%;
height: 100%;
}

.shape {
position: absolute;
background: var(--islamic-gradient);
opacity: 0.08;
filter: blur(40px);
border-radius: 50%;
animation: float 6s ease-in-out infinite;
}

.shape:nth-child(1) {
width: 100px;
height: 100px;
top: 10%;
left: 10%;
animation-delay: 0s;
}

.shape:nth-child(2) {
width: 150px;
height: 150px;
top: 60%;
right: 10%;
animation-delay: 2s;
}

.shape:nth-child(3) {
width: 80px;
height: 80px;
bottom: 20%;
left: 20%;
animation-delay: 4s;
}

@keyframes float {
0%, 100% {
transform: translateY(0) rotate(0deg);
}
50% {
transform: translateY(-20px) rotate(180deg);
}
}

/* تأثيرات إضافية للتفاعل */
.btn:focus {
outline: none;
animation: button-focus 0.3s ease;
}

@keyframes button-focus {
0% {
transform: scale(1);
}
50% {
transform: scale(1.05);
}
100% {
transform: scale(1);
}
}

/* تحسينات للرسوم البيانية */
.chart-container {
position: relative;
height: 300px;
margin: 30px 0;
background: var(--card-bg);
border-radius: 15px;
padding: 20px;
}

/* تحسينات لقسم النصائح */
.tips-container {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
gap: 20px;
margin: 30px 0;
}

.tip-card {
background: var(--card-bg);
border-radius: 15px;
padding: 25px;
transition: all 0.3s ease;
border-left: 5px solid var(--primary);
}

.tip-card:hover {
transform: translateY(-5px);
box-shadow: var(--shadow-hover);
}

.tip-card h4 {
color: var(--primary);
margin-bottom: 15px;
display: flex;
align-items: center;
gap: 10px;
}

/* طباعة الشهادة */
@media print {
body * {
visibility: hidden;
}

.certificate, .certificate * {
visibility: visible;
}

.certificate {
position: absolute;
left: 0;
top: 0;
width: 100%;
border: none;
box-shadow: none;
}

.no-print {
display: none !important;
}
}

/* النوافذ المنبثقة (مودال) */
.modal {
display: none;
position: fixed;
z-index: 2000;
left: 0;
top: 0;
width: 100%;
height: 100%;
background-color: rgba(0, 0, 0, 0.7);
backdrop-filter: blur(5px);
animation: fadeIn 0.3s ease;
}

.modal-content {
background: var(--card-bg);
margin: 5% auto;
padding: 30px;
border-radius: 20px;
width: 90%;
max-width: 600px;
max-height: 80vh;
overflow-y: auto;
box-shadow: var(--shadow-hover);
border: 1px solid var(--border);
position: relative;
animation: slideUp 0.5s ease;
}

.close-modal {
position: absolute;
left: 20px;
top: 20px;
color: var(--primary);
font-size: 28px;
font-weight: bold;
cursor: pointer;
width: 40px;
height: 40px;
display: flex;
align-items: center;
justify-content: center;
border-radius: 50%;
background: rgba(26, 95, 122, 0.1);
transition: all 0.3s ease;
}

.close-modal:hover {
background: rgba(26, 95, 122, 0.2);
transform: rotate(90deg);
}

.modal-header {
text-align: center;
margin-bottom: 25px;
padding-bottom: 15px;
border-bottom: 2px solid var(--border);
}

.modal-header h3 {
color: var(--text);
font-size: 1.8rem;
display: flex;
align-items: center;
justify-content: center;
gap: 12px;
}

/* تصميم شبكة الأسئلة في المودال */
#questions-grid-modal {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
gap: 12px;
margin: 25px 0;
}

.question-status-grid-modal {
width: 60px;
height: 60px;
border: 2px solid rgba(26, 95, 122, 0.3);
border-radius: 15px;
display: flex;
align-items: center;
justify-content: center;
cursor: pointer;
font-weight: 700;
transition: all 0.3s ease;
background: var(--card-bg);
position: relative;
overflow: hidden;
font-size: 1.1rem;
}

.question-status-grid-modal::before {
content: "";
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
background: var(--accent-gradient);
opacity: 0;
transition: opacity 0.3s ease;
}

.question-status-grid-modal:hover:not(.locked) {
transform: translateY(-3px) scale(1.1);
box-shadow: var(--shadow);
}

.question-status-grid-modal.current {
background: var(--accent-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-accent), 0 5px 15px rgba(21, 152, 149, 0.3);
animation: pulse 2s infinite;
}

.question-status-grid-modal.answered {
background: var(--secondary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-secondary), 0 5px 15px rgba(76, 175, 80, 0.3);
}

.question-status-grid-modal.flagged {
background: var(--tertiary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-tertiary), 0 5px 15px rgba(255, 152, 0, 0.3);
}

.question-status-grid-modal.locked {
cursor: not-allowed;
opacity: 0.7;
}

.legend-modal {
display: flex;
flex-wrap: wrap;
gap: 20px;
margin: 20px 0;
justify-content: center;
}

.legend-item-modal {
display: flex;
align-items: center;
gap: 10px;
font-size: 0.9rem;
}

/* تصميم عرض الدرجات في المودال */
.current-score-content {
text-align: center;
padding: 20px;
}

.score-circle {
width: 150px;
height: 150px;
margin: 20px auto;
position: relative;
}

.score-circle svg {
transform: rotate(-90deg);
}

.score-circle circle {
fill: none;
stroke-width: 10;
stroke-linecap: round;
}

.score-bg {
stroke: var(--border);
}

.score-fill {
stroke: var(--secondary);
stroke-dasharray: 314;
stroke-dashoffset: 314;
transition: stroke-dashoffset 1s ease;
}

.score-text {
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
font-size: 2rem;
font-weight: bold;
color: var(--secondary);
}

.score-details {
margin-top: 25px;
font-size: 1.1rem;
line-height: 1.8;
}

.score-details p {
margin: 10px 0;
}

/* تعديلات للأصوات */
.sound-controls {
display: flex;
align-items: center;
gap: 10px;
margin-top: 15px;
}

.sound-btn {
background: rgba(255, 255, 255, 0.1);
border: 1px solid rgba(255, 255, 255, 0.2);
border-radius: 50%;
width: 40px;
height: 40px;
display: flex;
align-items: center;
justify-content: center;
cursor: pointer;
color: white;
transition: all 0.3s ease;
}

.sound-btn:hover {
background: rgba(255, 255, 255, 0.2);
transform: scale(1.1);
}

.sound-btn.muted {
opacity: 0.5;
}

.sound-btn.muted i {
color: #ff6b6b;
}
</style>
</head>
<body>
<!-- رسوم متحركة للخلفية -->
<div class="bg-animation">
<div class="floating-shapes">
<div class="shape"></div>
<div class="shape"></div>
<div class="shape"></div>
</div>
</div>

<!-- Header -->
<header class="glass-effect">
<div class="header-container">
<div class="title-section">
<h1>اختبار الدراسات الإسلامية التفاعلي</h1>
</div>
<div class="header-actions">
<button class="theme-btn" id="themeBtn">
<i class="fas fa-moon"></i>
</button>
</div>
</div>
</header>

<!-- Main Content -->
<main>
<!-- Hero Section -->
<section class="hero-section glass-effect">
<div class="hero-content">
<h1 class="hero-title">اختبار الدراسات الإسلامية - الخوف والرجاء</h1>
<p class="hero-subtitle">اختبار شامل لموضوع الخوف والرجاء في الإسلام مع تفصيل الأحكام الشرعية وتغذية راجعة فورية</p>
<div class="quiz-info">عدد الأسئلة: 49 سؤالًا | الوقت المتاح: 49 دقيقة</div>
<div class="sound-controls">
<button class="sound-btn" id="soundToggleBtn" title="تشغيل/إيقاف الأصوات">
<i class="fas fa-volume-up"></i>
</button>
<span style="font-size: 0.9rem; opacity: 0.8;">الأصوات مفعلة</span>
</div>
</div>
</section>

<!-- Progress Bar -->
<div class="progress-bar glass-effect">
<div class="progress" id="progress"></div>
</div>

<!-- Quiz Container -->
<div id="quiz"></div>

<!-- Controls -->
<div class="controls">
<div class="quiz-info" id="quiz-info"></div>
<div id="timer">⏱️ <span id="time-display">49:00</span></div>
<div style="display: flex; gap: 15px; flex-wrap: wrap;">
<button class="btn btn-primary" onclick="openQuestionsModal()">
<i class="fas fa-list"></i>
قائمة الأسئلة
</button>
<button class="btn btn-warning" onclick="toggleMarkForReview()" id="mark-review-btn">
<i class="fas fa-flag"></i>
وضع علامة للمراجعة
</button>
<button class="btn btn-islamic" onclick="finishQuiz()">
<i class="fas fa-flag-checkered"></i>
إنهاء الاختبار
</button>
<button class="btn btn-secondary" onclick="openCurrentScoreModal()">
<i class="fas fa-chart-bar"></i>
الدرجات الحالية
</button>
</div>
</div>

<!-- Final Results -->
<div id="result-box" class="card">
<h3 id="result" style="color: var(--text); margin-bottom: 20px;"></h3>
<p id="percentage" style="font-size: 1.4rem; margin-bottom: 15px;"></p>
<p id="evaluation" style="font-weight: bold; font-size: 1.3rem;"></p>

<!-- قسم النتائج المتقدمة -->
<div id="advanced-results" style="display: none;">
<div class="chart-container">
<canvas id="performanceChart"></canvas>
</div>

<!-- قسم النصائح -->
<div class="tips-container" id="tips-container"></div>

<!-- قسم تحميل PDF -->
<div class="share-results">
<h4 style="color: var(--text); margin-bottom: 20px;">
<i class="fas fa-file-pdf"></i> تقرير النتائج
</h4>
<div class="share-buttons">
<button class="btn btn-success" onclick="generatePDF()">
<i class="fas fa-file-pdf"></i> تحميل تقرير PDF
</button>
<button class="btn btn-secondary" onclick="restartQuiz()">
<i class="fas fa-redo"></i> إعادة الاختبار
</button>
</div>
</div>
</div>
</div>
</main>

<!-- النافذة المنبثقة لعرض الدرجات الحالية -->
<div id="currentScoreModal" class="modal">
<div class="modal-content">
<span class="close-modal" onclick="closeCurrentScoreModal()">&times;</span>
<div class="modal-header">
<h3><i class="fas fa-chart-bar"></i> الدرجات الحالية</h3>
</div>
<div class="current-score-content">
<div class="score-circle">
<svg width="150" height="150">
<circle class="score-bg" cx="75" cy="75" r="70"></circle>
<circle class="score-fill" cx="75" cy="75" r="70" id="score-circle-fill"></circle>
</svg>
<div class="score-text" id="score-percentage">0%</div>
</div>
<div class="score-details">
<p id="current-score-details"></p>
<p id="current-correct-details"></p>
<p id="current-progress-details"></p>
</div>
</div>
</div>
</div>

<!-- النافذة المنبثقة لقائمة الأسئلة -->
<div id="questionsModal" class="modal">
<div class="modal-content">
<span class="close-modal" onclick="closeQuestionsModal()">&times;</span>
<div class="modal-header">
<h3><i class="fas fa-th-list"></i> قائمة الأسئلة</h3>
</div>
<div id="questions-grid-modal"></div>
<div class="legend-modal">
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--accent-gradient); color: white;"></div>
<span>السؤال الحالي</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--secondary-gradient); color: white;"></div>
<span>تمت الإجابة</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--tertiary-gradient); color: var(--text);"></div>
<span>معلم للمراجعة</span>
</div>
<div class="legend-item-modal">
<div class="question-status-grid-modal" style="background: var(--card-bg); border-color: var(--border);"></div>
<span>لم يتم الإجابة</span>
</div>
</div>
<button class="btn btn-primary" onclick="closeQuestionsModal()" style="margin-top:20px; width: 100%;">
<i class="fas fa-times"></i>
إغلاق القائمة
</button>
</div>
</div>

<script>
// مصفوفة أسئلة الدراسات الإسلامية (الخوف والرجاء)
const questions = [
{
"id": 1,
"q": "1️⃣ الخوف شرعًا هو عمل…",
"options": [
"قلبي يحث على الطاعة",
"بدني يتعلق بالأعمال",
"لساني يُظهر الأقوال",
"عقلي يحدد المصالح"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'قلبي يحث على الطاعة' لأن الخوف في الشرع عمل قلبي يؤثر على الجوارح ويحث على فعل الطاعات وترك المعاصي.",
"wrong1": "الخوف ليس عملًا بدنيًا بحتًا، بل هو عمل قلبي ينعكس على الأعمال.",
"wrong2": "الخوف ليس قولًا باللسان فقط، بل هو شعور قلبي يظهر في الأقوال والأفعال.",
"wrong3": "الخوف ليس مجرد تفكير عقلي، بل هو حالة قلبية لها أثر عملي."
}
},
{
"id": 2,
"q": "2️⃣ الخوف المحمود من الله يؤدي إلى…",
"options": [
"ترك الأوامر",
"ترك النواهي فقط",
"فعل الأوامر وترك النواهي",
"الغفلة عن الطاعة"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فعل الأوامر وترك النواهي' لأن الخوف المحمود من الله يحث العبد على الامتثال لأوامره واجتناب نواهيه.",
"wrong1": "الخوف المحمود لا يؤدي إلى ترك الأوامر بل إلى فعلها.",
"wrong2": "الخوف المحمود لا يؤدي إلى ترك النواهي فقط بل وفعل الأوامر أيضًا.",
"wrong3": "الخوف المحمود لا يؤدي إلى الغفلة بل إلى اليقظة والانتباه."
}
},
{
"id": 3,
"q": "3️⃣ من ثمرات الخوف من الله…",
"options": [
"زيادة اللهو",
"الوصول إلى الجنة",
"حب الدنيا",
"ترك الطاعات"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الوصول إلى الجنة' لأن الخوف من الله سبب لدخول الجنة كما قال تعالى: (وأما من خاف مقام ربه ونهى النفس عن الهوى فإن الجنة هي المأوى).",
"wrong1": "الخوف من الله لا يؤدي إلى زيادة اللهو بل إلى الجد والاجتهاد.",
"wrong2": "الخوف من الله لا يزيد حب الدنيا بل يزهد فيها.",
"wrong3": "الخوف من الله لا يؤدي إلى ترك الطاعات بل إلى الإكثار منها."
}
},
{
"id": 4,
"q": "4️⃣ الدليل على الخوف من الله ورد في قوله تعالى:",
"options": [
"اهدنا الصراط المستقيم",
"ولا تقتلوا النفس",
"فلا تخافوهم وخافون إن كنتم مؤمنين",
"إن الله غفور رحيم"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فلا تخافوهم وخافون إن كنتم مؤمنين' من سورة آل عمران الآية 175، وهي نص صريح في الأمر بخوف الله تعالى.",
"wrong1": "هذه آية من سورة الفاتحة ولا تتحدث عن الخوف.",
"wrong2": "هذه آية تحريم القتل ولا تتحدث عن الخوف من الله.",
"wrong3": "هذه آية تذكر صفتي المغفرة والرحمة ولا تتحدث عن الخوف."
}
},
{
"id": 5,
"q": "5️⃣ وعد الله من يخاف مقامه بـ…",
"options": [
"النار",
"المغفرة دون ثواب",
"الجنة",
"زيادة الرزق فقط"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الجنة' كما قال تعالى: (وأما من خاف مقام ربه ونهى النفس عن الهوى فإن الجنة هي المأوى).",
"wrong1": "الله لا يعد من يخافه بالنار بل بالجنة.",
"wrong2": "الوعد ليس بالمغفرة فقط بل بالجنة كاملة.",
"wrong3": "الوعد ليس بزيادة الرزق فقط بل بالجنة والمغفرة."
}
},
{
"id": 6,
"q": "6️⃣ الخوف من الأصنام يعد…",
"options": [
"توحيدًا",
"خوفًا طبيعيًا",
"عبادة لغير الله",
"خوفًا مباحًا"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'عبادة لغير الله' لأن الخوف من الأصنام خوف تعظيم وعبادة، وهذا شرك أكبر.",
"wrong1": "ليس توحيدًا بل شركًا لأن الخوف عبادة.",
"wrong2": "ليس خوفًا طبيعيًا بل خوف عبادة.",
"wrong3": "ليس مباحًا بل محرم لأنه شرك."
}
},
{
"id": 7,
"q": "7️⃣ الخوف الطبيعي مثاله…",
"options": [
"الخوف من النار",
"الخوف من الأموات",
"الخوف من الأصنام",
"الخوف من الحسد"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الخوف من النار' لأن النار مؤذية بطبيعتها، والخوف منها خوف طبيعي مباح.",
"wrong1": "الخوف من الأموات قد يكون شركيًا إذا اعتقد أن الميت يضر بنفسه.",
"wrong2": "الخوف من الأصنام شرك كما سبق.",
"wrong3": "الخوف من الحسد قد يكون وسواسًا إذا تجاوز الحد."
}
},
{
"id": 8,
"q": "8️⃣ من يخاف من الميت أن يضره فقد وقع في…",
"options": [
"الشرك",
"الطاعة",
"الزهد",
"التوكل"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الشرك' لأن الميت لا يملك لنفسه ضرًا ولا نفعًا، والخوف منه اعتقادًا بأنه يضر شرك.",
"wrong1": "ليس طاعة بل معصية وشرك.",
"wrong2": "ليس زهدًا بل جهل وشرك.",
"wrong3": "ليس توكلًا بل خوف باطل."
}
},
{
"id": 9,
"q": "9️⃣ الخوف الطبيعي يكون…",
"options": [
"مما لا يملكه إلا الله",
"مما يملكه البشر عادة",
"مما يملكه الأموات",
"مما تملكه الأصنام"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'مما يملكه البشر عادة' كالخوف من الأسد أو الحريق، فهذه أمور يملك البشر دفعها أو الاحتراز منها.",
"wrong1": "الخوف الطبيعي ليس مما لا يملكه إلا الله، بل مما يمكن للبشر التعامل معه.",
"wrong2": "الأموات لا يملكون شيئًا، فليس منهم خوف طبيعي.",
"wrong3": "الأصنام لا تملك شيئًا، فليس منها خوف طبيعي."
}
},
{
"id": 10,
"q": "🔟 مثال الخوف الطبيعي…",
"options": [
"الخوف من الجن",
"الخوف من الأسد",
"الخوف من الموتى",
"الخوف من المستقبل غيبًا"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الخوف من الأسد' لأنه حيوان مفترس يملك إيذاء الإنسان، فهذا خوف طبيعي مباح.",
"wrong1": "الخوف من الجن قد يكون شركيًا إذا اعتقد أن الجن يضر بنفسه.",
"wrong2": "الخوف من الموتى شرك كما تقدم.",
"wrong3": "الخوف المفرط من المستقبل نقص في التوكل."
}
},
{
"id": 11,
"q": "1️⃣1️⃣ من ثمرات الخوف من الله…",
"options": [
"يبعد عن الطاعات",
"يقود إلى المحرمات",
"يدفع إلى العمل الصالح",
"يزيد التكبر"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'يدفع إلى العمل الصالح' لأن الخوف من الله يحث العبد على فعل الطاعات واجتناب المعاصي.",
"wrong1": "الخوف من الله لا يبعد عن الطاعات بل يقرب منها.",
"wrong2": "الخوف من الله لا يقود إلى المحرمات بل يبعد عنها.",
"wrong3": "الخوف من الله لا يزيد التكبر بل يزيد التواضع."
}
},
{
"id": 12,
"q": "1️⃣2️⃣ يساعد على الخوف من الله…",
"options": [
"الغفلة",
"نسيان الآخرة",
"فهم أسماء الله وصفاته",
"ترك الذكر"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فهم أسماء الله وصفاته' لأن معرفة عظمة الله وقدرته وجبروته تزيد الخوف منه.",
"wrong1": "الغفلة تنقص الخوف من الله.",
"wrong2": "نسيان الآخرة يقلل الخوف من الله.",
"wrong3": "ترك الذكر يضعف الخوف من الله."
}
},
{
"id": 13,
"q": "1️⃣3️⃣ من أسماء الله التي تُعظّم الخوف…",
"options": [
"الكريم فقط",
"العليم والسميع والبصير",
"الودود وحده",
"الغني فقط"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'العليم والسميع والبصير' لأن هذه الأسماء تدل على إحاطة الله بكل شيء، فيخاف العبد أن يراه على معصية.",
"wrong1": "اسم الكريم يزيد الرجاء لا الخوف فقط.",
"wrong2": "اسم الودود يزيد المحبة لا الخوف فقط.",
"wrong3": "اسم الغني يزيد التوكل لا الخوف فقط."
}
},
{
"id": 14,
"q": "1️⃣4️⃣ تذكر مراقبة الله يعين على…",
"options": [
"الأمن من مكر الله",
"الجرأة على المعصية",
"زيادة الخوف منه",
"ترك الطاعات"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'زيادة الخوف منه' لأن تذكر أن الله يراك ويسمعك يزيد الخوف والحياء منه.",
"wrong1": "تذكر المراقبة لا يؤدي إلى الأمن من مكر الله بل يزيد الخوف منه.",
"wrong2": "تذكر المراقبة لا يزيد الجرأة بل يمنعها.",
"wrong3": "تذكر المراقبة لا يؤدي إلى ترك الطاعات بل إلى فعلها."
}
},
{
"id": 15,
"q": "1️⃣5️⃣ تعريف الرجاء هو طمع العبد في…",
"options": [
"متاع الدنيا",
"فضل الله ورحمته",
"رضا الناس",
"الثناء فقط"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فضل الله ورحمته' لأن الرجاء في الشرع: طمع العبد في فضل ربه ورحمته ومغفرته.",
"wrong1": "الرجاء الشرعي ليس في متاع الدنيا بل في الآخرة.",
"wrong2": "الرجاء ليس في رضا الناس بل في رضا الله.",
"wrong3": "الرجاء ليس في الثناء فقط بل في المغفرة والجنة."
}
},
{
"id": 16,
"q": "1️⃣6️⃣ الرجاء النافع يكون…",
"options": [
"بلا عمل",
"مع ترك الطاعات",
"مقرونًا بالعمل",
"مع اليأس"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'مقرونًا بالعمل' لأن الرجاء النافع هو الذي يصحبه عمل بطاعة الله، لا مجرد أماني.",
"wrong1": "الرجاء بلا عمل رجاء كاذب.",
"wrong2": "الرجاء مع ترك الطاعات رجاء باطل.",
"wrong3": "الرجاء مع اليأس متناقض، فلا يجتمعان."
}
},
{
"id": 17,
"q": "1️⃣7️⃣ الرجاء الكاذب هو…",
"options": [
"رجاء دون عمل",
"رجاء مع طاعة",
"رجاء محمود",
"رجاء الأنبياء"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'رجاء دون عمل' لأنه تمنٍ بلا فعل، وهو من الأماني الكاذبة.",
"wrong1": "الرجاء مع طاعة هو الرجاء النافع.",
"wrong2": "الرجاء الكاذب ليس محمودًا بل مذموم.",
"wrong3": "رجاء الأنبياء كان مقرونًا بالعمل فليس كاذبًا."
}
},
{
"id": 18,
"q": "1️⃣8️⃣ من ثمرات الرجاء…",
"options": [
"ترك العبادة",
"الكسل",
"الشعور بلذة العبادة",
"قطع الطاعات"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الشعور بلذة العبادة' لأن الرجاء يخفف على العبد مشقة الطاعة ويدفع له لذة فيها.",
"wrong1": "الرجاء لا يؤدي إلى ترك العبادة بل إلى فعلها.",
"wrong2": "الرجاء لا يؤدي إلى الكسل بل إلى النشاط.",
"wrong3": "الرجاء لا يؤدي إلى قطع الطاعات بل إلى المداومة عليها."
}
},
{
"id": 19,
"q": "1️⃣9️⃣ الدليل على الرجاء النافع قوله تعالى:",
"options": [
"ولا تقربوا الزنا",
"فليعمل عملًا صالحًا ولا يشرك بعبادة ربه أحدًا",
"كلوا من طيبات ما رزقناكم",
"لا يسخر قوم من قوم"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فليعمل عملًا صالحًا ولا يشرك بعبادة ربه أحدًا' من سورة الكهف الآية 110، وهي تجمع بين العمل والرجاء.",
"wrong1": "هذه آية نهي عن الزنا ولا تتحدث عن الرجاء.",
"wrong2": "هذه آية إباحة للأكل ولا تتحدث عن الرجاء.",
"wrong3": "هذه آية نهي عن السخرية ولا تتحدث عن الرجاء."
}
},
{
"id": 20,
"q": "2️⃣0️⃣ من ثمرات الرجاء…",
"options": [
"الحزن الشديد",
"السعادة",
"اليأس",
"الغرور"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'السعادة' لأن الرجاء يشرح الصدر ويسر القلب ويزيل الهم.",
"wrong1": "الرجاء لا يؤدي إلى الحزن الشديد بل يزيله.",
"wrong2": "الرجاء ينافي اليأس.",
"wrong3": "الرجاء لا يؤدي إلى الغرور بل إلى التواضع."
}
},
{
"id": 21,
"q": "2️⃣1️⃣ من يفعل عملًا صالحًا ويطمع بالأجر…",
"options": [
"مراءٍ",
"صاحب رجاء",
"مبتدع",
"متكاسل"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'صاحب رجاء' لأنه جمع بين العمل والطمع في ثواب الله، وهذا هو الرجاء النافع.",
"wrong1": "ليس مرائيًا لأنه يريد الأجر من الله لا مدح الناس.",
"wrong2": "ليس مبتدعًا إذا كان العمل موافقًا للسنة.",
"wrong3": "ليس متكاسلًا لأنه يعمل."
}
},
{
"id": 22,
"q": "2️⃣2️⃣ الخوف الذي يكون من الأسد يسمى…",
"options": [
"خوفًا شركيًا",
"خوفًا طبيعيًا",
"خوفًا ممنوعًا",
"خوفًا محرّمًا"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'خوفًا طبيعيًا' لأن الأسد حيوان مفترس يخشى منه على النفس، وهذا خوف فطري مباح.",
"wrong1": "ليس شركيًا لأنه لا تعظيم للأسد بل خوف من أذاه الطبيعي.",
"wrong2": "ليس ممنوعًا بل جائز.",
"wrong3": "ليس محرمًا بل مباح."
}
},
{
"id": 23,
"q": "2️⃣3️⃣ الخوف الذي لا يجوز هو…",
"options": [
"خوف من الحريق",
"خوف من الثعبان",
"خوف من الأموات",
"خوف من السيارة المسرعة"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'خوف من الأموات' إذا كان خوف تعظيم واعتقاد أن الميت يضر، فهذا شرك.",
"wrong1": "خوف من الحريق طبيعي وجائز.",
"wrong2": "خوف من الثعبان طبيعي وجائز.",
"wrong3": "خوف من السيارة المسرعة طبيعي وجائز."
}
},
{
"id": 24,
"q": "2️⃣4️⃣ من يخاف من السحر خوفًا يعتقد فيه الضرر بنفسه…",
"options": [
"موحّد",
"مبتدع",
"مشرك",
"متوكل"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'مشرك' لأن الخوف من السحر مع الاعتقاد أنه يضر بنفسه دون إذن الله شرك، فالله هو الضار النافع.",
"wrong1": "ليس موحدًا لأنه أشرك مع الله.",
"wrong2": "ليس مبتدعًا فقط بل قد يكون مشركًا.",
"wrong3": "ليس متوكلًا لأنه خاف من غير الله."
}
},
{
"id": 25,
"q": "2️⃣5️⃣ الخوف من الله يمنع العبد من…",
"options": [
"الحلال",
"النوافل",
"المحرمات",
"الطاعات"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'المحرمات' لأن الخوف من الله يردع العبد عن اقتراف المعاصي خوفًا من عقابه.",
"wrong1": "الخوف من الله لا يمنع من الحلال.",
"wrong2": "الخوف من الله لا يمنع من النوافل بل يحث عليها.",
"wrong3": "الخوف من الله لا يمنع من الطاعات بل يحث عليها."
}
},
{
"id": 26,
"q": "2️⃣6️⃣ ترك الكذب خوفًا من الله يُعد…",
"options": [
"خوفًا شركيًا",
"خوفًا طبيعيًا",
"خوفًا محمودًا",
"خوفًا كاذبًا"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'خوفًا محمودًا' لأنه خوف من الله دفع إلى ترك معصية، وهذا من الخوف المحمود.",
"wrong1": "ليس شركيًا لأنه خوف من الله.",
"wrong2": "ليس طبيعيًا بل شرعي.",
"wrong3": "ليس كاذبًا لأنه مقرون بفعل (ترك الكذب)."
}
},
{
"id": 27,
"q": "2️⃣7️⃣ يساعد على الخوف من الله…",
"options": [
"سماع الأغاني",
"معرفة عقوبات العصاة",
"ترك التدبر",
"تجاهل الآيات"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'معرفة عقوبات العصاة' لأنها تذكر بعذاب الله فتزيد الخوف منه.",
"wrong1": "سماع الأغاني ينقص الخوف من الله.",
"wrong2": "ترك التدبر ينقص الخوف من الله.",
"wrong3": "تجاهل الآيات ينقص الخوف من الله."
}
},
{
"id": 28,
"q": "2️⃣8️⃣ الرجاء النافع يقود العبد إلى…",
"options": [
"التضيع",
"ترك العمل",
"الطاعة",
"المعاصي"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الطاعة' لأن الرجاء النافع يحفز العبد على العمل الصالح طمعًا في ثواب الله.",
"wrong1": "لا يؤدي إلى التضييع بل إلى الجد.",
"wrong2": "لا يؤدي إلى ترك العمل بل إلى فعله.",
"wrong3": "لا يؤدي إلى المعاصي بل يبعد عنها."
}
},
{
"id": 29,
"q": "2️⃣9️⃣ الرجاء الكاذب نتيجته…",
"options": [
"السعادة",
"الغرور",
"المواظبة",
"الطاعة"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الغرور' لأنه يمني النفس بالأماني دون عمل فيغرر بها.",
"wrong1": "لا يؤدي إلى السعادة بل إلى الخيبة.",
"wrong2": "لا يؤدي إلى المواظبة بل إلى الكسل.",
"wrong3": "لا يؤدي إلى الطاعة بل إلى تركها."
}
},
{
"id": 30,
"q": "3️⃣0️⃣ من ثمرات الخوف والرجاء معًا…",
"options": [
"التوكل",
"الاعتدال في العبادة",
"الرياء",
"التكاسل"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الاعتدال في العبادة' لأن الجمع بينهما يمنع من القنوط والغرور فيكون العبد وسطًا.",
"wrong1": "التوكل ثمرة للإيمان ولكن ليس خاصًا بالخوف والرجاء.",
"wrong2": "الرياء ينافي الإخلاص وليس من ثمراتهما.",
"wrong3": "التكاسل ينافي العمل وليس من ثمراتهما."
}
},
{
"id": 31,
"q": "3️⃣1️⃣ العبد المؤمن يجمع بين…",
"options": [
"الغرور واليأس",
"الخوف والرجاء",
"القلق والحزن",
"الغفلة واللعب"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الخوف والرجاء' لأن المؤمن يخاف عذاب الله ويرجو رحمته، فهما جناحا العبادة.",
"wrong1": "الغرور واليأس صفتان مذمومتان لا يجتمعان في المؤمن.",
"wrong2": "القلق والحزن قد يعتريان المؤمن لكن ليسا من صفات العبادة.",
"wrong3": "الغفلة واللعب نقص في الإيمان."
}
},
{
"id": 32,
"q": "3️⃣2️⃣ من يخاف من الله ولا يعمل…",
"options": [
"عنده خوف محمود",
"عنده خوف كاذب",
"عنده رجاء صادق",
"عنده علم نافع"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'عنده خوف كاذب' لأن الخوف الحقيقي يدفع إلى العمل، فإذا لم يدفع فهو خوف كاذب.",
"wrong1": "الخوف المحمود مقرون بالعمل.",
"wrong2": "ليس عنده رجاء صادق بل خوف كاذب.",
"wrong3": "ليس بالضرورة عنده علم نافع."
}
},
{
"id": 33,
"q": "3️⃣3️⃣ من يعمل بلا رجاء يكون…",
"options": [
"مخلصًا دائمًا",
"قانطًا",
"صاحب أمل",
"مستقيمًا"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'قانطًا' لأنه عمل دون رجاء في ثواب الله، والقنوط من كبائر الذنوب.",
"wrong1": "قد يكون مخلصًا لكن ناقص الإيمان لفقده الرجاء.",
"wrong2": "ليس بالضرورة صاحب أمل لأنه بلا رجاء.",
"wrong3": "ليس مستقيمًا كاملًا لفقده الرجاء."
}
},
{
"id": 34,
"q": "3️⃣4️⃣ من أسباب زيادة الرجاء…",
"options": [
"الإكثار من الذنوب",
"معرفة فضل الله",
"كثرة الغفلة",
"ترك الصلاة"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'معرفة فضل الله' لأن معرفة سعة رحمة الله وعظيم عفوه تزيد الرجاء.",
"wrong1": "الإكثار من الذنوب قد يضعف الرجاء.",
"wrong2": "كثرة الغفلة تنقص الرجاء.",
"wrong3": "ترك الصلاة ينقص الرجاء والإيمان."
}
},
{
"id": 35,
"q": "3️⃣5️⃣ الرجاء النافع يدفع إلى…",
"options": [
"السعي للطاعات",
"الكسل",
"اللهو",
"التهاون"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'السعي للطاعات' لأنه يحفز العبد على العمل الصالح طمعًا في الثواب.",
"wrong1": "لا يؤدي إلى الكسل بل إلى النشاط.",
"wrong2": "لا يؤدي إلى اللهو بل إلى الجد.",
"wrong3": "لا يؤدي إلى التهاون بل إلى الاجتهاد."
}
},
{
"id": 36,
"q": "3️⃣6️⃣ الخوف الذي يختص بالله يسمى…",
"options": [
"خوفًا طبيعيًا",
"خوفًا قدرًا",
"خوف عبادة",
"خوف عادة"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'خوف عبادة' لأنه خوف تعظيم وإجلال، وهو من العبادات القلبية التي لا تصرف إلا لله.",
"wrong1": "الخوف الطبيعي لا يختص بالله.",
"wrong2": "الخوف قدرًا يعني الخوف من المقدر لا يختص بالله.",
"wrong3": "الخوف عادة لا يختص بالله."
}
},
{
"id": 37,
"q": "3️⃣7️⃣ الخوف من الأموات يدخل في…",
"options": [
"التوحيد",
"العبادة لغير الله",
"الخوف الطبيعي",
"الإيمان الواجب"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'العبادة لغير الله' إذا كان خوف تعظيم، لأن الميت لا يملك ضرًا ولا نفعًا.",
"wrong1": "ليس من التوحيد بل من الشرك.",
"wrong2": "ليس خوفًا طبيعيًا لأن الميت لا يؤذي بطبيعته.",
"wrong3": "ليس من الإيمان الواجب بل يناقضه."
}
},
{
"id": 38,
"q": "3️⃣8️⃣ من يخاف ضرر الجن اعتمادًا عليهم…",
"options": [
"مؤمن كامل",
"متوكل",
"مشرك",
"مستقيم"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'مشرك' لأنه خاف من مخلوق واعتمد عليه في الضر معتقدًا أنه يضره بنفسه دون الله.",
"wrong1": "ليس مؤمنًا كاملًا بل ناقص الإيمان أو مشرك.",
"wrong2": "ليس متوكلًا لأنه توكل على غير الله.",
"wrong3": "ليس مستقيمًا لأنه حاد عن التوحيد."
}
},
{
"id": 39,
"q": "3️⃣9️⃣ الخوف الطبيعي يكون سببه…",
"options": [
"قدرة المخلوق",
"قدرة الله",
"علم الشياطين",
"اعتقاد في الأموات"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'قدرة المخلوق' الطبيعية كقدرة الأسد على الإيذاء، أو النار على الحرق.",
"wrong1": "الخوف الطبيعي ليس بسبب قدرة الله بل قدرة المخلوق الطبيعية.",
"wrong2": "ليس بسبب علم الشياطين.",
"wrong3": "ليس بسبب اعتقاد في الأموات."
}
},
{
"id": 40,
"q": "4️⃣0️⃣ من أمثلة الرجاء النافع…",
"options": [
"فعل الطاعة مع نية الثواب",
"انتظار المغفرة دون عمل",
"ترك الصلاة رجاء الجنة",
"العمل للناس فقط"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'فعل الطاعة مع نية الثواب' لأنه جمع بين العمل والرجاء.",
"wrong1": "انتظار المغفرة دون عمل رجاء كاذب.",
"wrong2": "ترك الصلاة معصية ولا يكون رجاء مع معصية.",
"wrong3": "العمل للناس رياء لا رجاء."
}
},
{
"id": 41,
"q": "4️⃣1️⃣ الشعور بالسعادة أثناء الطاعة نتيجة…",
"options": [
"الغرور",
"الرجاء",
"اليأس",
"التكاسل"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الرجاء' لأن الرجاء بثواب الله يخفف مشقة الطاعة ويجعلها محببة للنفس.",
"wrong1": "الغرور ينافي الإخلاص ولا يؤدي إلى السعادة الحقيقية.",
"wrong2": "اليأس يسبب الحزن لا السعادة.",
"wrong3": "التكاسل ينافي الطاعة."
}
},
{
"id": 42,
"q": "4️⃣2️⃣ من يخاف من صوت مزعج يكون خوفه…",
"options": [
"ممنوعًا",
"طبيعيًا",
"شركيًا",
"بدعيًا"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'طبيعيًا' لأن الصوت المزعج يؤذي السمع، والخوف منه خوف فطري.",
"wrong1": "ليس ممنوعًا إذا لم يصل إلى حد الوسواس.",
"wrong2": "ليس شركيًا لأنه لا تعظيم للصوت.",
"wrong3": "ليس بدعيًا لأنه ليس متعلقًا بالدين."
}
},
{
"id": 43,
"q": "4️⃣3️⃣ الخوف الذي يؤدي لترك المعاصي…",
"options": [
"مذموم",
"كاذب",
"محمود",
"لا علاقة له بالطاعة"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'محمود' لأنه خوف من الله دفع إلى ترك المعصية، وهذا من ثمرات الخوف المحمود.",
"wrong1": "ليس مذمومًا بل محمود.",
"wrong2": "ليس كاذبًا لأنه أثر عنه فعل (ترك المعصية).",
"wrong3": "له علاقة بالطاعة لأنه دفع لترك المعصية."
}
},
{
"id": 44,
"q": "4️⃣4️⃣ فهم أسماء الله يساعد على…",
"options": [
"زيادة الغفلة",
"تقوية الخوف",
"اليأس من الرحمة",
"ترك التوبة"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'تقوية الخوف' لأن معرفة أسماء الله مثل المنتقم الجبار تزيد خوف العبد من عقابه.",
"wrong1": "لا تزيد الغفلة بل تزيلها.",
"wrong2": "لا تسبب اليأس بل تزيد الرجاء أيضًا.",
"wrong3": "لا تؤدي إلى ترك التوبة بل تحث عليها."
}
},
{
"id": 45,
"q": "4️⃣5️⃣ الرجاء الكاذب يعتمد على…",
"options": [
"العمل",
"الطاعة",
"الأماني الفارغة",
"الإخلاص"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الأماني الفارغة' لأنه تمنٍ بلا عمل، وهو رجاء باطل.",
"wrong1": "الرجاء الكاذب لا يعتمد على العمل.",
"wrong2": "لا يعتمد على الطاعة.",
"wrong3": "لا يعتمد على الإخلاص."
}
},
{
"id": 46,
"q": "4️⃣6️⃣ الخوف الذي يكون من أخطار محسوسة…",
"options": [
"شركًا",
"طبيعيًا",
"محرّمًا",
"بدعيًا"
],
"answer": 1,
"explanations": {
"correct": "الإجابة الصحيحة هي 'طبيعيًا' كالخوف من السقوط من مكان مرتفع، أو من حيوان مفترس.",
"wrong1": "ليس شركًا إذا لم يكن خوف تعظيم.",
"wrong2": "ليس محرمًا إذا كان ضمن الحد المعقول.",
"wrong3": "ليس بدعيًا لأنه ليس متعلقًا بالدين."
}
},
{
"id": 47,
"q": "4️⃣7️⃣ من يخاف المستقبل غيبًا خوفًا مفرطًا…",
"options": [
"مشرك",
"مذنب",
"غير متوكل",
"موحّد"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'غير متوكل' لأنه نقص في التوكل على الله وتسليم الأمور له.",
"wrong1": "ليس مشركًا لأنه لا تعظيم لغير الله.",
"wrong2": "ليس مذنبًا بذنب معين لكنه ناقص التوكل.",
"wrong3": "موحد لكن ناقص التوكل."
}
},
{
"id": 48,
"q": "4️⃣8️⃣ من ثمرات الرجاء…",
"options": [
"الإكثار من الصالحات",
"ترك الأعمال",
"الشعور باليأس",
"القلق الدائم"
],
"answer": 0,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الإكثار من الصالحات' لأن الرجاء يحفز العبد على العمل الصالح طمعًا في الثواب.",
"wrong1": "لا يؤدي إلى ترك الأعمال بل إلى فعلها.",
"wrong2": "ينافي اليأس.",
"wrong3": "لا يؤدي إلى القلق بل يزيله."
}
},
{
"id": 49,
"q": "4️⃣9️⃣ كمال الإيمان يكون بـ…",
"options": [
"الخوف فقط",
"الرجاء فقط",
"الجمع بين الخوف والرجاء",
"ترك الخوف والرجاء"
],
"answer": 2,
"explanations": {
"correct": "الإجابة الصحيحة هي 'الجمع بين الخوف والرجاء' لأن الإيمان الكامل يجمع بين الخوف من عقاب الله والرجاء في رحمته.",
"wrong1": "الخوف فقط قد يؤدي إلى القنوط.",
"wrong2": "الرجاء فقط قد يؤدي إلى الغرور.",
"wrong3": "تركهما نقص في الإيمان."
}
}
];

let currentQuestionIndex = 0;
let userAnswers = Array(questions.length).fill(null);
let timeLeft = 49 * 60; // 49 دقيقة للاختبار
let timerInterval;
let markedQuestions = [];
let answerLocked = Array(questions.length).fill(false);
let performanceHistory = [];
let shuffledQuestions = [];
let soundEnabled = true;

// نظام صوتي محسن
class SoundManager {
    constructor() {
        this.audioContext = null;
        this.sounds = new Map();
        this.isInitialized = false;
        this.initializing = false;
    }

    async init() {
        if (this.isInitialized || this.initializing) return;
        
        this.initializing = true;
        
        try {
            // إنشاء AudioContext
            this.audioContext = new (window.AudioContext || window.webkitAudioContext)();
            
            // تحميل الأصوات الرئيسية
            await this.loadSound('correct', 'https://media.vocaroo.com/mp3/19lcrilHKuHR');
            await this.loadSound('wrong', 'https://media.vocaroo.com/mp3/1ooZTr9sHVXS');
            await this.loadSound('finish', 'https://assets.mixkit.co/sfx/preview/mixkit-winning-chimes-2015.mp3');
            
            // تحميل الأصوات الإضافية من مصادر موثوقة وسريعة
            await this.loadSoundEffect('click', 'https://assets.mixkit.co/sfx/preview/mixkit-select-click-1109.mp3');
            await this.loadSoundEffect('hover', 'https://assets.mixkit.co/sfx/preview/mixkit-hover-click-1198.mp3');
            await this.loadSoundEffect('pageTurn', 'https://assets.mixkit.co/sfx/preview/mixkit-book-page-turn-1180.mp3');
            await this.loadSoundEffect('success', 'https://assets.mixkit.co/sfx/preview/mixkit-winning-chimes-2015.mp3');
            await this.loadSoundEffect('error', 'https://assets.mixkit.co/sfx/preview/mixkit-wrong-answer-fail-notification-946.mp3');
            
            this.isInitialized = true;
            console.log('نظام الصوت جاهز للاستخدام');
        } catch (error) {
            console.error('خطأ في تهيئة نظام الصوت:', error);
            // استعداد بدائي إذا فشل التحميل
            this.createFallbackSounds();
        } finally {
            this.initializing = false;
        }
    }

    async loadSound(name, url) {
        try {
            const response = await fetch(url);
            const arrayBuffer = await response.arrayBuffer();
            const audioBuffer = await this.audioContext.decodeAudioData(arrayBuffer);
            this.sounds.set(name, audioBuffer);
        } catch (error) {
            console.warn(`تعذر تحميل الصوت ${name}:`, error);
        }
    }

    async loadSoundEffect(name, url) {
        try {
            const response = await fetch(url);
            const arrayBuffer = await response.arrayBuffer();
            const audioBuffer = await this.audioContext.decodeAudioData(arrayBuffer);
            this.sounds.set(name, audioBuffer);
        } catch (error) {
            console.warn(`تعذر تحميل المؤثر الصوتي ${name}:`, error);
        }
    }

    createFallbackSounds() {
        // إنشاء أصوات احتياطية بسيطة
        this.sounds.set('click', this.generateBeep(440, 0.1));
        this.sounds.set('hover', this.generateBeep(220, 0.05));
        this.sounds.set('correct', this.generateBeep(523.25, 0.3)); // C5
        this.sounds.set('wrong', this.generateBeep(349.23, 0.3)); // F4
    }

    generateBeep(frequency, duration) {
        if (!this.audioContext) return null;
        
        const oscillator = this.audioContext.createOscillator();
        const gainNode = this.audioContext.createGain();
        
        oscillator.connect(gainNode);
        gainNode.connect(this.audioContext.destination);
        
        oscillator.frequency.value = frequency;
        oscillator.type = 'sine';
        
        gainNode.gain.setValueAtTime(0, this.audioContext.currentTime);
        gainNode.gain.linearRampToValueAtTime(0.1, this.audioContext.currentTime + 0.01);
        gainNode.gain.exponentialRampToValueAtTime(0.001, this.audioContext.currentTime + duration);
        
        return { oscillator, gainNode, duration };
    }

    play(name, volume = 0.5) {
        if (!soundEnabled || !this.isInitialized) return;
        
        try {
            if (this.audioContext.state === 'suspended') {
                this.audioContext.resume();
            }
            
            const sound = this.sounds.get(name);
            
            if (sound) {
                if (sound.oscillator) {
                    // الصوت المنشأ برمجيًا
                    const { oscillator, gainNode, duration } = sound;
                    
                    oscillator.start();
                    setTimeout(() => {
                        oscillator.stop();
                    }, duration * 1000);
                    
                    // إعادة إنشاء الصوت للاستخدام المستقبلي
                    this.sounds.set(name, this.generateBeep(
                        oscillator.frequency.value,
                        duration
                    ));
                } else {
                    // الصوت المحمل مسبقًا
                    const source = this.audioContext.createBufferSource();
                    const gainNode = this.audioContext.createGain();
                    
                    source.buffer = sound;
                    gainNode.gain.value = volume;
                    
                    source.connect(gainNode);
                    gainNode.connect(this.audioContext.destination);
                    
                    source.start(0);
                    
                    // تنظيف الذاكرة بعد انتهاء الصوت
                    source.onended = () => {
                        source.disconnect();
                        gainNode.disconnect();
                    };
                }
            }
        } catch (error) {
            console.warn(`تعذر تشغيل الصوت ${name}:`, error);
        }
    }

    playCorrect() {
        this.play('correct', 0.3);
    }

    playWrong() {
        this.play('wrong', 0.3);
    }

    playFinish() {
        this.play('finish', 0.5);
    }

    playClick() {
        this.play('click', 0.2);
    }

    playHover() {
        this.play('hover', 0.1);
    }

    playPageTurn() {
        this.play('pageTurn', 0.2);
    }

    playSuccess() {
        this.play('success', 0.3);
    }

    playError() {
        this.play('error', 0.3);
    }
}

// إنشاء مدير الصوت
const soundManager = new SoundManager();

// دالة لترتيب الخيارات بشكل عشوائي
function shuffleOptions(question) {
    // إنشاء نسخة من الخيارات
    const options = [...question.options];
    const answer = question.answer;
    
    // ترتيب الخيارات عشوائياً
    const shuffledIndices = [...Array(options.length).keys()];
    for (let i = shuffledIndices.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [shuffledIndices[i], shuffledIndices[j]] = [shuffledIndices[j], shuffledIndices[i]];
    }
    
    // إنشاء الخيارات الجديدة مع الحفاظ على الإجابة الصحيحة
    const shuffledOptions = shuffledIndices.map(idx => options[idx]);
    const newAnswer = shuffledIndices.indexOf(answer);
    
    return {
        ...question,
        options: shuffledOptions,
        answer: newAnswer
    };
}

// تحميل سجل الأداء السابق من localStorage
function loadPerformanceHistory() {
    const savedHistory = localStorage.getItem('islamicStudiesPerformanceHistory');
    if (savedHistory) {
        try {
            performanceHistory = JSON.parse(savedHistory);
        } catch (e) {
            performanceHistory = [];
        }
    }
}

// حفظ سجل الأداء إلى localStorage
function savePerformanceHistory() {
    localStorage.setItem('islamicStudiesPerformanceHistory', JSON.stringify(performanceHistory));
}

// تشغيل الصوت المحسن
function playSound(soundName) {
    if (!soundEnabled) return;
    
    switch(soundName) {
        case 'click':
            soundManager.playClick();
            break;
        case 'hover':
            soundManager.playHover();
            break;
        case 'pageTurn':
            soundManager.playPageTurn();
            break;
        case 'success':
            soundManager.playSuccess();
            break;
        case 'error':
            soundManager.playError();
            break;
    }
}

// تشغيل الصوت الصحيح
function playCorrectSound() {
    if (soundEnabled) {
        soundManager.playCorrect();
    }
}

// تشغيل الصوت الخاطئ
function playWrongSound() {
    if (soundEnabled) {
        soundManager.playWrong();
    }
}

// تشغيل صوت النهاية
function playFinishSound() {
    if (soundEnabled) {
        soundManager.playFinish();
    }
}

// تبديل الوضع الليلي
document.getElementById('themeBtn').addEventListener('click', function() {
    playSound('click');
    document.body.classList.toggle('dark-theme');
    const icon = this.querySelector('i');
    if (document.body.classList.contains('dark-theme')) {
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
        localStorage.setItem('darkMode', 'enabled');
    } else {
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
        localStorage.setItem('darkMode', 'disabled');
    }
});

// التحقق من تفضيل الوضع الداكن المخزن
function checkDarkModePreference() {
    const darkMode = localStorage.getItem('darkMode');
    const icon = document.querySelector('#themeBtn i');

    if (darkMode === 'enabled') {
        document.body.classList.add('dark-theme');
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
    } else {
        document.body.classList.remove('dark-theme');
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
    }
}

// تبديل تشغيل/إيقاف الصوت
document.getElementById('soundToggleBtn').addEventListener('click', function() {
    soundEnabled = !soundEnabled;
    const icon = this.querySelector('i');
    const statusText = this.nextElementSibling;
    
    if (soundEnabled) {
        icon.classList.remove('fa-volume-mute');
        icon.classList.add('fa-volume-up');
        this.classList.remove('muted');
        statusText.textContent = 'الأصوات مفعلة';
        playSound('click');
    } else {
        icon.classList.remove('fa-volume-up');
        icon.classList.add('fa-volume-mute');
        this.classList.add('muted');
        statusText.textContent = 'الأصوات معطلة';
    }
    
    localStorage.setItem('soundEnabled', soundEnabled);
});

// المؤقت
function startTimer() {
    timerInterval = setInterval(() => {
        timeLeft--;
        updateTimerDisplay();

        // تشغيل صوت تنبيه عند الـ 5 دقائق الأخيرة
        if (timeLeft === 5 * 60) {
            playSound('error');
        }
        
        // تشغيل صوت تنبيه كل دقيقة في الدقائق الخمس الأخيرة
        if (timeLeft < 5 * 60 && timeLeft % 60 === 0) {
            playSound('click');
        }

        if (timeLeft <= 0) {
            clearInterval(timerInterval);
            playSound('error');
            finishQuiz();
        }
    }, 1000);
}

function updateTimerDisplay() {
    const minutes = Math.floor(timeLeft / 60);
    const seconds = timeLeft % 60;
    const timeDisplay = document.getElementById('time-display');
    timeDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;

    if (timeLeft < 300) { // 5 دقائق
        timeDisplay.classList.add('timer-warning');
    } else {
        timeDisplay.classList.remove('timer-warning');
    }
}

// فتح نافذة الدرجات الحالية
function openCurrentScoreModal() {
    playSound('click');
    const score = calculateScore();
    const answeredCount = userAnswers.filter(answer => answer !== null).length;
    const totalQuestions = questions.length;
    const percentage = totalQuestions > 0 ? ((score.correct / totalQuestions) * 100).toFixed(2) : 0;
    
    // تحديث دائرة الدرجات
    const circle = document.getElementById('score-circle-fill');
    const text = document.getElementById('score-percentage');
    const circumference = 440; // 2 * π * r (r = 70)
    const offset = circumference - (percentage / 100) * circumference;
    
    circle.style.strokeDashoffset = offset;
    text.textContent = `${percentage}%`;
    
    // تحديث تفاصيل الدرجات
    document.getElementById('current-score-details').innerHTML = 
        `<strong>الدرجة الحالية:</strong> ${score.correct} من ${totalQuestions}`;
    document.getElementById('current-correct-details').innerHTML = 
        `<strong>الإجابات الصحيحة:</strong> ${score.correct}`;
    document.getElementById('current-progress-details').innerHTML = 
        `<strong>التقدم:</strong> ${answeredCount} من ${totalQuestions} (${Math.round((answeredCount/totalQuestions)*100)}%)`;
    
    // عرض النافذة المنبثقة
    document.getElementById('currentScoreModal').style.display = 'block';
}

function closeCurrentScoreModal() {
    playSound('click');
    document.getElementById('currentScoreModal').style.display = 'none';
}

// فتح نافذة قائمة الأسئلة
function openQuestionsModal() {
    playSound('click');
    const grid = document.getElementById('questions-grid-modal');
    grid.innerHTML = '';

    questions.forEach((_, index) => {
        const btn = document.createElement('div');
        btn.className = `question-status-grid-modal ${index === currentQuestionIndex ? 'current' : ''} ${userAnswers[index] !== null ? 'answered' : ''} ${markedQuestions.includes(index) ? 'flagged' : ''}`;
        btn.innerHTML = `<span>${index + 1}</span>`;
        btn.onclick = () => {
            playSound('click');
            currentQuestionIndex = index;
            loadQuiz();
            closeQuestionsModal();
        };
        grid.appendChild(btn);
    });

    document.getElementById('questionsModal').style.display = 'block';
}

function closeQuestionsModal() {
    playSound('click');
    document.getElementById('questionsModal').style.display = 'none';
}

// وضع علامة للمراجعة
function toggleMarkForReview() {
    playSound('click');
    const index = markedQuestions.indexOf(currentQuestionIndex);
    const btn = document.getElementById('mark-review-btn');

    if (index === -1) {
        markedQuestions.push(currentQuestionIndex);
        btn.innerHTML = '<i class="fas fa-flag"></i> إزالة العلامة';
        btn.style.background = 'var(--tertiary-gradient)';
    } else {
        markedQuestions.splice(index, 1);
        btn.innerHTML = '<i class="fas fa-flag"></i> وضع علامة للمراجعة';
        btn.style.background = 'var(--secondary-gradient)';
    }
}

// إضافة مؤثرات صوتية للخيارات
function addSoundToOptions() {
    document.querySelectorAll('.options label').forEach(label => {
        label.addEventListener('mouseenter', () => {
            if (!label.classList.contains('locked')) {
                playSound('hover');
            }
        });
    });
}

// تحميل الاختبار
function loadQuiz() {
    const quizDiv = document.getElementById("quiz");

    // إذا لم يتم ترتيب الأسئلة بعد، قم بترتيبها
    if (shuffledQuestions.length === 0) {
        shuffledQuestions = questions.map(q => shuffleOptions(q));
    }
    
    const question = shuffledQuestions[currentQuestionIndex];
    const isLocked = answerLocked[currentQuestionIndex];

    let html = `
    <div class="question-box fade-in">
        <div class="question-number">
            <i class="fas fa-question-circle"></i>
            السؤال ${currentQuestionIndex + 1} من ${questions.length}
            ${isLocked ? '<span style="color: var(--accent); margin-right: 10px;"><i class="fas fa-lock"></i> مقفل</span>' : ''}
            ${markedQuestions.includes(currentQuestionIndex) ? '<span style="background: var(--tertiary-gradient); color: white; padding: 5px 10px; border-radius: 10px; font-size: 0.8rem; margin-right: 10px;"><i class="fas fa-flag"></i> معلمة</span>' : ''}
        </div>
        <div class="question-text">${question.q}</div>
        <div class="options">
    `;

    question.options.forEach((opt, i) => {
        const isChecked = userAnswers[currentQuestionIndex] === i;
        const isDisabled = isLocked;
        let labelClass = '';

        if (isLocked) {
            labelClass = 'locked';
            if (isChecked) {
                labelClass += userAnswers[currentQuestionIndex] === question.answer ? ' correct-answer' : ' wrong-answer';
            } else if (i === question.answer) {
                labelClass += ' correct-answer';
            }
        } else if (isChecked) {
            labelClass = 'selected';
        }

        html += `
        <label class="${labelClass}">
            <input type="radio" name="q${currentQuestionIndex}" value="${i}" ${isChecked ? 'checked' : ''} ${isDisabled ? 'disabled' : ''} onchange="selectAnswer(${i})" ${isLocked ? 'onclick="return false;"' : ''}>
            ${opt}
            ${isLocked && i === question.answer ? ' <i class="fas fa-check" style="color: var(--secondary); margin-right: 5px;"></i>' : ''}
        </label>
        `;
    });

    html += `
        </div>
        <div id="explanation" class="explanation"></div>
    </div>
    <div class="navigation">
        <button class="btn btn-secondary" onclick="previousQuestion()" ${currentQuestionIndex === 0 ? 'disabled' : ''}>
            <i class="fas fa-arrow-right"></i>
            السابق
        </button>
        <button class="btn btn-primary" onclick="nextQuestion()" ${currentQuestionIndex === questions.length - 1 ? 'disabled' : ''}>
            التالي
            <i class="fas fa-arrow-left"></i>
        </button>
    </div>
    `;

    quizDiv.innerHTML = html;

    // تحديث شريط التقدم
    const progress = document.getElementById('progress');
    progress.style.width = questions.length > 0 ? `${((currentQuestionIndex + 1) / questions.length) * 100}%` : '0%';

    // تحديث معلومات الاختبار
    document.getElementById('quiz-info').innerHTML = `السؤال ${currentQuestionIndex + 1} من ${questions.length}`;

    // تحديث زر وضع العلامة
    const markBtn = document.getElementById('mark-review-btn');
    if (markedQuestions.includes(currentQuestionIndex)) {
        markBtn.innerHTML = '<i class="fas fa-flag"></i> إزالة العلامة';
        markBtn.style.background = 'var(--tertiary-gradient)';
    } else {
        markBtn.innerHTML = '<i class="fas fa-flag"></i> وضع علامة للمراجعة';
        markBtn.style.background = 'var(--secondary-gradient)';
    }

    // إضافة المؤثرات الصوتية للخيارات الجديدة
    setTimeout(() => {
        addSoundToOptions();
    }, 100);

    // عرض الشرح إذا كان المستخدم قد أجاب على السؤال
    if (userAnswers[currentQuestionIndex] !== null) {
        showExplanation();
    }
}

// اختيار إجابة - مقفل بعد الاختيار
function selectAnswer(answerIndex) {
    // إذا كان السؤال مقفولاً بالفعل، لا تفعل شيئاً
    if (answerLocked[currentQuestionIndex]) {
        return;
    }

    // تشغيل صوت النقر
    playSound('click');
    
    userAnswers[currentQuestionIndex] = answerIndex;
    answerLocked[currentQuestionIndex] = true;

    // تشغيل الصوت المناسب
    const question = shuffledQuestions[currentQuestionIndex];
    if (answerIndex === question.answer) {
        playCorrectSound();
        playSound('success');
    } else {
        playWrongSound();
        playSound('error');
    }

    // تعطيل جميع خيارات الراديو في السؤال الحالي
    const radioInputs = document.querySelectorAll(`input[name="q${currentQuestionIndex}"]`);
    radioInputs.forEach(input => {
        input.disabled = true;
    });

    // إضافة فئة locked لجميع labels
    const labels = document.querySelectorAll(`input[name="q${currentQuestionIndex}"]`);
    labels.forEach(input => {
        input.closest('label').classList.add('locked');
    });

    // إظهار الشرح والتغذية الراجعة
    showExplanation();
}

// عرض الشرح
function showExplanation() {
    const question = shuffledQuestions[currentQuestionIndex];
    const explanationDiv = document.getElementById("explanation");
    const userAnswer = userAnswers[currentQuestionIndex];

    if (userAnswer !== null) {
        explanationDiv.style.display = "block";

        let resultHTML = "";

        if (userAnswer === question.answer) {
            resultHTML = `<p class="correct"><i class="fas fa-check-circle"></i> إجابة صحيحة! أحسنت!</p>`;
        } else {
            resultHTML = `
            <p class="wrong"><i class="fas fa-times-circle"></i> إجابة خاطئة — الإجابة الصحيحة: <span class="correct">${question.options[question.answer]}</span></p>
            `;
        }

        // إضافة الشروح الملونة
        resultHTML += `
        <div class="explanation-line explanation-correct"><strong>📚 التفسير الصحيح:</strong> ${questions[currentQuestionIndex].explanations.correct}</div>
        `;

        // إضافة التفسيرات للخيارات الخاطئة
        const wrongKeys = ['wrong1', 'wrong2', 'wrong3'];

        wrongKeys.forEach((key, index) => {
            if (questions[currentQuestionIndex].explanations[key]) {
                resultHTML += `<div class="explanation-line explanation-wrong-${index + 1}"><strong>💡 ملاحظة:</strong> ${questions[currentQuestionIndex].explanations[key]}</div>`;
            }
        });

        explanationDiv.innerHTML = resultHTML;
    }
}

// الانتقال إلى السؤال التالي
function nextQuestion() {
    playSound('pageTurn');
    if (currentQuestionIndex < questions.length - 1) {
        currentQuestionIndex++;
        loadQuiz();
    }
}

// الانتقال إلى السؤال السابق
function previousQuestion() {
    playSound('pageTurn');
    if (currentQuestionIndex > 0) {
        currentQuestionIndex--;
        loadQuiz();
    }
}

// إنشاء الرسم البياني للأداء
function createPerformanceChart() {
    loadPerformanceHistory();
    const ctx = document.getElementById('performanceChart').getContext('2d');
    const dates = performanceHistory.map(attempt => {
        const date = new Date(attempt.date);
        return `${date.getDate()}/${date.getMonth() + 1}`;
    });
    const scores = performanceHistory.map(attempt => attempt.percentage);

    // إضافة الدرجة الحالية إلى الرسم البياني
    const currentScore = calculateScore().percentage;
    dates.push("الآن");
    scores.push(currentScore);

    // تدمير الرسم البياني القديم إذا كان موجودًا
    if (window.performanceChartInstance) {
        window.performanceChartInstance.destroy();
    }

    window.performanceChartInstance = new Chart(ctx, {
        type: 'line',
        data: {
            labels: dates,
            datasets: [{
                label: 'النسبة المئوية %',
                data: scores,
                borderColor: 'rgba(26, 95, 122, 1)',
                backgroundColor: 'rgba(26, 95, 122, 0.1)',
                borderWidth: 3,
                fill: true,
                tension: 0.4
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    display: true,
                    position: 'top',
                    labels: {
                        color: 'var(--text)',
                        font: {
                            family: 'Tajawal',
                            size: 14
                        }
                    }
                }
            },
            scales: {
                y: {
                    beginAtZero: true,
                    max: 100,
                    ticks: {
                        color: 'var(--text)',
                        callback: function(value) {
                            return value + '%';
                        },
                        font: {
                            family: 'Tajawal',
                            size: 12
                        }
                    },
                    grid: {
                        color: 'rgba(255, 255, 255, 0.1)'
                    }
                },
                x: {
                    ticks: {
                        color: 'var(--text)',
                        font: {
                            family: 'Tajawal',
                            size: 12
                        }
                    },
                    grid: {
                        color: 'rgba(255, 255, 255, 0.1)'
                    }
                }
            }
        }
    });
}

// إنشاء النصائح المخصصة
function createCustomTips() {
    const score = calculateScore();
    const tipsContainer = document.getElementById('tips-container');
    let tipsHTML = '';

    if (score.percentage >= 90) {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-star"></i> أداء ممتاز!</h4>
            <p>أداؤك رائع في موضوع الخوف والرجاء! لديك فهم قوي للأحكام الشرعية المتعلقة بهذا الباب الهام من أبواب العقيدة.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-lightbulb"></i> نصائح للمستوى المتقدم</h4>
            <p>يمكنك الآن التوسع في دراسة كتب العقيدة المتقدمة مثل كتاب "الخوف والرجاء" من مجموع الفتاوى لابن تيمية.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-book"></i> الخطوة التالية</h4>
            <p>ابدأ في دراسة الموازنة بين الخوف والرجاء في حياة السلف الصالح وكيفية تطبيق ذلك عمليًا.</p>
        </div>
        `;
    } else if (score.percentage >= 70) {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-check-circle"></i> أداء جيد</h4>
            <p>أداؤك جيد، ركز على الأسئلة التي واجهت صعوبة فيها، خاصة التمييز بين أنواع الخوف المختلفة.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-book-open"></i> مراجعة مركزة</h4>
            <p>راجع جيدًا الفروق بين: الخوف الطبيعي والخوف الشركي، والرجاء النافع والرجاء الكاذب.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-clock"></i> تحسين الفهم</h4>
            <p>ادرس الأمثلة العملية لكل نوع من أنواع الخوف والرجاء لترسخ المعلومة.</p>
        </div>
        `;
    } else {
        tipsHTML = `
        <div class="tip-card">
            <h4><i class="fas fa-exclamation-triangle"></i> يحتاج تحسين</h4>
            <p>أنت بحاجة إلى مراجعة شاملة لموضوع الخوف والرجاء، فهو من أساسيات العقيدة الإسلامية.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-graduation-cap"></i> الأساسيات أولاً</h4>
            <p>ابدأ بتعلم: تعريف الخوف والرجاء، أنواع كل منهما، الأحكام الشرعية، والأدلة من القرآن والسنة.</p>
        </div>
        <div class="tip-card">
            <h4><i class="fas fa-redo"></i> الممارسة المستمرة</h4>
            <p>كرر الاختبار بعد دراسة الموضوع من مصادره الأصلية لمتابعة تطور مستواك.</p>
        </div>
        `;
    }

    tipsContainer.innerHTML = tipsHTML;
}

// حساب الدرجات
function calculateScore() {
    let totalCorrect = 0;
    userAnswers.forEach((answer, index) => {
        // استخدام السؤال الأصلي (غير المرتب) للتحقق من الإجابة الصحيحة
        if (answer === questions[index]?.answer) {
            totalCorrect++;
        }
    });

    const total = questions.length;
    const percentage = total > 0 ? ((totalCorrect / total) * 100).toFixed(2) : 0;

    let evaluation = "";
    let evaluationIcon = "";
    if (percentage >= 90) {
        evaluation = "ممتاز - فهم تام للموضوع";
        evaluationIcon = "🌟";
    } else if (percentage >= 80) {
        evaluation = "جيد جداً - إلمام جيد بالأحكام";
        evaluationIcon = "🔵";
    } else if (percentage >= 70) {
        evaluation = "جيد - فهم مقبول يحتاج لبعض التحسين";
        evaluationIcon = "🟢";
    } else if (percentage >= 60) {
        evaluation = "مقبول - تحتاج لمراجعة إضافية";
        evaluationIcon = "🟡";
    } else {
        evaluation = "يحتاج تحسين - راجع الموضوع جيداً";
        evaluationIcon = "⚠️";
    }

    return {
        correct: totalCorrect,
        total: total,
        percentage: parseFloat(percentage),
        evaluation: evaluation,
        evaluationIcon: evaluationIcon
    };
}

// حفظ سجل الأداء
function savePerformanceRecord() {
    const score = calculateScore();
    performanceHistory.push({
        date: new Date().toISOString(),
        score: score.correct,
        total: score.total,
        percentage: score.percentage
    });

    // الحفاظ على آخر 10 محاولات فقط
    if (performanceHistory.length > 10) {
        performanceHistory = performanceHistory.slice(-10);
    }

    savePerformanceHistory();
}

// إنشاء تقرير PDF
function generatePDF() {
    playSound('click');
    const score = calculateScore();
    const answeredCount = userAnswers.filter(answer => answer !== null).length;
    
    // إنشاء محتوى PDF
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF();
    
    // إعداد الخط العربي
    doc.addFont('https://fonts.gstatic.com/s/tajawal/v9/Iurf6YBj_oCad4k1l_6gLrZjiLlJ.ttf', 'Tajawal', 'normal');
    doc.setFont('Tajawal');
    doc.setR2L(true);
    
    // العنوان
    doc.setFontSize(24);
    doc.setTextColor(26, 95, 122);
    doc.text('تقرير نتائج اختبار الدراسات الإسلامية', 105, 20, null, null, 'center');
    
    doc.setFontSize(16);
    doc.setTextColor(21, 152, 149);
    doc.text('موضوع: الخوف والرجاء في الإسلام', 105, 30, null, null, 'center');
    
    doc.setFontSize(12);
    doc.setTextColor(100, 100, 100);
    doc.text(`تاريخ الاختبار: ${new Date().toLocaleDateString('ar-SA')}`, 105, 40, null, null, 'center');
    
    // خط فاصل
    doc.setDrawColor(26, 95, 122);
    doc.setLineWidth(0.5);
    doc.line(20, 45, 190, 45);
    
    // النتائج الرئيسية
    doc.setFontSize(18);
    doc.setTextColor(30, 30, 30);
    doc.text('النتائج الرئيسية', 20, 60);
    
    doc.setFontSize(14);
    doc.text(`الدرجة النهائية: ${score.correct} من ${score.total}`, 20, 75);
    doc.text(`النسبة المئوية: ${score.percentage}%`, 20, 85);
    doc.text(`التقييم: ${score.evaluation}`, 20, 95);
    doc.text(`عدد الأسئلة المجابة: ${answeredCount} من ${questions.length}`, 20, 105);
    doc.text(`الوقت المستغرق: ${(49 - (timeLeft / 60)).toFixed(2)} دقيقة من 49 دقيقة`, 20, 115);
    
    // تفاصيل الإجابات
    doc.setFontSize(18);
    doc.text('تفاصيل الإجابات', 20, 135);
    
    doc.setFontSize(12);
    let yPos = 150;
    let pageNumber = 1;
    
    for (let i = 0; i < questions.length; i++) {
        if (yPos > 270) {
            doc.addPage();
            yPos = 20;
            pageNumber++;
            doc.setFontSize(10);
            doc.text(`صفحة ${pageNumber}`, 105, 290, null, null, 'center');
            doc.setFontSize(12);
        }
        
        const status = userAnswers[i] === null ? 'لم يتم الإجابة' : 
                      (userAnswers[i] === questions[i].answer ? 'صحيح' : 'خاطئ');
        const statusColor = userAnswers[i] === null ? [150, 150, 150] : 
                           (userAnswers[i] === questions[i].answer ? [76, 175, 80] : [239, 68, 68]);
        
        doc.setTextColor(statusColor[0], statusColor[1], statusColor[2]);
        doc.text(`سؤال ${i+1}: ${status}`, 20, yPos);
        yPos += 10;
    }
    
    // نصائح بناءً على النتيجة
    doc.addPage();
    doc.setFontSize(18);
    doc.setTextColor(30, 30, 30);
    doc.text('نصائح للتحسين', 20, 20);
    
    doc.setFontSize(12);
    doc.setTextColor(80, 80, 80);
    
    let tips = [];
    if (score.percentage >= 90) {
        tips = [
            'ممتاز! لديك فهم قوي لموضوع الخوف والرجاء.',
            'يمكنك الآن التوسع في دراسة كتب العقيدة المتقدمة.',
            'ركز على التطبيق العملي لموازنة الخوف والرجاء في حياتك اليومية.',
            'احرص على تعليم الآخرين هذا الباب الهام من أبواب العقيدة.'
        ];
    } else if (score.percentage >= 70) {
        tips = [
            'أداؤك جيد، يمكنك تحسينه بالمزيد من المراجعة.',
            'راجع جيدًا الفروق بين أنواع الخوف المختلفة.',
            'تأمل في الأمثلة العملية للخوف المحمود والخوف المذموم.',
            'ادرس الأدلة القرآنية والنبوية المتعلقة بالخوف والرجاء.'
        ];
    } else {
        tips = [
            'أنت بحاجة إلى مراجعة شاملة لموضوع الخوف والرجاء.',
            'ابدأ بتعلم التعريفات الأساسية والأحكام الشرعية.',
            'افهم جيدًا الفرق بين الخوف الطبيعي والخوف الشركي.',
            'تأكد من فهمك لشروط الرجاء النافع وأمثلته.'
        ];
    }
    
    yPos = 35;
    tips.forEach(tip => {
        doc.text(`• ${tip}`, 20, yPos);
        yPos += 15;
    });
    
    // مصادر للدراسة
    doc.setFontSize(16);
    doc.setTextColor(26, 95, 122);
    doc.text('مصادر مقترحة للدراسة:', 20, yPos + 10);
    
    doc.setFontSize(12);
    doc.setTextColor(80, 80, 80);
    const sources = [
        'كتاب "القواعد المثلى" لابن عثيمين',
        'كتاب "التوحيد" للشيخ صالح الفوزان',
        'شرح "ثلاثة الأصول" للشيخ ابن باز',
        'كتاب "الخوف والرجاء" من مجموع الفتاوى لابن تيمية'
    ];
    
    yPos += 25;
    sources.forEach(source => {
        doc.text(`- ${source}`, 20, yPos);
        yPos += 12;
    });
    
    // تذييل الصفحة
    doc.setFontSize(10);
    doc.setTextColor(150, 150, 150);
    doc.text('تم إنشاء هذا التقرير تلقائيًا من نظام الاختبارات التفاعلية', 105, 290, null, null, 'center');
    
    // حفظ الملف
    doc.save(`نتيجة-اختبار-الخوف-والرجاء-${new Date().toISOString().slice(0,10)}.pdf`);
    
    alert('تم إنشاء وتحميل تقرير PDF بنجاح!');
}

// إعادة تشغيل الاختبار
function restartQuiz() {
    playSound('pageTurn');
    
    // إعادة تعيين جميع المتغيرات
    currentQuestionIndex = 0;
    userAnswers = Array(questions.length).fill(null);
    timeLeft = 49 * 60;
    markedQuestions = [];
    answerLocked = Array(questions.length).fill(false);
    shuffledQuestions = [];

    // إعادة تعيين العرض
    document.getElementById("quiz").style.display = "block";
    document.querySelector(".controls").style.display = "flex";
    document.getElementById("result-box").style.display = "none";

    // إعادة تحميل المؤقت
    clearInterval(timerInterval);
    startTimer();

    // إعادة تحميل الاختبار
    loadQuiz();

    // تحديث المؤقت
    updateTimerDisplay();
}

// إنهاء الاختبار
function finishQuiz() {
    clearInterval(timerInterval);

    const score = calculateScore();

    // حفظ سجل الأداء
    savePerformanceRecord();

    // تشغيل صوت النهاية
    playFinishSound();
    playSound('success');

    // عرض النتائج
    document.getElementById("result-box").style.display = "block";
    document.getElementById("result").innerHTML = `${score.evaluationIcon} النتيجة: ${score.correct} من ${score.total}`;
    document.getElementById("percentage").innerHTML = `النسبة المئوية: ${score.percentage}%`;
    document.getElementById("evaluation").innerHTML = `التقييم: ${score.evaluation}`;

    // إخفاء الاختبار
    document.getElementById("quiz").style.display = "none";
    document.querySelector(".controls").style.display = "none";

    // عرض النتائج المتقدمة
    document.getElementById('advanced-results').style.display = 'block';

    // إنشاء الرسوم البيانية والنصائح
    setTimeout(() => {
        createPerformanceChart();
        createCustomTips();
    }, 100);
}

// إضافة مؤثرات صوتية للأزرار
document.addEventListener('DOMContentLoaded', function() {
    document.querySelectorAll('.btn').forEach(button => {
        button.addEventListener('click', () => {
            playSound('click');
        });
        
        button.addEventListener('mouseenter', () => {
            if (!button.disabled) {
                playSound('hover');
            }
        });
    });
});

// بدء التحميل الأولي
window.onload = async function() {
    checkDarkModePreference();
    loadPerformanceHistory();
    
    // تحميل تفضيلات الصوت
    const savedSoundSetting = localStorage.getItem('soundEnabled');
    if (savedSoundSetting !== null) {
        soundEnabled = savedSoundSetting === 'true';
    }
    
    // تحديث أيقونة الصوت
    const soundBtn = document.getElementById('soundToggleBtn');
    const soundIcon = soundBtn.querySelector('i');
    const soundStatus = soundBtn.nextElementSibling;
    
    if (soundEnabled) {
        soundIcon.classList.remove('fa-volume-mute');
        soundIcon.classList.add('fa-volume-up');
        soundBtn.classList.remove('muted');
        soundStatus.textContent = 'الأصوات مفعلة';
    } else {
        soundIcon.classList.remove('fa-volume-up');
        soundIcon.classList.add('fa-volume-mute');
        soundBtn.classList.add('muted');
        soundStatus.textContent = 'الأصوات معطلة';
    }
    
    // تهيئة نظام الصوت
    await soundManager.init();
    
    loadQuiz();
    startTimer();

    // إضافة تأثيرات عند التحميل
    document.querySelector('.hero-section').classList.add('bounce-in');
    setTimeout(() => {
        if (document.querySelector('.card')) {
            document.querySelector('.card').classList.add('fade-in');
        }
    }, 300);
    
    // إغلاق النوافذ المنبثقة عند النقر خارجها
    window.onclick = function(event) {
        const currentScoreModal = document.getElementById('currentScoreModal');
        const questionsModal = document.getElementById('questionsModal');
        
        if (event.target == currentScoreModal) {
            currentScoreModal.style.display = 'none';
        }
        
        if (event.target == questionsModal) {
            questionsModal.style.display = 'none';
        }
    }
}
</script>
</body>
</html>

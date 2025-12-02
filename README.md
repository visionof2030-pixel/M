<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="اختبار الرخصة المهنية التفاعلي للمعلمين - إعداد المعلم فهد الخالدي">
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>
<script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
<style>
:root {
/* نظام ألوان متوهج ومشرق */
--primary: #3B82F6;
--primary-glow: #60A5FA;
--primary-light: #93C5FD;

--accent: #6366F1;
--accent-glow: #8B5CF6;
--accent-light: #A78BFA;

--secondary: #10B981;
--secondary-glow: #34D399;
--secondary-light: #6EE7B7;

--tertiary: #F59E0B;
--tertiary-glow: #FBBF24;
--tertiary-light: #FCD34D;

--quaternary: #8B5CF6;
--quaternary-glow: #A78BFA;
--quaternary-light: #C4B5FD;

--neon-blue: #00D4FF;
--neon-purple: #A855F7;
--neon-green: #00FF9D;
--neon-yellow: #FFD700;
--neon-pink: #FF0080;

/* جرادينتز جديدة متوهجة */
--primary-gradient: linear-gradient(135deg, var(--primary) 0%, var(--primary-glow) 50%, var(--primary-light) 100%);
--accent-gradient: linear-gradient(135deg, var(--accent) 0%, var(--accent-glow) 50%, var(--neon-purple) 100%);
--secondary-gradient: linear-gradient(135deg, var(--secondary) 0%, var(--secondary-glow) 50%, var(--neon-green) 100%);
--tertiary-gradient: linear-gradient(135deg, var(--tertiary) 0%, var(--tertiary-glow) 50%, var(--neon-yellow) 100%);
--neon-gradient: linear-gradient(135deg, var(--neon-blue) 0%, var(--neon-purple) 50%, var(--neon-pink) 100%);

/* ظلال متوهجة */
--glow-primary: 0 0 20px rgba(59, 130, 246, 0.7), 0 0 40px rgba(59, 130, 246, 0.5), 0 0 60px rgba(59, 130, 246, 0.3);
--glow-accent: 0 0 20px rgba(99, 102, 241, 0.7), 0 0 40px rgba(99, 102, 241, 0.5), 0 0 60px rgba(99, 102, 241, 0.3);
--glow-secondary: 0 0 20px rgba(16, 185, 129, 0.7), 0 0 40px rgba(16, 185, 129, 0.5), 0 0 60px rgba(16, 185, 129, 0.3);
--glow-tertiary: 0 0 20px rgba(245, 158, 11, 0.7), 0 0 40px rgba(245, 158, 11, 0.5), 0 0 60px rgba(245, 158, 11, 0.3);
--glow-neon: 0 0 20px rgba(0, 212, 255, 0.8), 0 0 40px rgba(168, 85, 247, 0.6), 0 0 60px rgba(255, 0, 128, 0.4);

/* متغيرات التصميم */
--bg: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
--card-bg: rgba(255, 255, 255, 0.95);
--text: #1F2937;
--light-text: #6B7280;
--border: rgba(59, 130, 246, 0.2);
--shadow: 0 8px 32px rgba(59, 130, 246, 0.1);
--shadow-hover: 0 20px 40px rgba(59, 130, 246, 0.2);
}

.dark-theme {
--bg: linear-gradient(135deg, #1E3A8A 0%, #1E40AF 100%);
--card-bg: rgba(30, 41, 59, 0.95);
--text: #F1F5F9;
--light-text: #CBD5E1;
--border: rgba(59, 130, 246, 0.1);
--shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
--shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.4);
}

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
background: rgba(59, 130, 246, 0.1);
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
text-shadow: 0 2px 10px rgba(59, 130, 246, 0.3);
}

.header-actions {
display: flex;
gap: 10px;
}

.theme-btn, .back-btn {
background: rgba(59, 130, 246, 0.2);
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
box-shadow: 0 0 15px rgba(59, 130, 246, 0.3);
}

.theme-btn:hover, .back-btn:hover {
background: rgba(59, 130, 246, 0.3);
transform: translateY(-3px);
box-shadow: 0 0 25px rgba(59, 130, 246, 0.5), 0 5px 20px rgba(0, 0, 0, 0.2);
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
background: linear-gradient(135deg, rgba(59, 130, 246, 0.15), rgba(99, 102, 241, 0.15));
backdrop-filter: blur(30px);
color: white;
border-radius: 24px;
padding: 40px;
margin-bottom: 30px;
text-align: center;
position: relative;
overflow: hidden;
box-shadow: 0 20px 60px rgba(59, 130, 246, 0.15),
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
background: var(--neon-gradient);
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
box-shadow: 0 5px 15px rgba(59, 130, 246, 0.2);
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
background: linear-gradient(135deg, rgba(59, 130, 246, 0.15), rgba(139, 92, 246, 0.15));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(99, 102, 241, 0.3);
}

.options label.selected::before {
width: 6px;
background: var(--success-gradient);
}

.options label.correct-answer {
background: linear-gradient(135deg, rgba(16, 185, 129, 0.2), rgba(52, 211, 153, 0.2));
border: 2px solid var(--secondary);
box-shadow: 0 0 15px rgba(16, 185, 129, 0.3);
}

.options label.correct-answer::before {
width: 6px;
background: var(--secondary-gradient);
}

.options label.wrong-answer {
background: linear-gradient(135deg, rgba(99, 102, 241, 0.2), rgba(139, 92, 246, 0.2));
border: 2px solid var(--accent);
box-shadow: 0 0 15px rgba(99, 102, 241, 0.3);
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
background: linear-gradient(135deg, rgba(59, 130, 246, 0.05), rgba(99, 102, 241, 0.05));
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
background: linear-gradient(135deg, rgba(16, 185, 129, 0.1), rgba(52, 211, 153, 0.1));
border-right: 3px solid var(--secondary);
}

.explanation-wrong-1 {
background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.1));
border-right: 3px solid var(--accent);
}

.explanation-wrong-2 {
background: linear-gradient(135deg, rgba(245, 158, 11, 0.1), rgba(251, 191, 36, 0.1));
border-right: 3px solid var(--tertiary);
}

.explanation-wrong-3 {
background: linear-gradient(135deg, rgba(139, 92, 246, 0.1), rgba(196, 181, 253, 0.1));
border-right: 3px solid var(--quaternary);
}

/* تحديث تصميم الأزرار الرئيسية */
.btn-primary {
background: var(--accent-gradient);
color: white;
box-shadow: var(--glow-accent), 0 8px 25px rgba(99, 102, 241, 0.4);
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
box-shadow: var(--glow-accent), 0 15px 40px rgba(99, 102, 241, 0.6);
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
box-shadow: var(--glow-primary), 0 8px 25px rgba(59, 130, 246, 0.4);
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
box-shadow: var(--glow-primary), 0 15px 40px rgba(59, 130, 246, 0.6);
border-color: rgba(255, 255, 255, 0.5);
}

.btn-secondary:hover::before {
left: 100%;
}

/* أزرار خاصة إضافية */
.btn-neon {
background: var(--neon-gradient);
color: white;
box-shadow: var(--glow-neon), 0 8px 25px rgba(0, 212, 255, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
animation: neon-pulse 2s infinite alternate;
}

@keyframes neon-pulse {
0% {
box-shadow: var(--glow-neon), 0 8px 25px rgba(0, 212, 255, 0.4);
}
100% {
box-shadow: 0 0 25px rgba(0, 212, 255, 0.8),
0 0 50px rgba(168, 85, 247, 0.6),
0 0 75px rgba(255, 0, 128, 0.4),
0 15px 40px rgba(0, 212, 255, 0.6);
}
}

.btn-success {
background: var(--secondary-gradient);
color: white;
box-shadow: var(--glow-secondary), 0 8px 25px rgba(16, 185, 129, 0.4);
border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-warning {
background: var(--tertiary-gradient);
color: white;
box-shadow: var(--glow-tertiary), 0 8px 25px rgba(245, 158, 11, 0.4);
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
background: var(--neon-gradient);
box-shadow: 0 0 15px rgba(0, 212, 255, 0.5);
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
#result-box, #current-score {
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
background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(99, 102, 241, 0.1));
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
background: rgba(0, 212, 255, 0.2);
backdrop-filter: blur(20px);
padding: 10px 20px;
border-radius: 25px;
border: 2px solid rgba(0, 212, 255, 0.3);
box-shadow: 0 0 15px rgba(0, 212, 255, 0.2);
}

.timer-warning {
background: rgba(255, 0, 128, 0.2) !important;
border-color: rgba(255, 0, 128, 0.3) !important;
box-shadow: 0 0 20px rgba(255, 0, 128, 0.3) !important;
animation: warning-pulse 0.8s infinite alternate;
}

@keyframes warning-pulse {
from {
box-shadow: 0 0 15px rgba(255, 0, 128, 0.3);
}
to {
box-shadow: 0 0 25px rgba(255, 0, 128, 0.5), 0 0 40px rgba(255, 0, 128, 0.3);
}
}

@keyframes pulse {
0% { transform: scale(1); }
50% { transform: scale(1.05); }
100% { transform: scale(1); }
}

/* Questions List */
#questions-list {
margin-top: 25px;
background: var(--card-bg);
backdrop-filter: blur(20px);
padding: 30px;
border-radius: 20px;
box-shadow: var(--shadow);
border: 1px solid var(--border);
display: none;
}

#questions-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
gap: 12px;
margin: 20px 0;
}

.question-status-grid {
width: 60px;
height: 60px;
border: 2px solid rgba(59, 130, 246, 0.3);
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

.question-status-grid::before {
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

.question-status-grid:hover:not(.locked) {
transform: translateY(-3px) scale(1.1);
box-shadow: var(--shadow);
}

.question-status-grid.current {
background: var(--accent-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-accent), 0 5px 15px rgba(99, 102, 241, 0.3);
animation: pulse 2s infinite;
}

.question-status-grid.answered {
background: var(--secondary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-secondary), 0 5px 15px rgba(16, 185, 129, 0.3);
}

.question-status-grid.flagged {
background: var(--tertiary-gradient);
border-color: rgba(255, 255, 255, 0.5);
box-shadow: var(--glow-tertiary), 0 5px 15px rgba(245, 158, 11, 0.3);
}

.question-status-grid.locked {
cursor: not-allowed;
opacity: 0.7;
}

.question-status-grid span {
position: relative;
z-index: 1;
}

.legend {
display: flex;
flex-wrap: wrap;
gap: 20px;
margin-top: 20px;
font-size: 0.9rem;
}

.legend-item {
display: flex;
align-items: center;
gap: 10px;
}

/* تحسينات للوضع الداكن */
.dark-theme {
--bg: linear-gradient(135deg, #1E3A8A 0%, #1E40AF 100%);
--card-bg: rgba(30, 41, 59, 0.95);
--text: #F1F5F9;
--light-text: #CBD5E1;
--border: rgba(59, 130, 246, 0.1);
--shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
--shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.4);
}

.dark-theme .btn-primary,
.dark-theme .btn-secondary {
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .theme-btn,
.dark-theme .back-btn {
background: rgba(59, 130, 246, 0.15);
border-color: rgba(255, 255, 255, 0.2);
}

.dark-theme .card {
background: rgba(30, 41, 59, 0.7);
border-color: rgba(255, 255, 255, 0.05);
}

.dark-theme .hero-section {
background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(99, 102, 241, 0.1));
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

#questions-grid {
grid-template-columns: repeat(auto-fill, minmax(50px, 1fr));
}

.question-status-grid {
width: 50px;
height: 50px;
font-size: 1rem;
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
background: var(--neon-gradient);
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

/* تصميم الشهادة */
.certificate {
display: none;
text-align: center;
border: 20px solid var(--primary);
border-image: var(--primary-gradient) 30;
padding: 50px 30px;
background: white;
color: #1a1a1a;
position: relative;
max-width: 800px;
margin: 0 auto;
box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
}

.certificate-content {
position: relative;
z-index: 1;
}

.certificate-title {
font-size: 2.5rem;
color: var(--primary);
margin-bottom: 20px;
font-weight: 800;
}

.certificate-subtitle {
font-size: 1.3rem;
color: var(--accent);
margin-bottom: 30px;
}

.certificate-name {
font-size: 2.2rem;
color: var(--secondary);
margin: 25px 0;
padding: 15px;
border-bottom: 3px solid var(--secondary);
display: inline-block;
}

.certificate-details {
font-size: 1.1rem;
line-height: 1.8;
margin: 25px 0;
}

.certificate-stamp {
position: absolute;
bottom: 30px;
left: 30px;
width: 150px;
height: 150px;
background: var(--accent-gradient);
border-radius: 50%;
display: flex;
align-items: center;
justify-content: center;
color: white;
font-weight: bold;
transform: rotate(-15deg);
opacity: 0.9;
}

.certificate-date {
position: absolute;
bottom: 30px;
right: 30px;
font-size: 1.1rem;
font-weight: bold;
color: var(--primary);
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

/* قسم مشاركة النتائج */
.share-results {
text-align: center;
padding: 30px;
background: var(--card-bg);
border-radius: 20px;
margin: 30px 0;
}

.qr-code-container {
display: flex;
justify-content: center;
margin: 20px 0;
}

#qrcode {
padding: 20px;
background: white;
border-radius: 10px;
box-shadow: var(--shadow);
}

.share-buttons {
display: flex;
gap: 15px;
justify-content: center;
margin-top: 20px;
flex-wrap: wrap;
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

/* أزرار التحكم في الشهادة */
.certificate-buttons {
margin-top: 30px;
display: flex;
gap: 15px;
justify-content: center;
flex-wrap: wrap;
}

/* تخصيص الشهادة للطباعة */
@media print {
.certificate {
border: none !important;
box-shadow: none !important;
margin: 0 !important;
padding: 0 !important;
width: 100% !important;
}

.certificate-buttons {
display: none !important;
}
}

/* تحسينات PDF */
.pdf-container {
position: fixed;
top: -9999px;
left: -9999px;
width: 794px; /* A4 width in pixels at 96 DPI */
height: 1123px; /* A4 height in pixels at 96 DPI */
background: white;
padding: 40px;
color: #1a1a1a;
font-family: 'Tajawal', sans-serif;
direction: rtl;
text-align: right;
z-index: 9999;
}

.pdf-header {
border-bottom: 3px solid #3B82F6;
padding-bottom: 20px;
margin-bottom: 30px;
text-align: center;
}

.pdf-title {
color: #3B82F6;
font-size: 28px;
margin-bottom: 10px;
}

.pdf-subtitle {
color: #6366F1;
font-size: 18px;
}

.pdf-section {
margin-bottom: 30px;
}

.pdf-section-title {
color: #3B82F6;
font-size: 20px;
border-bottom: 2px solid #10B981;
padding-bottom: 10px;
margin-bottom: 15px;
}

.pdf-table {
width: 100%;
border-collapse: collapse;
margin: 20px 0;
}

.pdf-table th, .pdf-table td {
border: 1px solid #ddd;
padding: 12px;
text-align: center;
}

.pdf-table th {
background: #f8f9fa;
color: #3B82F6;
font-weight: bold;
}

.pdf-table tr:nth-child(even) {
background: #f9f9f9;
}

.pdf-footer {
margin-top: 50px;
padding-top: 20px;
border-top: 2px solid #3B82F6;
text-align: center;
color: #6B7280;
font-size: 14px;
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
<h1>اختبار الرخصة المهنية التفاعلي</h1>
</div>
<div class="header-actions">
<button class="theme-btn" id="themeBtn">
<i class="fas fa-moon"></i>
</button>
<a href="#" class="back-btn">
<i class="fas fa-arrow-right"></i>
العودة للرئيسية
</a>
</div>
</div>
</header>

<!-- Main Content -->
<main>
<!-- Hero Section -->
<section class="hero-section glass-effect">
<div class="hero-content">
<h1 class="hero-title">اختبار الرخصة المهنية للمعلمين</h1>
<p class="hero-subtitle">تم إعداد هذا الاختبار التفاعلي لمحاكاة الاختبار الرسمي للرخصة المهنية، ويقدم تغذية راجعة فورية لجميع الإجابات</p>
<div class="quiz-info">إعداد: المعلم فهد الخالدي</div>
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
<div id="timer">⏱️ <span id="time-display">15:00</span></div>
<div style="display: flex; gap: 15px; flex-wrap: wrap;">
<button class="btn btn-primary" onclick="showQuestionsList()">
<i class="fas fa-list"></i>
قائمة الأسئلة
</button>
<button class="btn btn-warning" onclick="toggleMarkForReview()" id="mark-review-btn">
<i class="fas fa-flag"></i>
وضع علامة للمراجعة
</button>
<button class="btn btn-neon" onclick="finishQuiz()">
<i class="fas fa-flag-checkered"></i>
إنهاء الاختبار
</button>
<button class="btn btn-secondary" onclick="showCurrentScore()">
<i class="fas fa-chart-bar"></i>
عرض الدرجات الحالية
</button>
</div>
</div>

<!-- Questions List -->
<div id="questions-list" class="card">
<h3 style="color: var(--text); margin-bottom: 20px; display: flex; align-items: center; gap: 12px;">
<i class="fas fa-th-list"></i>
قائمة الأسئلة
</h3>
<div id="questions-grid"></div>
<div class="legend">
<div class="legend-item">
<div class="question-status-grid" style="background: var(--accent-gradient); color: white;"></div>
<span>السؤال الحالي</span>
</div>
<div class="legend-item">
<div class="question-status-grid" style="background: var(--secondary-gradient); color: white;"></div>
<span>تمت الإجابة</span>
</div>
<div class="legend-item">
<div class="question-status-grid" style="background: var(--tertiary-gradient); color: var(--text);"></div>
<span>معلم للمراجعة</span>
</div>
<div class="legend-item">
<div class="question-status-grid" style="background: var(--card-bg); border-color: var(--border);"></div>
<span>لم يتم الإجابة</span>
</div>
</div>
<button class="btn btn-primary" onclick="hideQuestionsList()" style="margin-top:20px; width: 100%;">
<i class="fas fa-times"></i>
إغلاق القائمة
</button>
</div>

<!-- Current Score -->
<div id="current-score" class="card">
<h3 style="color: var(--text); margin-bottom: 20px; display: flex; align-items: center; gap: 12px;">
<i class="fas fa-chart-bar"></i>
الدرجات الحالية
</h3>
<p id="current-correct" style="margin-bottom: 15px; font-size: 1.1rem;"></p>
<p id="current-percentage" style="font-weight: bold; font-size: 1.3rem; color: var(--primary);"></p>
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

<!-- قسم مشاركة النتائج -->
<div class="share-results">
<h4 style="color: var(--text); margin-bottom: 20px;">
<i class="fas fa-share-alt"></i> مشاركة النتائج
</h4>
<div class="qr-code-container">
<div id="qrcode"></div>
</div>
<div class="share-buttons">
<button class="btn btn-primary" onclick="generateCertificate()">
<i class="fas fa-certificate"></i> عرض الشهادة
</button>
<button class="btn btn-success" onclick="generatePDF()">
<i class="fas fa-file-pdf"></i> تحميل تقرير PDF
</button>
<button class="btn btn-warning" onclick="shareResults()">
<i class="fas fa-share"></i> مشاركة النتائج
</button>
<button class="btn btn-secondary" onclick="restartQuiz()">
<i class="fas fa-redo"></i> إعادة الاختبار
</button>
</div>
</div>
</div>
</div>

<!-- الشهادة -->
<div id="certificate" class="certificate no-print">
<div class="certificate-content">
<h1 class="certificate-title">شهادة إتمام الاختبار</h1>
<h2 class="certificate-subtitle">اختبار الرخصة المهنية للمعلمين</h2>
<div style="border-top: 3px solid var(--primary); width: 100px; margin: 0 auto 30px;"></div>
<p class="certificate-details">تمنح هذه الشهادة إلى:</p>
<h3 class="certificate-name" id="certificate-name">المستخدم</h3>
<p class="certificate-details">لإتمامه اختبار الرخصة المهنية التفاعلي بنجاح</p>
<p class="certificate-details" id="certificate-score">الدرجة النهائية: 0/3 (0%)</p>
<p class="certificate-details" id="certificate-evaluation">التقييم: يحتاج تحسين</p>
<div style="border-top: 3px solid var(--primary); width: 100px; margin: 30px auto;"></div>
<p class="certificate-details">بتاريخ: <span id="certificate-date"></span></p>
<div class="certificate-stamp">
<span>مختوم<br>ومصدق</span>
</div>
<div class="certificate-date" id="certificate-date-right"></div>

<!-- أزرار التحكم في الشهادة -->
<div class="certificate-buttons" id="certificate-buttons">
<button class="btn btn-primary" onclick="printCertificate()">
<i class="fas fa-print"></i> طباعة الشهادة
</button>
<button class="btn btn-success" onclick="downloadCertificateAsImage()">
<i class="fas fa-download"></i> حفظ كصورة
</button>
<button class="btn btn-secondary" onclick="closeCertificate()">
<i class="fas fa-arrow-right"></i> العودة للنتائج
</button>
</div>
</div>
</div>
</main>

<!-- PDF Container (مخفي) -->
<div id="pdf-container" class="pdf-container"></div>

<script>
// مصفوفة مكونة من 3 أسئلة فقط
const questions = [
{
"id": 1,
"q": "ما يميز الفرد في مرحلة العمليات الحسية عند بياجيه:",
"options": ["النمو اللغوي", "التفكير المجرد", "النمو الحسي الحركي", "التصنيف والترتيب"],
"answer": 2,
"explanations": {
"correct": "النمو الحسي الحركي هو ما يميز مرحلة العمليات الحسية عند بياجيه، حيث يعتمد الطفل على الحواس والحركة لاكتساب المعرفة وفهم العالم من حوله.",
"wrong1": "النمو اللغوي يحدث تدريجيًا عبر مراحل الطفولة، لكنه ليس ما يميز مرحلة العمليات الحسية بشكل رئيسي.",
"wrong2": "التفكير المجرد يظهر في مرحلة العمليات العقلية الرسمية لاحقاً، وليس في مرحلة العمليات الحسية.",
"wrong3": "التصنيف والترتيب جزء من مرحلة العمليات العقلية العملية، أي تأتي بعد مرحلة العمليات الحسية."
}
},
{
"id": 2,
"q": "القاسم المشترك الأكبر للأعداد ٥٦ و٢١:",
"options": ["6", "7", "8", "9"],
"answer": 1,
"explanations": {
"correct": "القاسم المشترك الأكبر بين ٥٦ و٢١ هو 7، لأنه العدد الأكبر الذي يقسم كلا الرقمين بدون باقي.",
"wrong1": "6 لا يقسم 21 بدون باقي، لذا لا يمكن أن يكون القاسم المشترك الأكبر.",
"wrong2": "8 يقسم 56 لكنه لا يقسم 21، لذا غير صحيح.",
"wrong3": "9 لا يقسم أيًّا من الرقمين بشكل صحيح، لذا ليس القاسم المشترك الأكبر."
}
},
{
"id": 3,
"q": "يستخدم معلم اللغة العربية طريقة المناظرة في إحدى القضايا المجتمعية؛ حيث يقسم الطلاب إلى مؤيدين ومعارضين ويستعين بمحكمين مستقلين، يهدف إلى تنمية:",
"options": ["اتخاذ القرار", "التفكير الناقد", "التفكير الإبداعي", "حل المشكلات"],
"answer": 1,
"explanations": {
"correct": "المناظرة تهدف لتنمية التفكير الناقد، حيث يقوم الطلاب بتحليل الأدلة، تقييم الحجج، وتحديد موقفهم بناءً على تحليل منطقي.",
"wrong1": "اتخاذ القرار قد يكون نتيجة للمناظرة، لكنه ليس الهدف الرئيسي.",
"wrong2": "التفكير الإبداعي مرتبط بالابتكار وحل المشكلات بطرق جديدة.",
"wrong3": "حل المشكلات قد يكون نتيجة جانبية، لكنه ليس جوهر النشاط التربوي في المناظرة."
}
}
];

let currentQuestionIndex = 0;
let userAnswers = Array(questions.length).fill(null);
let timeLeft = 15 * 60; // 15 دقيقة للاختبار القصير
let timerInterval;
let markedQuestions = [];
let answerLocked = Array(questions.length).fill(false);
let performanceHistory = [];

// تحميل سجل الأداء السابق من localStorage
function loadPerformanceHistory() {
const savedHistory = localStorage.getItem('teacherLicensePerformanceHistory');
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
localStorage.setItem('teacherLicensePerformanceHistory', JSON.stringify(performanceHistory));
}

// تبديل الوضع الليلي
document.getElementById('themeBtn').addEventListener('click', function() {
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

// المؤقت
function startTimer() {
timerInterval = setInterval(() => {
timeLeft--;
updateTimerDisplay();

if (timeLeft <= 0) {
clearInterval(timerInterval);
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

// عرض قائمة الأسئلة
function showQuestionsList() {
const grid = document.getElementById('questions-grid');
grid.innerHTML = '';

questions.forEach((_, index) => {
const btn = document.createElement('div');
btn.className = `question-status-grid ${index === currentQuestionIndex ? 'current' : ''} ${userAnswers[index] !== null ? 'answered' : ''} ${markedQuestions.includes(index) ? 'flagged' : ''}`;
btn.innerHTML = `<span>${index + 1}</span>`;
btn.onclick = () => {
currentQuestionIndex = index;
loadQuiz();
hideQuestionsList();
};
grid.appendChild(btn);
});

document.getElementById('questions-list').style.display = 'block';
}

function hideQuestionsList() {
document.getElementById('questions-list').style.display = 'none';
}

// وضع علامة للمراجعة
function toggleMarkForReview() {
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

if (document.getElementById('questions-list').style.display === 'block') {
showQuestionsList();
}
}

// تحميل الاختبار
function loadQuiz() {
const quizDiv = document.getElementById("quiz");

const question = questions[currentQuestionIndex];
const isLocked = answerLocked[currentQuestionIndex];

let html = `
<div class="question-box fade-in">
<div class="question-number">
<i class="fas fa-question-circle"></i>
السؤال ${currentQuestionIndex + 1} من ${questions.length}
${isLocked ? '<span style="color: var(--accent); margin-right: 10px;"><i class="fas fa-lock"></i> مقفل</span>' : ''}
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
document.getElementById('progress').style.width = questions.length > 0 ? `${((currentQuestionIndex + 1) / questions.length) * 100}%` : '0%';

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

userAnswers[currentQuestionIndex] = answerIndex;
answerLocked[currentQuestionIndex] = true;

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

// تحديث قائمة الأسئلة إذا كانت ظاهرة
if (document.getElementById('questions-list').style.display === 'block') {
showQuestionsList();
}
}

// عرض الشرح
function showExplanation() {
const question = questions[currentQuestionIndex];
const explanationDiv = document.getElementById("explanation");
const userAnswer = userAnswers[currentQuestionIndex];

if (userAnswer !== null) {
explanationDiv.style.display = "block";

let resultHTML = "";

if (userAnswer === question.answer) {
resultHTML = `<p class="correct"><i class="fas fa-check-circle"></i> إجابة صحيحة</p>`;
} else {
resultHTML = `
<p class="wrong"><i class="fas fa-times-circle"></i> إجابة خاطئة — الإجابة الصحيحة: <span class="correct">${question.options[question.answer]}</span></p>
`;
}

// إضافة الشروح الملونة
resultHTML += `
<div class="explanation-line explanation-correct"><strong>التفسير الصحيح:</strong> ${question.explanations.correct}</div>
`;

// إضافة التفسيرات للخيارات الخاطئة
const wrongKeys = ['wrong1', 'wrong2', 'wrong3'];
const colors = ['explanation-wrong-1', 'explanation-wrong-2', 'explanation-wrong-3'];

wrongKeys.forEach((key, index) => {
if (question.explanations[key]) {
resultHTML += `<div class="explanation-line ${colors[index]}">${question.explanations[key]}</div>`;
}
});

explanationDiv.innerHTML = resultHTML;
}
}

// الانتقال إلى السؤال التالي
function nextQuestion() {
if (currentQuestionIndex < questions.length - 1) {
currentQuestionIndex++;
loadQuiz();
}
}

// الانتقال إلى السؤال السابق
function previousQuestion() {
if (currentQuestionIndex > 0) {
currentQuestionIndex--;
loadQuiz();
}
}

// عرض الدرجات الحالية دون إنهاء الاختبار
function showCurrentScore() {
let totalCorrect = 0;
userAnswers.forEach((answer, index) => {
if (answer === questions[index]?.answer) {
totalCorrect++;
}
});

const total = questions.length;
const percentage = total > 0 ? ((totalCorrect / total) * 100).toFixed(2) : 0;

document.getElementById("current-score").style.display = "block";
document.getElementById("current-correct").innerHTML = `الإجابات الصحيحة: ${totalCorrect} من ${total}`;
document.getElementById("current-percentage").innerHTML = `النسبة المئوية الحالية: ${percentage}%`;
}

// إعادة تشغيل الاختبار
function restartQuiz() {
// إعادة تعيين جميع المتغيرات
currentQuestionIndex = 0;
userAnswers = Array(questions.length).fill(null);
timeLeft = 15 * 60;
markedQuestions = [];
answerLocked = Array(questions.length).fill(false);

// إعادة تعيين العرض
document.getElementById("quiz").style.display = "block";
document.querySelector(".controls").style.display = "flex";
document.getElementById("result-box").style.display = "none";
document.getElementById('questions-list').style.display = 'none';
document.getElementById('certificate').style.display = 'none';

// إعادة تحميل المؤقت
clearInterval(timerInterval);
startTimer();

// إعادة تحميل الاختبار
loadQuiz();

// تحديث المؤقت
updateTimerDisplay();
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
borderColor: 'rgba(59, 130, 246, 1)',
backgroundColor: 'rgba(59, 130, 246, 0.1)',
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
<h4><i class="fas fa-star"></i> أداء ممتاز</h4>
<p>أداؤك رائع! يمكنك التركيز على المراجعة الدورية للحفاظ على هذا المستوى المتميز.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-book"></i> تطوير متقدم</h4>
<p>يمكنك الآن دراسة حالات متقدمة وتطبيقات عملية أكثر تعقيداً في التربية.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-chalkboard-teacher"></i> قيادة تربوية</h4>
<p>بمستواك الحالي، يمكنك المساهمة في تدريب زملائك وتقديم ورش عمل تربوية.</p>
</div>
`;
} else if (score.percentage >= 70) {
tipsHTML = `
<div class="tip-card">
<h4><i class="fas fa-check-circle"></i> أداء جيد</h4>
<p>أداؤك جيد، ركز على الأسئلة التي واجهت صعوبة فيها وحاول فهمها جيداً.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-book-open"></i> مراجعة مركزة</h4>
<p>راجع المفاهيم التي أخطأت فيها، وحاول حل تمارين إضافية مشابهة.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-clock"></i> تحسين الوقت</h4>
<p>تدرب على حل الأسئلة بسرعة أكبر مع الحفاظ على الدقة في الإجابات.</p>
</div>
`;
} else {
tipsHTML = `
<div class="tip-card">
<h4><i class="fas fa-exclamation-triangle"></i> يحتاج تحسين</h4>
<p>أنت بحاجة إلى مراجعة شاملة للمفاهيم الأساسية في التربية وعلم النفس التربوي.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-graduation-cap"></i> دراسة أساسيات</h4>
<p>ركز على فهم النظريات التربوية الأساسية وأساسيات علم النفس التربوي.</p>
</div>
<div class="tip-card">
<h4><i class="fas fa-redo"></i> تكرار الاختبار</h4>
<p>كرر الاختبار بعد دراسة المواد الأساسية لمتابعة تطور مستواك.</p>
</div>
`;
}

tipsContainer.innerHTML = tipsHTML;
}

// إنشاء رمز QR للنتائج
function generateQRCode() {
const score = calculateScore();
const resultText = `نتيجة اختبار الرخصة المهنية: ${score.correct}/${questions.length} (${score.percentage}%) - ${score.evaluation}`;
const qrElement = document.getElementById('qrcode');
qrElement.innerHTML = '';
new QRCode(qrElement, {
text: resultText,
width: 150,
height: 150,
colorDark: "#000000",
colorLight: "#ffffff",
correctLevel: QRCode.CorrectLevel.H
});
}

// حساب الدرجات
function calculateScore() {
let totalCorrect = 0;
userAnswers.forEach((answer, index) => {
if (answer === questions[index]?.answer) {
totalCorrect++;
}
});

const total = questions.length;
const percentage = total > 0 ? ((totalCorrect / total) * 100).toFixed(2) : 0;

let evaluation = "";
let evaluationIcon = "";
if (percentage >= 90) {
evaluation = "ممتاز";
evaluationIcon = "🌟";
} else if (percentage >= 80) {
evaluation = "جيد جداً";
evaluationIcon = "🔵";
} else if (percentage >= 70) {
evaluation = "جيد";
evaluationIcon = "🟢";
} else if (percentage >= 60) {
evaluation = "مقبول";
evaluationIcon = "🟡";
} else {
evaluation = "يحتاج تحسين";
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

// إنشاء شهادة الإتمام
function generateCertificate() {
const score = calculateScore();
const now = new Date();
const dateString = now.toLocaleDateString('ar-SA');
const name = prompt("أدخل اسمك للحصول على الشهادة:", "المستخدم");
if (!name) return;

// تحديث محتوى الشهادة
document.getElementById('certificate-name').textContent = name;
document.getElementById('certificate-score').textContent = `الدرجة النهائية: ${score.correct}/${score.total} (${score.percentage}%)`;
document.getElementById('certificate-evaluation').textContent = `التقييم: ${score.evaluation}`;
document.getElementById('certificate-date').textContent = dateString;
document.getElementById('certificate-date-right').textContent = dateString;

// عرض الشهادة وإخفاء النتائج
document.getElementById('certificate').style.display = 'block';
document.getElementById('result-box').style.display = 'none';
}

// طباعة الشهادة
function printCertificate() {
// حفظ المحتوى الأصلي
const originalContents = document.body.innerHTML;
const certificateContent = document.getElementById('certificate').innerHTML;

// إنشاء نافذة طباعة
const printWindow = window.open('', '_blank');
printWindow.document.write(`
<!DOCTYPE html>
<html dir="rtl" lang="ar">
<head>
<meta charset="UTF-8">
<title>شهادة اختبار الرخصة المهنية</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap');
body {
font-family: 'Tajawal', sans-serif;
margin: 0;
padding: 20px;
background: white;
color: #1F2937;
text-align: center;
}
.certificate {
border: 20px solid #3B82F6;
padding: 50px 30px;
max-width: 800px;
margin: 0 auto;
}
.certificate-title {
font-size: 2.5rem;
color: #3B82F6;
margin-bottom: 20px;
}
.certificate-name {
font-size: 2.2rem;
color: #10B981;
margin: 25px 0;
padding: 15px;
border-bottom: 3px solid #10B981;
display: inline-block;
}
button { display: none; }
@media print {
body { padding: 0; }
}
</style>
</head>
<body>
${certificateContent}
<script>
window.onload = function() {
window.print();
setTimeout(() => {
window.close();
}, 1000);
};
<\/script>
</body>
</html>
`);
}

// تحميل الشهادة كصورة
function downloadCertificateAsImage() {
const certificate = document.getElementById('certificate');
if (typeof html2canvas !== 'undefined') {
html2canvas(certificate, {
scale: 2,
backgroundColor: '#ffffff',
useCORS: true,
allowTaint: true
}).then(canvas => {
const link = document.createElement('a');
const date = new Date().toLocaleDateString('ar-SA').replace(/\//g, '-');
link.download = `شهادة_اختبار_الرخصة_المهنية_${date}.png`;
link.href = canvas.toDataURL('image/png');
link.click();
}).catch(error => {
console.error('خطأ في تحويل الشهادة إلى صورة:', error);
alert('حدث خطأ في تحويل الشهادة إلى صورة. حاول استخدام زر الطباعة بدلاً من ذلك.');
});
} else {
alert('ميزة تحويل الشهادة إلى صورة غير متوفرة حالياً. الرجاء استخدام زر الطباعة.');
}
}

// إغلاق الشهادة
function closeCertificate() {
document.getElementById('certificate').style.display = 'none';
document.getElementById('result-box').style.display = 'block';
}

// إنشاء تقرير PDF - الطريقة المحسنة
function generatePDF() {
const score = calculateScore();
const now = new Date();
const dateString = now.toLocaleDateString('ar-SA');
const name = prompt("أدخل اسمك لتضمينه في التقرير:", "المستخدم");
if (!name) name = "المستخدم";

// إنشاء محتوى PDF
const pdfContent = `
<div class="pdf-container">
    <div class="pdf-header">
        <h1 class="pdf-title">تقرير نتائج اختبار الرخصة المهنية</h1>
        <p class="pdf-subtitle">إعداد: المعلم فهد الخالدي</p>
    </div>
    
    <div class="pdf-section">
        <h2 class="pdf-section-title">معلومات الاختبار</h2>
        <p><strong>اسم المستخدم:</strong> ${name}</p>
        <p><strong>تاريخ الاختبار:</strong> ${dateString}</p>
        <p><strong>عدد الأسئلة:</strong> ${score.total}</p>
        <p><strong>مدة الاختبار:</strong> 15 دقيقة</p>
    </div>
    
    <div class="pdf-section">
        <h2 class="pdf-section-title">النتائج</h2>
        <table class="pdf-table">
            <tr>
                <th>المؤشر</th>
                <th>القيمة</th>
                <th>النسبة</th>
            </tr>
            <tr>
                <td>الإجابات الصحيحة</td>
                <td>${score.correct}</td>
                <td>${score.percentage}%</td>
            </tr>
            <tr>
                <td>الإجابات الخاطئة</td>
                <td>${score.total - score.correct}</td>
                <td>${(100 - score.percentage).toFixed(2)}%</td>
            </tr>
            <tr>
                <td>إجمالي الأسئلة</td>
                <td>${score.total}</td>
                <td>100%</td>
            </tr>
        </table>
        <p style="margin-top: 20px; font-size: 18px; color: ${score.percentage >= 70 ? '#10B981' : '#F59E0B'}">
            <strong>التقييم:</strong> ${score.evaluation}
        </p>
    </div>
    
    <div class="pdf-section">
        <h2 class="pdf-section-title">تفاصيل الإجابات</h2>
        <table class="pdf-table">
            <tr>
                <th>رقم السؤال</th>
                <th>الحالة</th>
                <th>الإجابة الصحيحة</th>
            </tr>
            ${questions.map((q, index) => {
                const userAnswer = userAnswers[index];
                const isCorrect = userAnswer === q.answer;
                return `
                <tr>
                    <td>${index + 1}</td>
                    <td style="color: ${isCorrect ? '#10B981' : '#EF4444'}">
                        ${isCorrect ? '✓ صحيح' : '✗ خطأ'}
                    </td>
                    <td>${q.options[q.answer]}</td>
                </tr>
                `;
            }).join('')}
        </table>
    </div>
    
    <div class="pdf-section">
        <h2 class="pdf-section-title">نصائح للتحسين</h2>
        ${score.percentage >= 90 ? 
            '<p>أداؤك ممتاز! استمر في المراجعة الدورية للمحافظة على هذا المستوى.</p>' : 
        score.percentage >= 70 ?
            '<p>أداؤك جيد. ركز على الأسئلة التي أخطأت فيها وحاول فهمها جيداً.</p>' :
            '<p>أنت بحاجة إلى مراجعة شاملة للمفاهيم الأساسية. ننصحك بمراجعة المواد التعليمية وحل المزيد من التمارين.</p>'
        }
        <ul style="margin-right: 20px; margin-top: 15px;">
            <li>مراجعة النظريات التربوية الأساسية</li>
            <li>حل تمارين إضافية متنوعة</li>
            <li>التركيز على فهم التفسيرات بدلاً من حفظ الإجابات</li>
            <li>التدرب على إدارة وقت الاختبار</li>
        </ul>
    </div>
    
    <div class="pdf-section">
        <h2 class="pdf-section-title">معلومات إضافية</h2>
        <p><strong>وقت الإكمال:</strong> ${(15 - timeLeft/60).toFixed(0)} دقيقة من أصل 15 دقيقة</p>
        <p><strong>عدد الأسئلة المعلمة:</strong> ${markedQuestions.length}</p>
        <p><strong>سجل الأداء:</strong> ${performanceHistory.length} محاولة سابقة</p>
    </div>
    
    <div class="pdf-footer">
        <p>تم إنشاء هذا التقرير تلقائياً بواسطة نظام اختبار الرخصة المهنية التفاعلي</p>
        <p>© ${new Date().getFullYear()} - إعداد المعلم فهد الخالدي</p>
    </div>
</div>
`;

// إضافة المحتوى إلى الصفحة
const pdfContainer = document.getElementById('pdf-container');
pdfContainer.innerHTML = pdfContent;

// استخدام html2canvas لتحويل المحتوى إلى صورة
html2canvas(pdfContainer, {
    scale: 2,
    backgroundColor: '#ffffff',
    useCORS: true,
    logging: false
}).then(canvas => {
    // تحويل Canvas إلى صورة
    const imgData = canvas.toDataURL('image/png');
    
    // استخدام jsPDF مع الصورة
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF('p', 'mm', 'a4');
    
    // حساب أبعاد الصورة
    const imgWidth = 210; // A4 width in mm
    const pageHeight = 297; // A4 height in mm
    const imgHeight = (canvas.height * imgWidth) / canvas.width;
    
    // إضافة الصورة إلى PDF
    doc.addImage(imgData, 'PNG', 0, 0, imgWidth, imgHeight);
    
    // إذا كانت الصورة أطول من صفحة واحدة، إضافة صفحات إضافية
    let heightLeft = imgHeight;
    let position = 0;
    
    // إضافة صفحات إضافية إذا لزم الأمر
    while (heightLeft >= pageHeight) {
        position = heightLeft - pageHeight;
        doc.addPage();
        doc.addImage(imgData, 'PNG', 0, -position, imgWidth, imgHeight);
        heightLeft -= pageHeight;
    }
    
    // حفظ الملف
    const date = new Date().toLocaleDateString('ar-SA').replace(/\//g, '-');
    doc.save(`تقرير_نتائج_اختبار_الرخصة_المهنية_${date}.pdf`);
    
    // إظهار رسالة نجاح
    alert('تم إنشاء وتحميل التقرير بنجاح!');
    
}).catch(error => {
    console.error('خطأ في إنشاء PDF:', error);
    
    // طريقة بديلة إذا فشلت الطريقة الأولى
    try {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF('p', 'mm', 'a4');
        
        // إضافة نص بسيط إذا فشلت الطريقة الأولى
        doc.setFontSize(16);
        doc.text('تقرير نتائج اختبار الرخصة المهنية', 105, 20, null, null, 'center');
        doc.setFontSize(12);
        doc.text(`اسم المستخدم: ${name}`, 20, 40);
        doc.text(`التاريخ: ${dateString}`, 20, 50);
        doc.text(`النتيجة: ${score.correct}/${score.total} (${score.percentage}%)`, 20, 60);
        doc.text(`التقييم: ${score.evaluation}`, 20, 70);
        doc.text('إعداد: المعلم فهد الخالدي', 105, 280, null, null, 'center');
        
        const date = new Date().toLocaleDateString('ar-SA').replace(/\//g, '-');
        doc.save(`تقرير_نتائج_${date}.pdf`);
        
        alert('تم تحميل التقرير بنسخة مبسطة (بدون رسوم بيانية).');
    } catch (e) {
        alert('حدث خطأ في إنشاء PDF. الرجاء المحاولة مرة أخرى أو استخدام زر طباعة الشهادة بدلاً من ذلك.');
    }
});
}

// مشاركة النتائج
function shareResults() {
const score = calculateScore();
const text = `🎯 حصلت على ${score.correct}/${score.total} (${score.percentage}%) في اختبار الرخصة المهنية! \nجرب الاختبار: ${window.location.href}`;

if (navigator.share) {
navigator.share({
title: 'نتيجة اختبار الرخصة المهنية',
text: text,
url: window.location.href
}).catch(error => {
console.log('Error sharing:', error);
});
} else {
// نسخ إلى الحافظة
navigator.clipboard.writeText(text)
.then(() => alert('تم نسخ النتيجة إلى الحافظة! يمكنك مشاركتها الآن.'))
.catch(err => {
console.error('Error copying text: ', err);
// طريقة بديلة للمتصفحات القديمة
const textArea = document.createElement('textarea');
textArea.value = text;
document.body.appendChild(textArea);
textArea.select();
document.execCommand('copy');
document.body.removeChild(textArea);
alert('تم نسخ النتيجة إلى الحافظة!');
});
}
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

// إنهاء الاختبار
function finishQuiz() {
clearInterval(timerInterval);

const score = calculateScore();

// حفظ سجل الأداء
savePerformanceRecord();

// عرض النتائج
document.getElementById("result-box").style.display = "block";
document.getElementById("result").innerHTML = `${score.evaluationIcon} النتيجة: ${score.correct} من ${score.total}`;
document.getElementById("percentage").innerHTML = `النسبة المئوية: ${score.percentage}%`;
document.getElementById("evaluation").innerHTML = `التقييم: ${score.evaluation}`;

// إخفاء الاختبار
document.getElementById("quiz").style.display = "none";
document.querySelector(".controls").style.display = "none";
document.getElementById('questions-list').style.display = 'none';

// عرض النتائج المتقدمة
document.getElementById('advanced-results').style.display = 'block';

// إنشاء الرسوم البيانية والنصائح
setTimeout(() => {
createPerformanceChart();
createCustomTips();
generateQRCode();
}, 100);
}

// بدء التحميل الأولي
window.onload = function() {
checkDarkModePreference();
loadPerformanceHistory();
loadQuiz();
startTimer();

// إضافة تأثيرات عند التحميل
document.querySelector('.hero-section').classList.add('bounce-in');
setTimeout(() => {
if (document.querySelector('.card')) {
document.querySelector('.card').classList.add('fade-in');
}
}, 300);
}
</script>
</body>
</html>

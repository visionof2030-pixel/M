<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="اختبار دورة الاتصالات التفاعلي">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            /* ألوان متطورة وجذابة */
            --primary: #6366F1;
            --primary-dark: #4F46E5;
            --primary-light: #8B5CF6;
            --accent: #EC4899;
            --accent-dark: #DB2777;
            --accent-light: #F472B6;
            --secondary: #10B981;
            --secondary-dark: #059669;
            --tertiary: #F59E0B;
            --quaternary: #8B5CF6;
            --bg: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --card-bg: rgba(255, 255, 255, 0.95);
            --text: #1F2937;
            --light-text: #6B7280;
            --border: rgba(255, 255, 255, 0.2);
            --shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            --shadow-hover: 0 20px 40px rgba(0, 0, 0, 0.2);
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-dark: linear-gradient(135deg, #5a67d8 0%, #6b46c1 100%);
            --gradient-light: linear-gradient(135deg, #a78bfa 0%, #c4b5fd 100%);
            --accent-gradient: linear-gradient(135deg, #EC4899, #8B5CF6);
            --success-gradient: linear-gradient(135deg, #10B981, #34D399);
            --warning-gradient: linear-gradient(135deg, #F59E0B, #FBBF24);
            --primary-gradient: linear-gradient(135deg, #6366F1, #8B5CF6);
        }

        .dark-theme {
            --bg: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
            --card-bg: rgba(30, 41, 59, 0.95);
            --text: #F1F5F9;
            --light-text: #CBD5E1;
            --border: rgba(255, 255, 255, 0.1);
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
            background: rgba(255, 255, 255, 0.1);
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
            text-shadow: 0 2px 10px rgba(236, 72, 153, 0.3);
        }

        .header-actions {
            display: flex;
            gap: 10px;
        }

        .theme-btn, .back-btn {
            background: rgba(255, 255, 255, 0.15);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 6px;
            backdrop-filter: blur(10px);
            text-decoration: none;
        }

        .theme-btn:hover, .back-btn:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Main Content */
        main {
            max-width: 1000px;
            margin: 30px auto;
            padding: 0 20px;
        }

        .hero-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            color: white;
            border-radius: 24px;
            padding: 40px;
            margin-bottom: 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow);
            border: 1px solid var(--border);
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
            margin-bottom: 15px;
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
            background: var(--card-bg);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 25px;
            box-shadow: var(--shadow);
            transition: all 0.4s ease;
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--accent-gradient);
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

        /* تصميم الأسئلة المتطور */
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

        .options label:hover {
            border-color: var(--primary);
            transform: translateX(-8px);
            box-shadow: 0 5px 15px rgba(99, 102, 241, 0.2);
        }

        .options label:hover::before {
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
        }

        .options label.selected {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.1));
            border-color: var(--primary);
            box-shadow: 0 5px 15px rgba(99, 102, 241, 0.2);
        }

        .options label.selected::before {
            width: 6px;
            background: var(--success-gradient);
        }

        .options label.correct-answer {
            background: linear-gradient(135deg, rgba(16, 185, 129, 0.15), rgba(52, 211, 153, 0.15));
            border-color: var(--secondary);
            box-shadow: 0 5px 15px rgba(16, 185, 129, 0.2);
        }

        .options label.correct-answer::before {
            width: 6px;
            background: var(--success-gradient);
        }

        .options label.wrong-answer {
            background: linear-gradient(135deg, rgba(236, 72, 153, 0.1), rgba(244, 114, 182, 0.1));
            border-color: var(--accent);
            box-shadow: 0 5px 15px rgba(236, 72, 153, 0.2);
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
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.05), rgba(236, 72, 153, 0.05));
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
            background: linear-gradient(135deg, rgba(236, 72, 153, 0.1), rgba(244, 114, 182, 0.1));
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

        .btn-primary {
            background: var(--accent-gradient);
            color: white;
            box-shadow: 0 8px 25px rgba(236, 72, 153, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(236, 72, 153, 0.4);
        }

        .btn-secondary {
            background: var(--primary-gradient);
            color: white;
            box-shadow: 0 8px 25px rgba(99, 102, 241, 0.3);
        }

        .btn-secondary:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(99, 102, 241, 0.4);
        }

        .btn:disabled {
            background: #9CA3AF;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .btn:disabled:hover::before {
            left: -100%;
        }

        /* Progress Bar متطور */
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
            background: var(--accent-gradient);
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
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(236, 72, 153, 0.1));
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: 600;
            backdrop-filter: blur(10px);
        }

        /* Timer متطور */
        #timer {
            font-size: 1.1rem;
            font-weight: bold;
            color: white;
            margin-left: 20px;
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.2);
            padding: 10px 20px;
            border-radius: 25px;
            backdrop-filter: blur(10px);
        }

        .timer-warning {
            color: #FECACA !important;
            animation: pulse 0.8s infinite;
            background: rgba(254, 202, 202, 0.3) !important;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Questions List متطور */
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
            border: 2px solid var(--border);
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

        .question-status-grid:hover {
            transform: translateY(-3px) scale(1.1);
            box-shadow: var(--shadow);
        }

        .question-status-grid.current {
            border-color: var(--accent);
            background: var(--accent);
            color: white;
            transform: scale(1.1);
        }

        .question-status-grid.answered {
            border-color: var(--secondary);
            background: var(--secondary);
            color: white;
        }

        .question-status-grid.flagged {
            border-color: var(--tertiary);
            background: var(--tertiary);
            color: var(--text);
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
        .dark-theme .question-status-grid {
            border-color: var(--border);
        }

        .dark-theme .options label {
            background: var(--card-bg);
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
            background: var(--accent-gradient);
            border-radius: 50%;
            opacity: 0.1;
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
                <h1>اختبار دورة الاتصالات التفاعلي</h1>
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
                <h1 class="hero-title">اختبار دورة الاتصالات</h1>
                <p class="hero-subtitle">تم إعداد هذا الاختبار التفاعلي لمحاكاة اختبار دورة الاتصالات، ويقدم تغذية راجعة فورية لجميع الإجابات</p>
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
            <div id="timer">⏱️ <span id="time-display">45:00</span></div>
            <div style="display: flex; gap: 15px; flex-wrap: wrap;">
                <button class="btn btn-primary" onclick="showQuestionsList()">
                    <i class="fas fa-list"></i>
                    قائمة الأسئلة
                </button>
                <button class="btn btn-secondary" onclick="toggleMarkForReview()" id="mark-review-btn">
                    <i class="fas fa-flag"></i>
                    وضع علامة للمراجعة
                </button>
                <button class="btn btn-primary" onclick="finishQuiz()">
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
                    <div class="question-status-grid" style="background: var(--accent); color: white;"></div>
                    <span>السؤال الحالي</span>
                </div>
                <div class="legend-item">
                    <div class="question-status-grid" style="background: var(--secondary); color: white;"></div>
                    <span>تمت الإجابة</span>
                </div>
                <div class="legend-item">
                    <div class="question-status-grid" style="background: var(--tertiary); color: var(--text);"></div>
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
        </div>
    </main>

    <script>
        // مصفوفة الأسئلة
        const questions = [
            {
                "id": 1,
                "q": "من قواعد وأصول المخابرة الأساسية:",
                "options": ["التعقيد – السرعة – الأمن – التشفير", "الدقة – السرعة – الإيجاز – الأمن", "السرية – التفصيل – البطء – التنظيم", "الأمن – الاستطلاع – الدقة – التخطيط"],
                "answer": 1,
                "explanations": {
                    "correct": "القواعد الأساسية للمخابرة هي الدقة والسرعة والإيجاز والأمن. الدقة تضمن نقل المعلومات بشكل صحيح، السرعة تضمن وصول المعلومات في الوقت المناسب، الإيجاز يمنع إضاعة الوقت، والأمن يحمي المعلومات من الوصول غير المصرح به.",
                    "wrong1": "التعقيد ليس من قواعد المخابرة الأساسية بل يجب أن تكون المخابرة بسيطة ومفهومة.",
                    "wrong2": "التفصيل المفرط قد يؤدي إلى إضاعة الوقت وعدم وضوح الرسالة.",
                    "wrong3": "الاستطلاع ليس من قواعد المخابرة الأساسية بل هو مهمة عسكرية منفصلة."
                }
            },
            {
                "id": 2,
                "q": "الغرض من قواعد المخابرة هو:",
                "options": ["زيادة عدد الرسائل المتداولة", "ضمان تمرير المعلومات بشكل ناجح ومضمون", "تمكين الضباط من استخدام الشفرات فقط", "تحسين المراسلات الورقية"],
                "answer": 1,
                "explanations": {
                    "correct": "الغرض الأساسي من قواعد المخابرة هو ضمان تمرير المعلومات بشكل ناجح ومضمون بين الأطراف المختلفة، مع الحفاظ على دقة المعلومات وسرية وسلامة الاتصال.",
                    "wrong1": "زيادة عدد الرسائل ليس هدفاً في حد ذاته، بل جودة ووضوح الرسائل هو المهم.",
                    "wrong2": "تمكين الضباط من استخدام الشفرات هو وسيلة وليس غاية في حد ذاتها.",
                    "wrong3": "تحسين المراسلات الورقية هو جزء صغير فقط من نطاق المخابرة الشامل."
                }
            },
            {
                "id": 3,
                "q": "الاتصالات التي تتم عن طريق الهاتف تعتبر:",
                "options": ["اتصالات ميدانية", "اتصالات مشفرة", "اتصالات سلكية", "اتصالات صوتية"],
                "answer": 2,
                "explanations": {
                    "correct": "الاتصالات الهاتفية تعتبر اتصالات سلكية لأنها تعتمد على الأسلاك والنقاط المادية لنقل الإشارات الصوتية بين الأطراف.",
                    "wrong1": "الاتصالات الميدانية قد تكون لاسلكية أو سلكية، لكن الهاتف التقليدي يعتمد على الأسلاك.",
                    "wrong2": "الاتصالات الهاتفية التقليدية ليست مشفرة بالضرورة.",
                    "wrong3": "الاتصالات الصوتية وصف عام قد يشمل أنواعاً أخرى غير الهاتف."
                }
            },
            {
                "id": 4,
                "q": "الاتصالات اللاسلكية لا تشمل مما يلي:",
                "options": ["الإشارات الصوتية", "المورس", "المبرقات", "الاتصالات السلكية"],
                "answer": 3,
                "explanations": {
                    "correct": "الاتصالات السلكية لا تدخل ضمن نطاق الاتصالات اللاسلكية، فهي تعتمد على وسائط مادية لنقل الإشارات.",
                    "wrong1": "الإشارات الصوتية يمكن نقلها لاسلكياً عبر موجات الراديو.",
                    "wrong2": "المورس هو نظام اتصال لاسلكي يستخدم النبضات الكهربائية.",
                    "wrong3": "المبرقات هي أجهزة اتصال لاسلكي تستخدم لنقل البرقيات."
                }
            },
            {
                "id": 5,
                "q": "المحادثة عبر اللاسلكي تتميز بأنها:",
                "options": ["بطيئة وغير فعالة", "سريعة وأفضل وسائل الاتصال", "تستخدم فقط وقت الطوارئ", "تمنع أثناء العمليات"],
                "answer": 1,
                "explanations": {
                    "correct": "المحادثة عبر اللاسلكي تتميز بسرعتها وفعاليتها في نقل المعلومات الفورية، مما يجعلها من أفضل وسائل الاتصال في الظروف المختلفة.",
                    "wrong1": "المحادثة اللاسلكية سريعة وفعالة عندما تستخدم بشكل صحيح.",
                    "wrong2": "تستخدم المحادثة اللاسلكية في جميع الأوقات وليس فقط في الطوارئ.",
                    "wrong3": "المحادثة اللاسلكية أساسية أثناء العمليات وليست ممنوعة."
                }
            },
            {
                "id": 6,
                "q": "البرقية الشفوية يتم:",
                "options": ["تسجيلها في مركز الاتصال", "إتلافها بعد الإرسال", "ترميزها دائمًا", "إرسالها عبر الفاكس"],
                "answer": 1,
                "explanations": {
                    "correct": "البرقية الشفوية يتم إتلافها بعد الإرسال لضمان السرية وعدم بقاء أي أثر للمعلومات المنقولة.",
                    "wrong1": "تسجيل البرقية الشفوية قد يخالف مبدأ السرية.",
                    "wrong2": "البرقية الشفوية قد لا تكون مشفرة دائماً.",
                    "wrong3": "الفاكس يستخدم للوثائق المكتوبة وليس للبرقيات الشفوية."
                }
            },
            {
                "id": 7,
                "q": "المورس يستخدم عادة عندما تكون:",
                "options": ["المحطات قريبة", "الأجواء جيدة", "المسافات بعيدة أو الظروف الجوية سيئة", "الحاجة للسرية قليلة"],
                "answer": 2,
                "explanations": {
                    "correct": "المورس يستخدم بشكل فعال عندما تكون المسافات بعيدة أو الظروف الجوية سيئة، لأنه نظام مقاوم للتداخل ويمكنه اختراق الظروف الصعبة.",
                    "wrong1": "للمسافات القريبة توجد وسائل اتصال أكثر كفاءة من المورس.",
                    "wrong2": "في الأجواء الجودة يمكن استخدام وسائل اتصال أكثر تطوراً.",
                    "wrong3": "المورس يوفر درجة جيدة من السرية وليس العكس."
                }
            },
            {
                "id": 8,
                "q": "من واجبات مستخدم الجهاز للحفاظ على الأمن:",
                "options": ["الإطالة في المحادثة", "استخدام الأسماء الحقيقية", "التفكير قبل الكلام على الجهاز", "عدم تغيير الترددات"],
                "answer": 2,
                "explanations": {
                    "correct": "التفكير قبل الكلام على الجهاز من أهم واجبات مستخدم الجهاز للحفاظ على الأمن، لتجنب تسرب معلومات حساسة.",
                    "wrong1": "الإطالة في المحادثة تزيد من فرص اعتراض الاتصال.",
                    "wrong2": "استخدام الأسماء الحقيقية يخالف مبدأ السرية.",
                    "wrong3": "تغيير الترددات باستمرار يساهم في تعزيز الأمن."
                }
            },
            {
                "id": 9,
                "q": "من أهم طرق المحافظة على السرية:",
                "options": ["عدم استخدام الشيفرة", "تغيير النداءات والترددات باستمرار", "إطالة البرقية", "إرسال كل شيء بالمفتوح"],
                "answer": 1,
                "explanations": {
                    "correct": "تغيير النداءات والترددات باستمرار من أهم طرق المحافظة على السرية، لأنه يجعل من الصعب على العدو تتبع الاتصالات.",
                    "wrong1": "استخدام الشيفرة أساسي للحفاظ على السرية.",
                    "wrong2": "إطالة البرقية تزيد من فرص اعتراضها.",
                    "wrong3": "إرسال المعلومات بالمفتوح يخالف مبدأ السرية تماماً."
                }
            },
            {
                "id": 10,
                "q": "يمنع استخدام:",
                "options": ["الشيفرة", "الأسماء الرمزية", "المصطلحات المتداولة بين الجميع", "الإجابات المبهمة"],
                "answer": 2,
                "explanations": {
                    "correct": "يمنع استخدام المصطلحات المتداولة بين الجميع لأنها تفقد الغرض من السرية وقد يفهمها أي شخص.",
                    "wrong1": "الشيفرة مطلوبة للحفاظ على سرية المعلومات.",
                    "wrong2": "الأسماء الرمزية تستخدم للحفاظ على السرية.",
                    "wrong3": "الإجابات المبهمة قد تكون ضرورية في بعض الأحيان للحفاظ على الأمن."
                }
            },
            {
                "id": 11,
                "q": "يجب أن تكون اللهجة أثناء المحادثة:",
                "options": ["سريعة وغير واضحة", "رسمية جداً", "عادية ومفهومة", "منخفضة وغير مسموعة"],
                "answer": 2,
                "explanations": {
                    "correct": "يجب أن تكون اللهجة أثناء المحادثة عادية ومفهومة لضمان وصول المعلومة بشكل واضح ودقيق.",
                    "wrong1": "اللهجة السريعة وغير الواضحة تؤدي إلى سوء الفهم.",
                    "wrong2": "اللهجة الرسمية جداً قد تعيق التواصل الفعال.",
                    "wrong3": "اللهجة المنخفضة وغير المسموعة تمنع وصول المعلومة."
                }
            },
            {
                "id": 12,
                "q": "السرعة المناسبة للإرسال هي:",
                "options": ["بطيئة جداً", "عالية جداً", "سرعة إملائية", "سرعة Morse"],
                "answer": 2,
                "explanations": {
                    "correct": "السرعة الإملائية هي السرعة المناسبة للإرسال، حيث تمكن المستقبل من فهم وتدوين المعلومات بدقة.",
                    "wrong1": "السرعة البطيئة جداً تضيع الوقت.",
                    "wrong2": "السرعة العالية جداً تؤدي إلى أخطاء في الاستقبال.",
                    "wrong3": "سرعة Morse محددة لنظام مورس وليست للاتصال الصوتي."
                }
            },
            {
                "id": 13,
                "q": "الاسم الرمزي 'شمس' يعني:",
                "options": ["أركان حرب", "قائد", "ركن العمليات", "الدفاع الجوي"],
                "answer": 1,
                "explanations": {
                    "correct": "الاسم الرمزي 'شمس' يشير إلى القائد في نظام الترميز العسكري.",
                    "wrong1": "أركان حرب له اسم رمزي مختلف.",
                    "wrong2": "ركن العمليات له اسم رمزي مختلف.",
                    "wrong3": "الدفاع الجوي له اسم رمزي مختلف."
                }
            },
            {
                "id": 14,
                "q": "الاسم الرمزي 'برق' يشير إلى:",
                "options": ["سلاح الهندسة", "سلاح الجو", "سلاح الإشارة", "الشرطة العسكرية"],
                "answer": 2,
                "explanations": {
                    "correct": "الاسم الرمزي 'برق' يشير إلى سلاح الإشارة في نظام الترميز العسكري.",
                    "wrong1": "سلاح الهندسة له اسم رمزي مختلف.",
                    "wrong2": "سلاح الجو له اسم رمزي مختلف.",
                    "wrong3": "الشرطة العسكرية لها اسم رمزي مختلف."
                }
            },
            {
                "id": 15,
                "q": "الاسم الرمزي 'نجم' يدل على:",
                "options": ["ركن التموين", "ركن الإدارة", "أركان حرب", "القائد"],
                "answer": 2,
                "explanations": {
                    "correct": "الاسم الرمزي 'نجم' يدل على أركان حرب في نظام الترميز العسكري.",
                    "wrong1": "ركن التموين له اسم رمزي مختلف.",
                    "wrong2": "ركن الإدارة له اسم رمزي مختلف.",
                    "wrong3": "القائد له اسم رمزي مختلف وهو 'شمس'."
                }
            },
            {
                "id": 16,
                "q": "المحطة الرئيسية مهمتها:",
                "options": ["تلقي فقط", "التنسيق والسيطرة على الشبكة", "تشفير البرقيات", "إرسال فقط"],
                "answer": 1,
                "explanations": {
                    "correct": "المحطة الرئيسية مهمتها التنسيق والسيطرة على الشبكة اللاسلكية وإدارة الاتصالات بين المحطات المختلفة.",
                    "wrong1": "المحطة الرئيسية تقوم بالإرسال والاستقبال وليس الاستقبال فقط.",
                    "wrong2": "تشفير البرقيات قد تقوم به المحطة الرئيسية لكنها ليست مهمتها الأساسية.",
                    "wrong3": "المحطة الرئيسية تقوم بالإرسال والاستقبال وليس الإرسال فقط."
                }
            },
            {
                "id": 17,
                "q": "المحطة الفرعية الأولى هي:",
                "options": ["صاحبة أكبر نداء", "التي تحل محل الرئيسية عند غيابها", "المحطة خارج الشبكة", "محطة الإرسال الاحتياطي"],
                "answer": 1,
                "explanations": {
                    "correct": "المحطة الفرعية الأولى هي التي تحل محل المحطة الرئيسية عند غيابها أو تعطلها.",
                    "wrong1": "ليس بالضرورة أن تكون صاحبة أكبر نداء.",
                    "wrong2": "المحطة خارج الشبكة ليست جزءاً من الشبكة الأساسية.",
                    "wrong3": "محطة الإرسال الاحتياطي قد تكون منفصلة عن المحطة الفرعية الأولى."
                }
            },
            {
                "id": 18,
                "q": "العنوان يتكون من:",
                "options": ["رقمين", "أربعة أرقام", "ثلاثة أحرف أو اسم رمزي", "رقم ثم حرف"],
                "answer": 2,
                "explanations": {
                    "correct": "العنوان في نظام الاتصالات العسكرية يتكون عادة من ثلاثة أحرف أو اسم رمزي للتعريف.",
                    "wrong1": "رقمين قد لا يكونان كافيين للتعريف.",
                    "wrong2": "أربعة أرقام قد تكون مفرطة في الطول.",
                    "wrong3": "رقم ثم حرف ليس الشكل المعياري للعنوان."
                }
            },
            {
                "id": 19,
                "q": "النداء المتغير يعطى عادة لـ:",
                "options": ["الوحدات تحت مستوى السرية", "الوحدات أقل من كتيبة", "الوحدات من مستوى كتيبة فأعلى", "الهواتف الميدانية"],
                "answer": 2,
                "explanations": {
                    "correct": "النداء المتغير يعطى عادة للوحدات من مستوى كتيبة فأعلى لأهميتها وحاجتها للسرية.",
                    "wrong1": "الوحدات تحت مستوى السرية قد لا تحتاج لنداء متغير.",
                    "wrong2": "الوحدات أقل من كتيبة قد تستخدم نداءات ثابتة.",
                    "wrong3": "الهواتف الميدانية لها نظام نداء مختلف."
                }
            },
            {
                "id": 20,
                "q": "يستخدم نداء تمييز الشبكة عند:",
                "options": ["المحادثة العادية", "إرسال برقية", "تأسيس الاتصال أو حدوث تداخل", "تغيير الأسماء الرمزية"],
                "answer": 2,
                "explanations": {
                    "correct": "يستخدم نداء تمييز الشبكة عند تأسيس الاتصال أو حدوث تداخل لضمان التعريف الصحيح للمحطات.",
                    "wrong1": "في المحادثة العادية يستخدم النداء العادي.",
                    "wrong2": "إرسال البرقية لا يتطلب بالضرورة نداء تمييز الشبكة.",
                    "wrong3": "تغيير الأسماء الرمزية عملية منفصلة."
                }
            },
            {
                "id": 21,
                "q": "تطلب الهوية عند:",
                "options": ["وضوح الإشارة", "سماع صوت غير مألوف", "عند كل محادثة", "استلام برقية"],
                "answer": 1,
                "explanations": {
                    "correct": "تطلب الهوية عند سماع صوت غير مألوف للتأكد من هوية المتحدث ومنع التسلل.",
                    "wrong1": "وضوح الإشارة لا يعني بالضرورة صحة الهوية.",
                    "wrong2": "طلب الهوية عند كل محادثة غير عملي.",
                    "wrong3": "استلام البرقية لا يتطلب بالضرورة طلب الهوية."
                }
            },
            {
                "id": 22,
                "q": "في الهوية المعاكسة يجب على المحطة:",
                "options": ["تجاهل الطلب", "طلب هوية المحطة التي طلبت هويتها", "إرسال برقية", "فتح الشبكة"],
                "answer": 1,
                "explanations": {
                    "correct": "في الهوية المعاكسة يجب على المحطة طلب هوية المحطة التي طلبت هويتها للتأكد المتبادل.",
                    "wrong1": "تجاهل الطلب يخالف إجراءات الأمن.",
                    "wrong2": "إرسال برقية لا علاقة له بالهوية المعاكسة.",
                    "wrong3": "فتح الشبكة ليس إجراءً مرتبطاً بالهوية المعاكسة."
                }
            },
            {
                "id": 23,
                "q": "البرقية الواضحة يكون:",
                "options": ["متنها مشفراً", "عنوانها واضح", "عنوانها مرمز ومتنها واضح", "بدون درجة سرية"],
                "answer": 2,
                "explanations": {
                    "correct": "البرقية الواضحة يكون عنوانها مرمز ومتنها واضح لضمان السرية مع إمكانية الفهم السريع.",
                    "wrong1": "إذا كان المتن مشفراً فهي برقية مشفرة وليست واضحة.",
                    "wrong2": "عنوانها الواضح فقط لا يكفي لتصنيفها كبرقية واضحة.",
                    "wrong3": "البرقية الواضحة قد يكون لها درجة سرية مناسبة."
                }
            },
            {
                "id": 24,
                "q": "قسم البرقية الذي يحتوي النص يسمى:",
                "options": ["المقدمة", "المتن", "النهاية", "الخاتمة"],
                "answer": 1,
                "explanations": {
                    "correct": "قسم البرقية الذي يحتوي النص يسمى المتن، وهو الجزء الرئيسي الذي يحوي المعلومات المراد نقلها.",
                    "wrong1": "المقدمة تحتوي معلومات التعريف وليس النص.",
                    "wrong2": "النهاية تحتوي معلومات الإغلاق وليس النص.",
                    "wrong3": "الخاتمة قد تحتوي توقيعاً أو معلومات إضافية وليس النص الرئيسي."
                }
            },
            {
                "id": 25,
                "q": "البرقية 'فوري' يتم إرسالها خلال:",
                "options": ["12 ساعة", "3 ساعات", "30 دقيقة", "10 دقائق"],
                "answer": 3,
                "explanations": {
                    "correct": "البرقية 'فوري' يتم إرسالها خلال 10 دقائق كحد أقصى لأهميتها القصوى.",
                    "wrong1": "12 ساعة مدة طويلة جداً للبرقية الفورية.",
                    "wrong2": "3 ساعات مدة طويلة للبرقية الفورية.",
                    "wrong3": "30 دقيقة مدة أطول من المطلوب للبرقية الفورية."
                }
            },
            {
                "id": 26,
                "q": "الشبكة الحرة تعني:",
                "options": ["تبادل البرقيات بإذن", "عدم إرسال البرقيات", "تبادل البرقيات مباشرة دون إذن", "توقف العمل"],
                "answer": 2,
                "explanations": {
                    "correct": "الشبكة الحرة تعني تبادل البرقيات مباشرة بين المحطات دون الحاجة للحصول على إذن من المحطة الرئيسية.",
                    "wrong1": "تبادل البرقيات بإذن هو وصف للشبكة المقيدة.",
                    "wrong2": "عدم إرسال البرقيات يعني توقف العمل وليس الشبكة الحرة.",
                    "wrong3": "توقف العمل يعني انقطاع الاتصال وليس الشبكة الحرة."
                }
            },
            {
                "id": 27,
                "q": "الشبكة تُقيد إذا:",
                "options": ["كانت الإشارات قوية", "كان هناك انضباط كامل", "ضعف السماع بين الفرعيات", "عدم وجود رئيسية"],
                "answer": 2,
                "explanations": {
                    "correct": "الشبكة تُقيد إذا ضعف السماع بين المحطات الفرعية لضمان تنظيم الاتصال ومنع الفوضى.",
                    "wrong1": "الإشارات القوية تساعد على استمرار الشبكة الحرة.",
                    "wrong2": "الانضباط الكامل يسمح باستمرار الشبكة الحرة.",
                    "wrong3": "عدم وجود رئيسية يتطلب نظاماً بديلاً وليس بالضرورة تقييد الشبكة."
                }
            },
            {
                "id": 28,
                "q": "أعلى درجة سرية هي:",
                "options": ["محظور", "مكتوم", "سري", "سري للغاية"],
                "answer": 3,
                "explanations": {
                    "correct": "'سري للغاية' هي أعلى درجة سرية في التصنيف العسكري للمعلومات.",
                    "wrong1": "'محظور' قد يشير إلى منع وليس درجة سرية.",
                    "wrong2": "'مكتوم' درجة سرية متوسطة.",
                    "wrong3": "'سري' درجة سرية عادية وليست الأعلى."
                }
            },
            {
                "id": 29,
                "q": "البرقية غير المفيدة للعدو ترسل:",
                "options": ["بالشيفرة", "سري للغاية", "بالمفتوح", "عاجلة"],
                "answer": 2,
                "explanations": {
                    "correct": "البرقية غير المفيدة للعدو يمكن إرسالها بالمفتاح المفتوح (بدون تشفير) لأنها لا تحوي معلومات حساسة.",
                    "wrong1": "إرسالها بالشيفرة غير ضروري إذا كانت غير مفيدة للعدو.",
                    "wrong2": "'سري للغاية' درجة سرية عالية ولا علاقة لها بفائدة المعلومات للعدو.",
                    "wrong3": "'عاجلة' تصنيف للأهمية وليس للسرية."
                }
            },
            {
                "id": 30,
                "q": "النداء المفرد يكون بين:",
                "options": ["عدة محطات", "رئيسية ومجموعة", "محطتين فقط", "جميع الشبكة"],
                "answer": 2,
                "explanations": {
                    "correct": "النداء المفرد يكون بين محطتين فقط لإجراء اتصال مباشر ومحدد.",
                    "wrong1": "النداء لعدة محطات يكون نداء جزئي أو عام.",
                    "wrong2": "النداء بين رئيسية ومجموعة يكون نداء جزئي.",
                    "wrong3": "النداء لجميع الشبكة يكون نداء عام."
                }
            },
            {
                "id": 31,
                "q": "النداء العام يوجه إلى:",
                "options": ["محطتين", "جميع محطات الشبكة", "محطات نداء جزئي", "محطات رئيسية فقط"],
                "answer": 1,
                "explanations": {
                    "correct": "النداء العام يوجه إلى جميع محطات الشبكة لنقل معلومات تهم الكل.",
                    "wrong1": "النداء لمحطتين فقط يكون نداء مفرد.",
                    "wrong2": "محطات نداء جزئي تكون مجموعة محددة وليست جميع الشبكة.",
                    "wrong3": "المحطات الرئيسية فقط تكون نداء خاص وليس عام."
                }
            },
            {
                "id": 32,
                "q": "عند إرسال برقية والشبكة مقيدة يجب:",
                "options": ["عدم طلب إذن", "أخذ إذن من الرئيسية", "إرسال البرقية مباشرة", "استخدام نداء عام"],
                "answer": 1,
                "explanations": {
                    "correct": "عند إرسال برقية والشبكة مقيدة يجب أخذ إذن من المحطة الرئيسية أولاً لتنظيم الاتصال.",
                    "wrong1": "عدم طلب إذن يخالف نظام الشبكة المقيدة.",
                    "wrong2": "إرسال البرقية مباشرة مسموح فقط في الشبكة الحرة.",
                    "wrong3": "استخدام نداء عام لا يحل محل طلب الإذن في الشبكة المقيدة."
                }
            },
            {
                "id": 33,
                "q": "البرقية الطويلة تحتاج:",
                "options": ["سرعة عالية", "تقديم برقيات", "عدم التسجيل", "اتصال ضعيف"],
                "answer": 1,
                "explanations": {
                    "correct": "البرقية الطويلة تحتاج تقديم برقيات (إشعار مسبق) لإعلام المستقبل بطول الرسالة واستعداده لتلقيها.",
                    "wrong1": "السرعة العالية قد تؤدي إلى أخطاء في البرقيات الطويلة.",
                    "wrong2": "عدم التسجيل يخالف إجراءات التوثيق.",
                    "wrong3": "الاتصال الضعيف يعيق إرسال البرقيات الطويلة."
                }
            },
            {
                "id": 34,
                "q": "يستخدم جدول رمز الأرقام عند:",
                "options": ["تشفير الأسماء", "إرسال الإحداثيات", "تشفير الكلمات", "تشفير البرقيات التحريرية"],
                "answer": 1,
                "explanations": {
                    "correct": "يستخدم جدول رمز الأرقام عند إرسال الإحداثيات لضمان دقة نقل البيانات الرقمية.",
                    "wrong1": "تشفير الأnames يستخدم جداول مختلفة.",
                    "wrong2": "تشفير الكلمات يستخدم جداول كلمات وليس أرقام فقط.",
                    "wrong3": "تشفير البرقيات التحريرية قد يستخدم أنظمة تشفير شاملة."
                }
            },
            {
                "id": 35,
                "q": "عند تكرار رقم مرتين يستخدم:",
                "options": ["كلمة افتح قوس", "كلمة أغلق قوس", "حرف التكرار الأول ثم الثاني", "الرقم نفسه"],
                "answer": 2,
                "explanations": {
                    "correct": "عند تكرار رقم مرتين يستخدم حرف التكرار الأول ثم الثاني للإشارة إلى التكرار.",
                    "wrong1": "كلمة افتح قوس تستخدم لبداية مجموعة.",
                    "wrong2": "كلمة أغلق قوس تستخدم لنهاية مجموعة.",
                    "wrong3": "تكرار الرقم نفسه قد يسبب لبساً."
                }
            },
            {
                "id": 36,
                "q": "يعمل هاتف TA-1/PT على:",
                "options": ["بطاريات", "الطاقة الشمسية", "قوة الصوت", "جهد 12 فولت"],
                "answer": 2,
                "explanations": {
                    "correct": "هاتف TA-1/PT يعمل على قوة الصوت (لا يحتاج لمصدر طاقة خارجي) حيث يحول الطاقة الصوتية إلى إشارات كهربائية.",
                    "wrong1": "لا يعمل على بطاريات.",
                    "wrong2": "لا يعمل على الطاقة الشمسية.",
                    "wrong3": "لا يعمل على جهد 12 فولت."
                }
            },
            {
                "id": 37,
                "q": "مؤشر الدليل البصري يظهر عند:",
                "options": ["انتهاء البطارية", "وجود مكالمة واردة", "عدم وجود خط", "تشغيل الجهاز"],
                "answer": 1,
                "explanations": {
                    "correct": "مؤشر الدليل البصري يظهر عند وجود مكالمة واردة لتنبيه المستخدم.",
                    "wrong1": "الهاتف لا يعمل ببطاريات.",
                    "wrong2": "عدم وجود خط يمنع عمل الهاتف أساساً.",
                    "wrong3": "تشغيل الجهاز لا يظهر بالضرورة المؤشر البصري."
                }
            },
            {
                "id": 38,
                "q": "عند تعطل المرسلة يجب:",
                "options": ["عدم استخدام الهاتف", "التكلم في المستقبلة", "تغيير السلك", "فصل الجهاز"],
                "answer": 1,
                "explanations": {
                    "correct": "عند تعطل المرسلة يجب التكلم في المستقبلة حيث يمكن استخدامها كبديل للاتصال.",
                    "wrong1": "عدم استخدام الهاتف يحرم من وسيلة اتصال مهمة.",
                    "wrong2": "تغيير السلك قد لا يحل مشكلة المرسلة المعطلة.",
                    "wrong3": "فصل الجهاز يوقف الاتصال تماماً."
                }
            },
            {
                "id": 39,
                "q": "يعمل الهاتف TA-312/PT على:",
                "options": ["بطارية واحدة", "بطاريتين 1.5 فولت", "بطارية 12 فولت", "دون بطاريات"],
                "answer": 1,
                "explanations": {
                    "correct": "الهاتف TA-312/PT يعمل على بطاريتين 1.5 فولت لتشغيل الدوائر الإلكترونية.",
                    "wrong1": "لا يعمل على بطارية واحدة.",
                    "wrong2": "لا يعمل على بطارية 12 فولت.",
                    "wrong3": "يعمل ببطاريات وليس دونها."
                }
            },
            {
                "id": 40,
                "q": "مدى إرسال الهاتف في المناطق الجافة:",
                "options": ["6 كم", "15 كم", "22 كم", "35 كم"],
                "answer": 3,
                "explanations": {
                    "correct": "مدى إرسال الهاتف في المناطق الجافة يصل إلى 35 كم بسبب قلة الرطوبة التي تعيق انتقال الإشارات.",
                    "wrong1": "6 كم مدى قصير جداً.",
                    "wrong2": "15 كم مدى أقل من القدرة الحقيقية.",
                    "wrong3": "22 كم مدى متوسط وليس الأقصى."
                }
            },
            {
                "id": 41,
                "q": "الخط الدائري الساخن يستخدم لربط:",
                "options": ["المرسلات فقط", "المدافع بنقطة السيطرة", "الشبكات اللاسلكية", "الهوية"],
                "answer": 1,
                "explanations": {
                    "correct": "الخط الدائري الساخن يستخدم لربط المدافع بنقطة السيطرة لتمكين الاتصال المباشر والسريع.",
                    "wrong1": "ليس للمرسلات فقط.",
                    "wrong2": "لا يستخدم لربط الشبكات اللاسلكية.",
                    "wrong3": "لا علاقة له بالهوية."
                }
            },
            {
                "id": 42,
                "q": "الخط الدائري المفتوح يعني:",
                "options": ["خط مقفل", "خط يستقبل فقط", "أن الاتصالات تمر بشكل تسلسلي", "أن الخط بلا سيطرة"],
                "answer": 2,
                "explanations": {
                    "correct": "الخط الدائري المفتوح يعني أن الاتصالات تمر بشكل تسلسلي بين النقاط المتصلة.",
                    "wrong1": "الخط المقفل مختلف عن المفتوح.",
                    "wrong2": "الخط يستقبل فقط يسمى خط أحادي الاتجاه.",
                    "wrong3": "الخط بلا سيطرة يسمى خط غير منظم."
                }
            },
            {
                "id": 43,
                "q": "من مهام لوحة محادثة المأمور:",
                "options": ["إرسال أوامر واضحة", "استخدام عبارات مبهمة", "زيادة زمن الاتصال", "تسجيل البرقيات"],
                "answer": 1,
                "explanations": {
                    "correct": "من مهام لوحة محادثة المأمور استخدام عبارات مبهمة للحفاظ على السرية.",
                    "wrong1": "إرسال أوامر واضحة قد يخالف السرية.",
                    "wrong2": "زيادة زمن الاتصال غير مرغوب فيه للأمن.",
                    "wrong3": "تسجيل البرقيات قد يتم بواسطة جهاز منفصل."
                }
            },
            {
                "id": 44,
                "q": "المفتاح العمودي والأفقي للوحة المأمور يتم:",
                "options": ["تغييره كل أسبوع", "تغييره يومياً", "تثبيته", "إلغاؤه"],
                "answer": 1,
                "explanations": {
                    "correct": "المفتاح العمودي والأفقي للوحة المأمور يتم تغييره يومياً للحفاظ على الأمن.",
                    "wrong1": "تغييره أسبوعياً فترة طويلة قد تهدد الأمن.",
                    "wrong2": "تثبيته يخالف مبدأ تغيير المفاتيح للأمن.",
                    "wrong3": "إلغاؤه يمنع استخدام النظام."
                }
            },
            {
                "id": 45,
                "q": "الهوية تتكون من لوحة عدد مربعاتها:",
                "options": ["50", "80", "100", "150"],
                "answer": 2,
                "explanations": {
                    "correct": "الهوية تتكون من لوحة عدد مربعاتها 100 (10×10) للتعريف الآمن.",
                    "wrong1": "50 مربع عدد قليل جداً.",
                    "wrong2": "80 مربع ليس العدد القياسي.",
                    "wrong3": "150 مربع عدد كبير جداً."
                }
            },
            {
                "id": 46,
                "q": "عند استخدام هوية يجب شطب:",
                "options": ["الرقم العمودي", "الرقم الأفقي", "الرقم الرباعي بعد الاستخدام", "جميع الأرقام"],
                "answer": 2,
                "explanations": {
                    "correct": "عند استخدام هوية يجب شطب الرقم الرباعي بعد الاستخدام لمنع إعادة استخدامه.",
                    "wrong1": "الرقم العمودي يحتاجه الطرف الآخر للتحقق.",
                    "wrong2": "الرقم الأفقي يحتاجه الطرف الآخر للتحقق.",
                    "wrong3": "شطب جميع الأرقام يمنع التحقق من الهوية."
                }
            },
            {
                "id": 47,
                "q": "عند طلب الهوية يجب البدء بـ:",
                "options": ["الرقم الأفقي", "الرقم العمودي", "الكلمة الرمزية", "النداء العام"],
                "answer": 1,
                "explanations": {
                    "correct": "عند طلب الهوية يجب البدء بالرقم العمودي حسب النظام المتبع.",
                    "wrong1": "الرقم الأفقي يأتي بعد العمودي.",
                    "wrong2": "الكلمة الرمزية تستخدم في سياقات أخرى.",
                    "wrong3": "النداء العام لا علاقة له بالهوية."
                }
            },
            {
                "id": 48,
                "q": "الترددات والنداءات يجب تغييرها:",
                "options": ["سنوياً", "أسبوعياً", "شهرياً", "كلما تطلب الموقف"],
                "answer": 3,
                "explanations": {
                    "correct": "الترددات والنداءات يجب تغييرها كلما تطلب الموقف للحفاظ على الأمن ومنع الاعتراض.",
                    "wrong1": "تغييرها سنوياً فترة طويلة تهدد الأمن.",
                    "wrong2": "تغييرها أسبوعياً قد يكون غير كاف في بعض الظروف.",
                    "wrong3": "تغييرها شهرياً قد يكون غير كاف في بعض الظروف."
                }
            },
            {
                "id": 49,
                "q": "المحطة الفرعية الأولى تحمل:",
                "options": ["أكبر نداء", "أصغر نداء", "رمز الشبكة", "العنوان الأساسي"],
                "answer": 1,
                "explanations": {
                    "correct": "المحطة الفرعية الأولى تحمل أصغر نداء في التسلسل الهرمي للنداءات.",
                    "wrong1": "أكبر نداء يكون للمحطة الرئيسية عادة.",
                    "wrong2": "رمز الشبكة قد يكون مشتركاً بين المحطات.",
                    "wrong3": "العنوان الأساسي قد يكون للمحطة الرئيسية."
                }
            },
            {
                "id": 50,
                "q": "عند الاتصال بالمفتوح يفضل إرسال:",
                "options": ["المعلومات التي لا تفيد العدو", "الإحداثيات السرية", "الأوامر الخططية", "الأسرار العسكرية"],
                "answer": 0,
                "explanations": {
                    "correct": "عند الاتصال بالمفتوح يفضل إرسال المعلومات التي لا تفيد العدو للحفاظ على الأمن.",
                    "wrong1": "إرسال الإحداثيات السرية بالمفتوح يخالف الأمن.",
                    "wrong2": "إرسال الأوامر الخططية بالمفتوح يخالف الأمن.",
                    "wrong3": "إرسال الأسرار العسكرية بالمفتوح يخالف الأمن بشكل كامل."
                }
            }
        ];

        let currentQuestionIndex = 0;
        let userAnswers = Array(questions.length).fill(null);
        let timeLeft = 45 * 60; // 45 دقيقة
        let timerInterval;
        let markedQuestions = [];
        let answerLocked = Array(questions.length).fill(false); // مصفوفة لتتبع حالة القفل لكل سؤال

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
                btn.style.background = 'var(--tertiary)';
            } else {
                markedQuestions.splice(index, 1);
                btn.innerHTML = '<i class="fas fa-flag"></i> وضع علامة للمراجعة';
                btn.style.background = 'var(--secondary)';
            }
            
            if (document.getElementById('questions-list').style.display === 'block') {
                showQuestionsList();
            }
        }

        // تحميل الاختبار
        function loadQuiz() {
            const quizDiv = document.getElementById("quiz");
            quizDiv.innerHTML = "";

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
                        <input type="radio" name="q${currentQuestionIndex}" value="${i}" ${isChecked ? 'checked' : ''} ${isDisabled ? 'disabled' : ''} onchange="selectAnswer(${i})">
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
            document.getElementById('progress').style.width = `${((currentQuestionIndex + 1) / questions.length) * 100}%`;
            
            // تحديث معلومات الاختبار
            document.getElementById('quiz-info').innerHTML = `السؤال ${currentQuestionIndex + 1} من ${questions.length}`;
            
            // تحديث زر وضع العلامة
            const markBtn = document.getElementById('mark-review-btn');
            if (markedQuestions.includes(currentQuestionIndex)) {
                markBtn.innerHTML = '<i class="fas fa-flag"></i> إزالة العلامة';
                markBtn.style.background = 'var(--tertiary)';
            } else {
                markBtn.innerHTML = '<i class="fas fa-flag"></i> وضع علامة للمراجعة';
                markBtn.style.background = 'var(--secondary)';
            }
            
            // عرض الشرح إذا كان المستخدم قد أجاب على السؤال
            if (userAnswers[currentQuestionIndex] !== null) {
                showExplanation();
            }
        }

        // اختيار إجابة
        function selectAnswer(answerIndex) {
            userAnswers[currentQuestionIndex] = answerIndex;
            answerLocked[currentQuestionIndex] = true; // قفل الإجابة
            showExplanation();
            loadQuiz(); // إعادة تحميل لعرض التغييرات
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
                
                if (question.explanations.wrong1) {
                    resultHTML += `<div class="explanation-line explanation-wrong-1">${question.explanations.wrong1}</div>`;
                }
                
                if (question.explanations.wrong2) {
                    resultHTML += `<div class="explanation-line explanation-wrong-2">${question.explanations.wrong2}</div>`;
                }
                
                if (question.explanations.wrong3) {
                    resultHTML += `<div class="explanation-line explanation-wrong-3">${question.explanations.wrong3}</div>`;
                }
                
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
                if (answer === questions[index].answer) {
                    totalCorrect++;
                }
            });

            const total = questions.length;
            const percentage = ((totalCorrect / total) * 100).toFixed(2);

            document.getElementById("current-score").style.display = "block";
            document.getElementById("current-correct").innerHTML = `الإجابات الصحيحة: ${totalCorrect} من ${total}`;
            document.getElementById("current-percentage").innerHTML = `النسبة المئوية الحالية: ${percentage}%`;
        }

        // حساب الدرجات النهائية
        function finishQuiz() {
            clearInterval(timerInterval);
            
            let totalCorrect = 0;
            userAnswers.forEach((answer, index) => {
                if (answer === questions[index].answer) {
                    totalCorrect++;
                }
            });

            const total = questions.length;
            const percentage = ((totalCorrect / total) * 100).toFixed(2);

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
            } else {
                evaluation = "يحتاج تحسين";
                evaluationIcon = "⚠️";
            }

            document.getElementById("result-box").style.display = "block";
            document.getElementById("result").innerHTML = `${evaluationIcon} النتيجة: ${totalCorrect} من ${total}`;
            document.getElementById("percentage").innerHTML = `النسبة المئوية: ${percentage}%`;
            document.getElementById("evaluation").innerHTML = `التقييم: ${evaluation}`;
            
            // إخفاء الاختبار
            document.getElementById("quiz").style.display = "none";
            document.querySelector(".controls").style.display = "none";
            document.getElementById('questions-list').style.display = 'none';
        }

        // بدء التحميل الأولي
        window.onload = function() {
            checkDarkModePreference();
            loadQuiz();
            startTimer();
        }
    </script>
</body>
</html>
